# Passive Reconnaissance

## Objective

Perform passive reconnaissance against `certifiedhacker.com` using publicly available information.

The objective was to collect domain, DNS, search-engine, and internet-exposed infrastructure information without performing intrusive exploitation.

---

## Target

**Target Domain:** `certifiedhacker.com`

**Resolved IPv4 Address:** `162.241.216.11`

The target was used for the passive reconnaissance activities required for Task 2.

---

# 1. WHOIS Enumeration

## Purpose

WHOIS enumeration is used to obtain publicly available domain-registration information.

It can provide information such as:

- Domain registration dates
- Registrar
- Domain status
- Name servers
- DNSSEC status
- Registrant information when publicly available
- Registration privacy information

## Command Used

    whois certifiedhacker.com

## Findings

The WHOIS query returned the following information:

| Field | Result |
|---|---|
| Domain Name | `CERTIFIEDHACKER.COM` |
| Registry Domain ID | `88849376_DOMAIN_COM-VRSN` |
| Registrar | Network Solutions, LLC |
| Registrar IANA ID | `2` |
| Creation Date | `2002-07-30T00:32:00Z` |
| Registry Expiry Date | `2027-07-30T00:32:00Z` |
| Updated Date | `2026-05-30T06:36:42Z` |
| Domain Status | `clientTransferProhibited` |
| Name Server | `NS1.BLUEHOST.COM` |
| Name Server | `NS2.BLUEHOST.COM` |
| DNSSEC | Unsigned |
| Registrant | Perfect Privacy, LLC |
| Registrant Organization | Not publicly listed |
| Registrant Country | US |

The WHOIS output also indicated that the domain uses Network Solutions private registration. Therefore, the actual registrant's personal contact information was not publicly exposed in the returned record.

## Security-Relevant Observations

1. The domain has been registered since 2002.
2. Network Solutions, LLC is listed as the registrar.
3. The domain uses Bluehost name servers.
4. DNSSEC is reported as unsigned.
5. Registrant information is protected through a privacy-registration service.
6. The `clientTransferProhibited` status indicates that the domain has a registrar-level transfer restriction.

## Evidence

- `screenshots/01-whois.png`
- `screenshots/02-whois.png`

The two screenshots contain the complete WHOIS output captured during the practical exercise.

---

# 2. DNS Enumeration with Nslookup

## Purpose

`nslookup` is a DNS query utility used to determine how a domain resolves through DNS.

In this exercise, it was used to identify the IPv4 address associated with the target domain.

## Command Used

    nslookup certifiedhacker.com

## Result

The command returned:

    Server:         192.168.122.1
    Address:        192.168.122.1#53

    Non-authoritative answer:
    Name:   certifiedhacker.com
    Address: 162.241.216.11

## Findings

| Field | Result |
|---|---|
| DNS Server | `192.168.122.1` |
| DNS Server Port | `53` |
| Response Type | Non-authoritative |
| Domain | `certifiedhacker.com` |
| IPv4 Address | `162.241.216.11` |

The domain resolved to `162.241.216.11` during the test.

The response was non-authoritative, meaning the DNS server used for the query was providing the answer from its resolver/cache rather than acting as the authoritative DNS server for the domain.

## Security-Relevant Observation

The resolved IPv4 address was subsequently used as the reference point for examining publicly indexed information in Shodan.

## Evidence

- `screenshots/03-nslookup-certifiedhacker.png`

---

# 3. Google Dorking

## Purpose

Google Dorking uses search-engine operators to locate publicly indexed information associated with a specific domain.

The objective was to identify publicly searchable pages, documents, and potentially interesting URL patterns without directly scanning the target infrastructure.

## Queries Tested

### Query 1 — Domain Discovery

    site:certifiedhacker.com

This query restricts Google results to pages indexed under the target domain.

### Query 2 — PDF Document Discovery

    site:certifiedhacker.com filetype:pdf

This query attempts to identify PDF documents indexed by Google that belong to the target domain.

### Query 3 — Directory Listing Search

    site:certifiedhacker.com intitle:"index of"

This query searches for pages whose title contains `index of`, which can sometimes indicate directory-listing pages.

### Query 4 — Login Page Discovery

    site:certifiedhacker.com inurl:login

This query searches for URLs containing `login` within the target domain.

## Methodology

The queries were executed through a normal search engine rather than by directly crawling or scanning the target.

The results were reviewed to determine what information was publicly indexed and discoverable through search-engine queries.

## Security-Relevant Observations

Google Dorking demonstrates that information may be discoverable without directly interacting with the target infrastructure.

Search-engine indexing can expose:

- Public documentation
- PDF files
- Login-related pages
- Publicly indexed URLs
- Other domain-associated resources

The results were treated as passive reconnaissance data and were not used for exploitation.

## Evidence

- `screenshots/04-G-Dorking.png`
- `screenshots/05-G-Dorking-Filetype.png`
- `screenshots/06-G-Dorking.png`
- `screenshots/07-G-Dorking.png`

---

# 4. Shodan Reconnaissance

## Purpose

Shodan is an internet-wide search engine that indexes information about publicly accessible hosts and services.

For this exercise, the IP address obtained from DNS enumeration was searched in Shodan.

## Target IP

    162.241.216.11

## Findings

The Shodan result displayed the following information:

| Category | Observation |
|---|---|
| IP Address | `162.241.216.11` |
| Country | United States |
| City | Provo |
| Organization | Unified Layer |
| ISP | Unified Layer |
| ASN | `AS46606` |
| Domains shown | `bluehost.com`, `rdjeinc.com` |
| Example detected service | Pure-FTPd |
| Example service port | `21` |
| Indexed services | Multiple TCP services |

Shodan displayed multiple services associated with the IP address.

The indexed ports visible in the result included:

    21
    22
    26
    53
    80
    110
    143
    443
    465
    587
    993
    995
    2077
    2079
    2082
    2083
    2086
    2087
    2095
    2096
    2222
    3306
    5432

Shodan identified Pure-FTPd on port `21` in the displayed service information.

## Important Observation

The IP address appears to be associated with shared hosting infrastructure because Shodan displayed multiple domains and hostnames associated with the same address.

Therefore, the presence of a particular service or port on `162.241.216.11` should **not automatically be interpreted as a service belonging exclusively to `certifiedhacker.com`**.

This distinction is important when analyzing passive reconnaissance results on shared hosting infrastructure.

## Evidence

- `screenshots/08-shodan-certifiedhacker.png`

---

# 5. Overall Findings

The passive reconnaissance exercise produced information from four different public sources.

### WHOIS

Provided:

- Registrar information
- Domain creation date
- Domain expiry date
- Domain status
- Name servers
- DNSSEC status
- Registration privacy information

### Nslookup

Provided:

- DNS resolver information
- Domain resolution status
- IPv4 address associated with the domain

### Google Dorking

Demonstrated how search-engine operators can be used to identify publicly indexed resources associated with a domain.

### Shodan

Provided publicly indexed infrastructure information associated with the resolved IP address, including:

- Geographic information
- Organization
- ISP
- ASN
- Associated domains
- Indexed network services

---

# 6. Methodology and Scope

The activities documented in this section were limited to passive reconnaissance and publicly available information.

No exploitation was performed as part of passive reconnaissance.

The following techniques were used:

- WHOIS enumeration
- DNS resolution using `nslookup`
- Search-engine reconnaissance using Google operators
- Publicly indexed host/service information using Shodan

The results represent information available at the time of testing and may change as DNS records, search-engine indexes, domain registration data, or Shodan's database are updated.

---

# 7. Evidence Summary

| Evidence | Activity |
|---|---|
| `01-whois.png` | WHOIS output — Part 1 |
| `02-whois.png` | WHOIS output — Part 2 |
| `03-nslookup-certifiedhacker.png` | DNS resolution |
| `04-G-Dorking.png` | Google Dorking |
| `05-G-Dorking-Filetype.png` | PDF filetype search |
| `06-G-Dorking.png` | Google indexed-resource search |
| `07-G-Dorking.png` | Google URL/login search |
| `08-shodan-certifiedhacker.png` | Shodan IP reconnaissance |

---

# 8. Conclusion

Passive reconnaissance successfully collected publicly available information about `certifiedhacker.com` from WHOIS, DNS resolution, Google indexing, and Shodan.

The exercise demonstrated how an analyst can build an initial picture of a target's domain registration, DNS configuration, publicly indexed resources, and internet-facing infrastructure without beginning with intrusive vulnerability testing.

**Status: Passive Reconnaissance Completed**
