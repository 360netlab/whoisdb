# whoisdb
The python client of 360 Netlab whois database

```
Usage:  whoisdb exists  domain,domain,...
	whoisdb detail  domain,domain,...
	whoisdb history domain
	whoisdb count   domain,domain,...
	whoisdb count   field  value
	whoisdb related domain
	whoisdb reverse value ( default field : <name && email && organization> )
	whoisdb reverse field value

	field: (name, email, organization, phone, nameserver, registrant_email, registrant_name, registrant_organization, registrant_phone, admin_email, admin_name, admin_organization, tech_email, tech_name, tech_organization)

Options:
  -h, --help            show this help message and exit
  -d, --debug           show http url and and http header, including SENSITIVE
                        token
  -b, --brief           show parts of fields (name, email, organization)
  -v, --verbose         show detail field (original unparsed WHOIS)
  -j, --json            output in json format
  -r, --renew           Refresh record if not exists, used with detail, one
                        domain per query
  -V, --version
  -l LIMIT, --limit=LIMIT
                        maximum number of results. works for method reverse
                        and related. [default: 1000]
  -s SKIP, --skip=SKIP  number of documents to skip. works for method reverse
                        and related. [default: 0]
  -c CONFIG, --config=CONFIG
                        config file
```
