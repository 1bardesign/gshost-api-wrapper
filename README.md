# Introduction

gshost-api-wrapper (`gshost_api.py`) is an MIT Licensed Python wrapper around the GSHost Web API, allowing the secure remote administration of servers hosted at gshost.us.

All requests are made synchronously over HTTPS, and raise errors if something goes wrong.

# Installation

Clone the repo with git:

```
$ git clone https://github.com/1bardesign/gshost-api-wrapper.git
```

(Or: download a zip [from github!](https://github.com/1bardesign/gshost-api-wrapper) (top right))

# Usage

```
import gshost_api

# lets set up a fresh autoconfig from python!

my_server = gshost_api.server('node_url.gshost.us', server_number, ('username', 'password'))

if my_server.running():
	my_server.stop()

autoconfig = {}
autoconfig['sv_name'] = 'My GSHost Server'
autoconfig['sv_name'] = 'My GSHost Server'
if sv_password != '':
	autoconfig['sv_password'] = sv_password

my_server.write_config_from_dict('autoconfig.cfg', autoconfig)

my_server.start()
```

# Dependencies

`gshost_api.py` depends on `requests` - you can learn more [here](python-requests.org/) or use pip to install `requests` if you haven't already.