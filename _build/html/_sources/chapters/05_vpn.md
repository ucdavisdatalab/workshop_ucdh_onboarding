(chapter:vpn)=
# VPN Access
In order access services that are hosted on UCDH premises, you must make a secure connection via the UCDH VPN. There is an official [UCDH help page for the VPN](https://health.ucdavis.edu/remote-access/vpn/download-and-install-vpn), which smoe people may prefer. This chapter is meant to be very practical, so it may leave leave "why"-type questions unanswered.

## Getting Authorization for the VPN
Remember that to get new powers on the UCDH IT system, you need to "order" them through the Service Now catalog (see the previous chapter.) This is how to get your account authorized for the VPN. Search the service now catalog for "VPN" and order the item called "Remote Access - VPN - External Employee".

## Install the Client Software
You need a program on your computer that can create the connection to the UCDH VPN. The officially supported VPN client is Cisco AnyConnect, but you can also use OpenConnect on a computer that uses the Mac or Linux operating systems. I use OpenConnect and find it more reliable than the official Cisco client, but your mileage may vary. Install the AnyConnect client by following the instructions at [https://health.ucdavis.edu/remote-access/vpn/download-and-install-vpn](https://health.ucdavis.edu/remote-access/vpn/download-and-install-vpn). Installing `openconnect` is slightly more advanced because you have to use your computer's package manager (use [`brew`](https://brew.sh) or [`pixi`](https://pixi.sh) on a Mac.)

## Connecting
The address for VPN login is `connect.ucdmc.ucdavis.edu`. Type this into the Cisco AnyConnect client and click `Connect`, or the command for connecting to the VPN via OpenConnect is the following:

```
sudo openconnect --protocol=anyconnect connect.ucdmc.ucdavis.edu
```

Since this is a `sudo` command, you wil first have to enter your computer's password. Then you must enter your UCDH login credentials (which is generally different than your UCD login credentials.) The username must be prefaced by `hs\`, so even though my username is `wbrooks`, I log into the VPN with username `hs\wbrooks`. Then enter your UCDH password at the next prompt (remember that this wis different from your UCD main campus passowrd if you have one.) Finally, complete a Duo two-actor authentication in order to join the VPN. Now all of your computer's network traffic will be routed through UCDH as long as the connection is open.

The VPN connection generally stays open until one of three things happens:
1. You close the connection by clicking "Disconnect" in Cisco AnyConnect or typing Ctrl-C into the terminal window where you started OpenConnect.
2. You close the Cisco AnyConnect app or close the terminal window from which you started OpenConnect.
3. Your computer goes to sleep or turns off.

As long as you are connected to the UCDH VPN, all of your computer's network traffic is routed through UCDH on a connection that is encrypted between you and UCDH. This adds stops between your computer and the Internet, so you may notice that data is a bit slower (this often affects my Zoom calls, for instance.)


