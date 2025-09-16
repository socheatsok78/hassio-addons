# Newt

Newt is a fully user space [WireGuard](https://www.wireguard.com/) tunnel client and TCP/UDP proxy, designed to securely expose private resources controlled by Pangolin. By using Newt, you don't need to manage complex WireGuard tunnels and NATing.

https://github.com/fosrl/

## Expose Home Assistant via Pangolin Newt:

Home Assistant, by default, blocks requests from reverse proxies, like the Pangolin Resources.

To enable it, add the following lines to your `configuration.yaml`, without changing anything:

```yaml
http:
    use_x_forwarded_for: true
    trusted_proxies:
    - 127.0.0.1
```

Once done, restart Home Assistant. 

You should be able to create the resource in Pangolin Dashboard and access your Home Assistant from the created resource URL.

[http_integration]: https://www.home-assistant.io/integrations/http/
