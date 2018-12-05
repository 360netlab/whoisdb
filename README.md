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

The output demo

```
➜  whoisdb $ python whoisdb detail apple.com
apple.com	domainname                  apple.com
apple.com	createddate                 1987-02-19 05:00:00
apple.com	updateddate                 2018-09-27 20:53:12
apple.com	expiresdate                 2021-02-20 05:00:00
apple.com	status                      clientTransferProhibited
apple.com	registrant_email            domains@apple.com
apple.com	registrant_name             Domain Administrator
apple.com	registrant_organization     Apple Inc.
apple.com	registrant_address          One Apple Park Way
apple.com	registrant_city             Cupertino
apple.com	registrant_state            CA
apple.com	registrant_postalcode       95014
apple.com	registrant_country          UNITED STATES
apple.com	registrant_fax              +1.4089741560
apple.com	registrant_telephone        +1.4089961010
apple.com	admin_email                 domains@apple.com
apple.com	admin_name                  Domain Administrator
apple.com	admin_organization          Apple Inc.
apple.com	admin_address               One Apple Park Way
apple.com	admin_city                  Cupertino
apple.com	admin_state                 CA
apple.com	admin_postalcode            95014
apple.com	admin_country               UNITED STATES
apple.com	admin_fax                   +1.4089741560
apple.com	admin_telephone             +1.4089961010
apple.com	tech_email                  apple-noc@apple.com
apple.com	tech_name                   Domain Administrator
apple.com	tech_organization           Apple Inc.
apple.com	tech_address                One Apple Park Way
apple.com	tech_city                   Cupertino
apple.com	tech_state                  CA
apple.com	tech_postalcode             95014
apple.com	tech_country                UNITED STATES
apple.com	tech_fax                    +1.4089741560
apple.com	tech_telephone              +1.4089961010
apple.com	registrarname               CSC CORPORATE DOMAINS, INC.
apple.com	whoisserver                 whois.corporatedomains.com
apple.com	nameservers                 a.ns.apple.com | b.ns.apple.com | c.ns.apple.com | d.ns.apple.com | e.ns.apple.com | f.ns.apple.com
apple.com	first_seen                  2018-10-15 18:51:34

```

## How to use the script?

Before execute the script, a config file that contain the authentication token should be configured properly.
Any of the following two methods can be work fine.

1. ``cat TOKEN = xxxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxx > ~/.netlab.token`` (Higly recommend)
2. Create netlab.token file at any path, and assign a specified configuration file while running the script with  `-c` parameter 
