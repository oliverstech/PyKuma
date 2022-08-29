# PyKuma
An API for Python Scripts to integrate with Uptime Kuma.

[![PyPI](https://img.shields.io/pypi/v/pykuma)](https://pypi.org/project/pykuma/)
[![GitHub watchers](https://img.shields.io/github/watchers/oliverstech/pykuma?style=social)](https://github.com/oliverstech/pykuma/watchers)
[![GitHub forks](https://img.shields.io/github/forks/oliverstech/pykuma?style=social)](https://github.com/oliverstech/pykuma/fork)
![GitHub Repo stars](https://img.shields.io/github/stars/oliverstech/pykuma?style=social)

Interested in donating? A donate link will be here soon :)



## Installation
### PyPI/pip - Easiest method
The easiest way to install PyKuma is using PyPI. Simply type:
```console
pip install pykuma
```
or, if python isn't in your PATH:
```console
py -m pip install pykuma
```
[View on PyPI](https://pypi.org/project/pykuma/)
### Including the script
1. The second way to install PyKuma is using the script directly. 
2. You can do this by downloading the latest version of the script [here](helper.py) 
3. Place it in the same directory as your script. Once you've done so, rename it to 'pykuma.py'.

## Usage
First, import PyKuma into your project:
```py
import pykuma
# -- or, use an alias --
import pykuma as pyk
```
Secondly, we need to configure it with Uptime Kuma. To do this, open your Uptime Kuma dashboard and create a new Push monitor. Copy the Push URL given.

Now, back at the script, type:
```py
pykuma.configure(url="uptime-kuma-push-url", heartbeat=60, ShowMessage=True, printPush=False)
```
the arguements mean the following:
- `url` - the push URL from Uptime Kuma. Required.
- `heartbeat` - the heartbeat interval to push to kuma in. Optional - if not specified, 60
- `ShowMessage` - whether to show PyKuma credit message. Optional - if not specified, true
- `printPush` - print when pushed. Optional - if not specified, false

Finally, type:
```py
pykuma.start()
```
PyKuma will begin periodically pushing every heartbeat interval. If you check your monitor, you should see one push already come through as PyKuma runs one for testing.

## Dependencies used
- [requests](https://pypi.org/project/requests)
- [asyncio](https://pypi.org/project/asyncio)
