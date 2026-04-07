# Initial Setup

After [installing StartOS](installing-startos.md), follow these steps to initialize your server, set a master password, and download your Root CA.

## Watch The Video

<div class="yt-video" data-id="S5v0LW3BNj4" data-title="Initial Setup"></div>


1. Connect your server to power and Ethernet.

1. From a computer connected to the same Local Area Network (LAN) as your server, open a browser and visit [http://start.local](http://start.local).

1. Select a setup option:
   - **Start fresh**: Select this option if you are setting up a new server.

   - **Restore from Backup**: Select this option _only_ if your existing StartOS data drive has been lost or corrupted. This is for disaster recovery only.

   - **Transfer**: Select this option if you are transferring your existing data from one drive to another.

1. Set a strong master password. _Make it good. Write it down_. Resetting your password is non-trivial, but your data will be preserved.

1. Set your [server name](server-name.md). Your server's [mDNS address](mdns.md) is derived from this name.

1. Following successful initialization, you will be prompted to download a `StartOS-info.html`. This file contains your server's mDNS address and Root Certificate Authority (Root CA). It is recommended to save this file for future reference.

1. Click "Continue to Login" and follow instructions for [Trusting your Root CA](./trust-ca.md)
