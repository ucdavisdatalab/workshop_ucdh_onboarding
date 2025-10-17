(chapter:vpn)=
# Virtual Private Network (VPN) Access

In order to access computing resources at UCDH remotely, you must first connect
to UCDH's **virtual private network** (VPN). There's an official [help
page for the VPN][vpn-help] with a list of frequently asked questions and links
to the necessary software. This chapter provides a high-level summary of the
steps to access the VPN.

[vpn-help]: https://health.ucdavis.edu/remote-access/vpn/


## Get Permission via Service Now

Recall from the {ref}`chapter:service-now` chapter that to get permissions to
use UCDH computing resources, you must "order" them through the [Service Now
catalog][service-now]. Search the catalog for "VPN" and order the item called
"Remote Access - VPN - External Employee".

[service-now]: https://ucdh.service-now.com


## Install the Client Software

To connect to the VPN, you'll first need to install VPN client software on your
computer. For Windows, macOS, and iOS, the officially supported VPN client is
Cisco AnyConnect. You can install the AnyConnect client by following [these
instructions][vpn-instructions].

[vpn-instructions]: https://health.ucdavis.edu/remote-access/vpn/download-and-install-vpn

:::{tip}
There's no officially supported VPN client for other operating systems, but the
open-source [OpenConnect][] client is able to connect as of writing. You can
install OpenConnect with your operating system's package manager (on Linux) or
with a standalone package manager like [Pixi][] (cross-platform) or
[Homebrew][] (on macOS & Linux).

In our experience, OpenConnect is more reliable than the official AnyConnect
client, but your mileage may vary.

[OpenConnect]: https://gitlab.com/openconnect/openconnect
[Pixi]: https://pixi.sh/
[Homebrew]: https://brew.sh/
:::


## Connect to the VPN

The address for VPN login is `connect.ucdmc.ucdavis.edu`. Type this into the
Cisco AnyConnect client and then click the "Connect" button. Your computer will
stay connected to the VPN until any one of:

* Your computer disconnects from the internet (for example, if the Wifi signal
   drops).
* You put your computer into sleep mode or turn it off.
* You disconnect by clicking the "Disconnect" button.
* You close the Cisco AnyConnect app.

As long as you're connected to the VPN, all of your computer's network traffic
is routed through UCDH on a connection that is encrypted between you and UCDH.
This adds stops between your computer and the Internet, so you may notice that
your Internet connection is a bit slower than without the VPN (this often
affects my Zoom calls, for instance).


:::{tip}
The command to connect to the VPN via OpenConnect is:
```
sudo openconnect --protocol=anyconnect connect.ucdmc.ucdavis.edu
```

Since this is a `sudo` command, you'll first have to enter your computer's
password. OpenConnect will then prompt you for your UCDH AD account username
and password. Recall that your username must be prefixed with `hs\` (for
example, my username is `wbrooks`, but I log into the VPN with `hs\wbrooks`).
As with the AnyConnect client, you'll also be prompted to complete Duo
two-factor authentication.

You can close the connection and OpenConnect by pressing `Ctrl`-`c`.
:::
