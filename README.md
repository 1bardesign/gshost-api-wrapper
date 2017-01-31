# Introduction

gshost-api-wrapper (`gshost_api.py`) is an MIT Licensed Python wrapper around the GSHost Web API, allowing the secure remote administration of servers hosted at gshost.us.

All requests are made synchronously over HTTPS, and raise errors if something goes wrong.

# Installation

Clone the repo with git:

```
$ git clone https://github.com/1bardesign/gshost-api-wrapper.git
```

(Or download a zip [from github!](https://github.com/1bardesign/gshost-api-wrapper) (top right))

# Usage

You'll need to get your node url and server number from your [servers panel](https://gshost.us/my_servers) - your node url is given under IP:Port (don't take the port part), your server number is the number after /id/ in the URL for managing a specific server.

Be careful: your server number is NOT the same as your port.

```
import gshost_api

# lets set up a fresh autoconfig from python!

my_server = gshost_api.server('node_url.gshost.us', server_number, ('username', 'password'))

if my_server.running():
	my_server.stop()

autoconfig = {}
autoconfig['sv_name'] = 'My GSHost Server'
autoconfig['sv_info'] = 'This server is managed remotely using a very cool script'
autoconfig['sv_gamemode'] = 'TDM'
my_server.write_config_from_dict('autoconfig.cfg', autoconfig)

my_server.start()
```

# Dependencies

`gshost_api.py` depends on `requests` - you can learn more [here](http://docs.python-requests.org/) or just use pip to install `requests` if you haven't already.

# Warning

This has only been tested with KAG servers. I'm not sure yet how it'll go with other server types.
