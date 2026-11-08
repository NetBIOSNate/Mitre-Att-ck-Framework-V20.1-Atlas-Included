# DC0104 - Response Content

[Enterprise](../../README.md) / [Data Components](README.md)

Captured network traffic that provides details about responses received during an internet scan. This data includes both protocol header values (e.g., HTTP status codes, IP headers, or DNS response codes) and response body content (e.g., HTML, JSON, or raw data). Examples:

- HTTP Scan: A web server responds to a probe with an HTTP 200 status code and an HTML body indicating the default page is accessible.
- DNS Scan: A DNS server replies to a query with a resolved IP address for a domain, along with details like Time-To-Live (TTL) and authoritative information.
- TCP Banner Grab: A service listening on a port (e.g., SSH or FTP) responds with a banner containing service name, version, or other metadata.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0104)

## Log sources and channels

- **Internet Scan** — None
- **NSM:Flow** — Suspicious changes in TLS certificate responses or redirected domains

## Analytics using this component

- [AN1150 - Analytic 1150](../Analytics/AN1150.md)
- [AN1952 - Analytic 1952](../Analytics/AN1952.md)
- [AN1956 - Analytic 1956](../Analytics/AN1956.md)
- [AN1957 - Analytic 1957](../Analytics/AN1957.md)
- [AN1958 - Analytic 1958](../Analytics/AN1958.md)
- [AN1961 - Analytic 1961](../Analytics/AN1961.md)
- [AN1966 - Analytic 1966](../Analytics/AN1966.md)
- [AN1968 - Analytic 1968](../Analytics/AN1968.md)
- [AN1970 - Analytic 1970](../Analytics/AN1970.md)
- [AN1971 - Analytic 1971](../Analytics/AN1971.md)
- [AN1972 - Analytic 1972](../Analytics/AN1972.md)
- [AN1976 - Analytic 1976](../Analytics/AN1976.md)
- [AN1980 - Analytic 1980](../Analytics/AN1980.md)
- [AN1982 - Analytic 1982](../Analytics/AN1982.md)
- [AN1985 - Analytic 1985](../Analytics/AN1985.md)
- [AN1986 - Analytic 1986](../Analytics/AN1986.md)
- [AN1991 - Analytic 1991](../Analytics/AN1991.md)
- [AN1996 - Analytic 1996](../Analytics/AN1996.md)
- [AN2003 - Analytic 2003](../Analytics/AN2003.md)
- [AN2006 - Analytic 2006](../Analytics/AN2006.md)
- [AN2013 - Analytic 2013](../Analytics/AN2013.md)
- [AN2014 - Analytic 2014](../Analytics/AN2014.md)
- [AN2017 - Analytic 2017](../Analytics/AN2017.md)
- [AN2019 - Analytic 2019](../Analytics/AN2019.md)
- [AN2020 - Analytic 2020](../Analytics/AN2020.md)
- [AN2025 - Analytic 2025](../Analytics/AN2025.md)
- [AN2027 - Analytic 2027](../Analytics/AN2027.md)
- [AN2028 - Analytic 2028](../Analytics/AN2028.md)
