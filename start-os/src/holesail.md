# Holesail

[Holesail](https://docs.holesail.io/) creates direct, encrypted peer-to-peer tunnels between your devices and your server. No port forwarding, static IP, or centralized servers are required. Traffic flows directly between peers as if they were on the same local network. This is a good option when:

1. You want fast, private remote access without the complexity of setting up a VPN server.
1. You don't have control over your network (e.g. work, school, shared housing) and cannot configure port forwarding.
1. You want a simple, zero-configuration alternative to Tor that offers better performance.

## Setting Up Holesail

Holesail is not included in StartOS by default. To use Holesail, you must install the **Holesail** service from the marketplace.

1. Go to the Marketplace and install the **Holesail** service.

1. Start the Holesail service and wait for it to become healthy.

## Managing Tunnels

Once Holesail is installed and running, you can create tunnels for specific service interfaces on your server.

1. Open the Holesail service and go to **Actions > Manage Tunnels**.

1. Select a service interface to create a tunnel for. Each tunnel produces a unique connection key.

1. To view your tunnel connection keys, go to **Actions > View Tunnels**.

> [!NOTE]
> Anyone with the connection key can access the tunnel. Treat connection keys like passwords — only share them with trusted devices.

## Connecting over Holesail

> [!WARNING]
> Holesail tunnels only work when your client device is **not** on the same LAN as your server. If you are connected to the same local network, the tunnel will fail due to loopback. To test a tunnel from home, disconnect your phone or laptop from WiFi and use mobile data instead.

To connect to a Holesail tunnel from a client device, install the [Holesail client](https://docs.holesail.io/) and use the connection key provided by your server.

**CLI example:**

```
holesail --connect <connection-key> --host 127.0.0.1 --port 16972
```

**GUI clients** will have fields for "Host" and "Port". Enter the same values.

> [!WARNING]
> The **host** and **port** are where the Holesail client listens _on your local device_ — they are **not** the host and port of the service on your server. Holesail handles the remote connection automatically using the connection key.
>
> - **Host** should always be `127.0.0.1` (localhost).
> - **Port** should be any unused port on your device in the range 1024–65535 (e.g. `16972`). Pick any number you like — it just needs to be free on your machine.

Once the client is running, open your app or browser and point it at `127.0.0.1:<port>` (e.g. `127.0.0.1:16972`) to access the service.
