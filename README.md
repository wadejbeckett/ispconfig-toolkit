# ISPConfig Toolkit

A curated collection of modules, themes, and tools for the
[ISPConfig](https://www.ispconfig.org/) hosting control panel. Every module
lives in its own repository (own issues, own releases) and is pinned here as a
git submodule, so this repo is both the index and a one-command checkout of
the whole toolkit.

## Modules

| Module | What it is | Status |
|---|---|---|
| [clarity-theme-ispconfig](https://github.com/wadejbeckett/clarity-theme-ispconfig) | A complete dark theme for the panel, built on VMware Clarity design tokens — navy rail, dark/light switcher, Clarity icons, redesigned login. No core modifications; survives panel updates. | v2.0, stable |
| [ispconfig-customizer](https://github.com/wadejbeckett/ispconfig-customizer) | A standalone white-label / branding module — set your logo, panel name, accent colours and login screen from an admin page. Runs on stock ISPConfig; a brand-aware theme (like Clarity) applies the colours. No core modifications. | new |

[![Clarity Theme for ISPConfig dashboard](https://raw.githubusercontent.com/wadejbeckett/clarity-theme-ispconfig/main/mockup/shots/dark-dashboard-desktop.png)](https://github.com/wadejbeckett/clarity-theme-ispconfig)

More modules are planned. Have something you wish ISPConfig did better?
[Open an idea](../../issues/new) here.

## Get everything

```bash
git clone --recurse-submodules https://github.com/wadejbeckett/ispconfig-toolkit.git
```

Or grab a single module from its own repository — each one installs
independently and documents its own setup.

## Contributing

- **Bugs and PRs for a module** go to that module's repository (each has
  issue templates and a contributing guide).
- **Ideas for new modules** and toolkit-wide suggestions belong here.

## Support this project

The toolkit is free and open source. If it saves you time and you'd like to
say thanks, donations are taken in Monero:

```text
44BtMn9izxH8mK2yFbSdY6Di7TNobkLbnHdZ6gZQjukCME5vsNhtPRtH4TcVkDHKHLhSpAJbsjv8gCdYuSZVMpXgMkUC1hV
```

### Support ISPConfig itself

None of this exists without ISPConfig. The project takes no direct donations;
the way its developers ask to be supported is:

- **Buy the [ISPConfig manual](https://www.ispconfig.org/documentation/user-manual/)** (€5) or a
  [HowtoForge subscription](https://www.howtoforge.com/download-the-ispconfig-3-manual)
  that includes it — the project's own README names this as the way to fund
  development.
- Need paid help? [ISPConfig Business Support](https://www.ispconfig.org/get-support/)
  is run by the core team's official partner.
- Their commercial tools fund the free panel:
  [ISPProtect](https://www.ispprotect.com/) and the
  [Migration Tool](https://www.ispconfig.org/add-ons/ispconfig-migration-tool/).
- Contribute upstream: code and bug reports at
  [git.ispconfig.org](https://git.ispconfig.org/ispconfig/ispconfig3), help
  other users at the [HowtoForge forum](https://forum.howtoforge.com/).

## License

This index repository is [MIT](LICENSE)-licensed. Each module carries its own
license in its own repository. ISPConfig itself is BSD-licensed by its
authors.
