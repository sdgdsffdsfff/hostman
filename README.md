```
-----------------------------------------------------
88  88  dP"Yb  .dP"Y8 888888 8b    d8    db    88b 88
88  88 dP   Yb `Ybo."   88   88b  d88   dPYb   88Yb88
888888 Yb   dP o.`Y8b   88   88YbdP88  dP__Yb  88 Y88
88  88  YbodP  8bodP'   88   88 YY 88 dP""""Yb 88  Y8
-----------------------------------------------------
```

# HostMan
## Description
HostMan is a little tool written in Python to manage ssh access to remote hosts. It's just like SecureCRT or Xshell, but it's much simpler and light-weighted. And what matters most is that I make a wheel for myself again.

Imagine that you're managing tens of linux servers, you event can't remember ip/hostname of each. You can put this IPs/hostnames in hostman's config file and visit them with `UP-ARROW`, `DOWN-ARROW` and `ENTER`.

Imagine that you have to jump to tens of linux servers via a trusted gateway, you've to `ssh` to the gateway and then `ssh` to your target server. With hostman, you can achive this using only `UP-ARROW`, `DOWN-ARROW` and `ENTER`, without `ssh` twice.

## Installation
HostMan depends on [urwid](http://excess.org/urwid/) python library. You can install urwid with the following commands:

```bash
wget http://excess.org/urwid/urwid-1.1.1.tar.gz 
tar zxf urwid-1.1.1.tar.gz 
cd urwid-1.1.1
sudo python setup.py install
```

Then get the `hm` file from github, and put it on your `$PATH`.

## Configuration
Configuate hostman like this:

```ini
;; user@gateway.host as sectioin
[xiafei.qiuxf@login1.myhost.org]
;; hosts logon via this gateway
;; if more than one, one per line
;; format: hostname or user@hostname
hosts = ttbroker236004.cm3
	qiuxiafei@ttbroker216055.cm3
	ttbroker165028.cm3

;; hosts under localhost section will be logged on directly
[localhost]
hosts = xiafei.qiuxf@10.232.130.1
    xiafei@localhost
```
Put your config file at `$HOME/.hostman.ini`.

## Usage
* Type to search in your hosts.
* Press `esc` to clear search text.
* Press `enter` to visit the selected host.
* Press `Ctrl + c` to exit.

__Your're strongly recommend to open SSH channel bettwen your machina and the gates and target servers.__

## TODO
* Remember the password?
