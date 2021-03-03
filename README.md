# UnboundBL 🛑

Block ads, malware, tracking, mining + more on OPNsense with UnboundBL & Unbound DNS.

![UnboundBL](https://i.imgur.com/zvKpPDk.png)

UnboundBL goes hand-in-hand with Unbound DNS to blackhole undesired content. By generating a .conf file for Unbound in realtime, it allows you to easily submit, convert & manage blacklist URL's. It's not quite at the pfBlocker level, but it's getting there! 😅

I will try to fix as many as possible but I am not really a coder, so yeah we will see.

### Current Features

- Add, download and parse blocklist URLs.
- Add unlimited whitelist entries in domain format (eg. `www.malware-server.net`) which will be ignored from any blocklist you parse.
- One-click refresh and rebuild.

### Planned Features

- Cron-job management.
- Advanced error reporting.
- Preset blacklists for easy setup.
- Advanced blacklist management.
- Regex builder for whitelist.
- Pixelserv (NGINX) to replace 0.0.0.0.

### Installing

Obviously, this is all done with the `Shell` mode via SSH.
Do all these steps below in this order.

```
opnsense-code tools plugins
cd /usr/plugins/dns
git clone https://github.com/alectrocute/UnboundBL.git
cd UnboundBL
make package
pkg add work/pkg/*.txz
chmod +x /usr/local/opnsense/scripts/OPNsense/Unboundbl/*.sh
```

Thanks at koenvervloesem for the hint, see https://github.com/alectrocute/UnboundBL/issues/6

### Removing

`8) Shell` mode via SSH, or web-based package manager, I suppose.

`$ pkg remove os-UnboundBL-devel-1.0`

#### Currently at version: `devel-1.0` on March 12, 2019

Special thanks to [Devin Ortner](https://devinstechblog.com/block-ads-with-dns-in-opnsense/) for his awesome blog post, which helped kickstart this project. OPNsense contributor @mimugmail for his awesome critique and help. And of course, the Unbound DNS & OPNsense team. You guys are 'da real MVPs.
