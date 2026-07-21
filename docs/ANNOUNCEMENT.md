# Community announcement — draft

Drop-in post for **forum.howtoforge.com** (ISPConfig → Tips/Tutorials or
Contributions). It is written in Markdown; the forum uses BBCode, so convert
headings to `[b]…[/b]`, links to `[url=…]…[/url]`, and images to `[img]…[/img]`
when posting. Images to attach are listed at the end.

Keep the framing in the first two paragraphs intact — it is what positions this
as *building on* ISPConfig, not competing with it.

---

## Clarity + Customizer — a modern dark theme and a white-label branding module for ISPConfig (open source, no core changes)

Hi everyone,

I've been running ISPConfig in production and wanted it to look and feel like a
first-class modern control panel — and to let me hand a cleanly branded panel to
clients — **without ever patching the core.** That turned into two small
open-source projects I'd like to share with the community:

- **Clarity** — a complete dark (and light) theme: a navy sidebar rail, a
  redesigned login screen, a restructured dashboard with proper stat cards and
  themed charts, and Clarity/CDS-style iconography.
- **Customizer** — a standalone branding module: set your logo, panel name,
  accent colours, login screen and a few visibility toggles from an admin page
  inside ISPConfig. It runs on **stock ISPConfig** too; a brand-aware theme
  (like Clarity) applies the colours.

**Both are built to be good citizens of the ISPConfig ecosystem.** Everything
lives in theme and module directories only — **no core file is ever modified**,
so both survive `ispconfig_update.sh` and panel upgrades. Every setting is
stored in ISPConfig's own `sys_ini` table (so it also pushes across a fleet via
the remote API). The "powered by ISPConfig" credit is **shown by default**, the
admin update notice and version info are left untouched, and the donate dashlet
is left in place. The goal is to make ISPConfig an easier "yes" for people who'd
otherwise reach for Plesk/cPanel — and send them to ISPConfig's own support and
paid modules, not away from them.

### Screenshots

![Login](https://raw.githubusercontent.com/wadejbeckett/clarity-theme-ispconfig/main/mockup/shots/dark-login-desktop.png)

![Dashboard](https://raw.githubusercontent.com/wadejbeckett/clarity-theme-ispconfig/main/mockup/shots/dark-dashboard-desktop.png)

*(Light mode and the branding page are attached below.)*

### What Clarity (the theme) gives you

- Dark canon + a light mode, toggled in the top bar and remembered per browser.
- A redesigned login screen and a dashboard that leads with system status
  (live load / memory / network) instead of a wall of launcher tiles.
- Charts themed to match (gradient fills, hover tooltips), in both modes.
- Clarity-style icons, keyboard search (Ctrl/⌘-K), a mobile drawer, and a11y
  fixes for the stock markup.
- Self-contained: it only borrows the stock theme's vendor CSS/JS; it never
  edits them.

### What Customizer (the module) gives you

- **Logo** — upload SVG/PNG/JPEG/GIF/WebP (validated), or reference a file by
  path/URL. Shows on the sidebar, mobile header and login.
- **Panel name, accent / sidebar / login colours, login footnote.**
- **Visibility toggles** — optionally hide the footer credits, the dashboard
  news feed, and the Help version line (handy for clean client demos). The
  open-source **licence notices are always kept** — the toggles only hide
  optional courtesy text, never a licence file.
- Stored in `sys_ini`, so it survives updates and is pushable via the remote
  API. Clean uninstaller included.

### Install

Theme:
```bash
git clone https://github.com/wadejbeckett/clarity-theme-ispconfig.git
cd clarity-theme-ispconfig && sudo ./install.sh --copy
# then set $conf['theme'] = 'clarity'; in interface/lib and server/lib config.inc.php
```

Customizer:
```bash
git clone https://github.com/wadejbeckett/ispconfig-customizer.git
cd ispconfig-customizer && sudo ./install.sh --copy
# log out/in; open the "Branding" module in the top nav
```

Or grab both together via the umbrella repo (git submodules):
`git clone --recurse-submodules https://github.com/wadejbeckett/ispconfig-toolkit.git`

### Compatibility

- ISPConfig **3.2 / 3.3** — developed and verified against **3.3.1p1**.
- PHP 8.x (tested on 8.2).
- The theme pins the ISPConfig version it was built against and re-stamps on
  install; re-run the installer after a major panel upgrade. Both ship a clean
  `uninstall.sh` that restores stock.

### Licence & attribution

Both are **MIT** (© Wade John Beckett). Not affiliated with or endorsed by the
ISPConfig project (BSD-3-Clause) or VMware (the Clarity design system);
disclaimers are in each README. UI available in English and German so far, with
more European languages landing.

### Feedback wanted

This is offered back to the community free and open. I'd genuinely value
review, bug reports, and translation help — and I'm keeping a short list of
small **core** patches I found along the way (a couple of long-standing panel
papercuts) that I'd like to offer upstream as merge requests if the maintainers
are open to them.

Repos:
- Theme — https://github.com/wadejbeckett/clarity-theme-ispconfig
- Customizer — https://github.com/wadejbeckett/ispconfig-customizer
- Toolkit (both) — https://github.com/wadejbeckett/ispconfig-toolkit

Thanks — and thanks to Till and the team for ISPConfig.

---

### Images to attach

| File | Caption |
|---|---|
| `clarity-theme-ispconfig/mockup/shots/dark-login-desktop.png` | Login — dark |
| `clarity-theme-ispconfig/mockup/shots/light-login-desktop.png` | Login — light |
| `clarity-theme-ispconfig/mockup/shots/dark-dashboard-desktop.png` | Dashboard — dark |
| `clarity-theme-ispconfig/mockup/shots/light-dashboard-desktop.png` | Dashboard — light |
| A screenshot of the **Branding** admin page | The Customizer module |

### Pre-post checklist

- [ ] Attach the branding-page screenshot (capture from a live panel).
- [ ] Confirm the raw.githubusercontent image URLs render in a forum preview
      (use `raw.githubusercontent.com/.../main/...`, not `github.com/.../raw/...`).
- [ ] Post from the project account; link the repos, not the live panel.
- [ ] Optional: open a separate, humble thread offering the upstream core
      patches, rather than bundling them into the announcement.
