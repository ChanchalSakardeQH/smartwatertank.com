# Hosting smartwatertank.com on GitHub Pages with a Hostycare Domain

Nov 6, 2026 · @Chanchal

## Overview

The landing page lives in a GitHub repository and is served free by GitHub Pages. The domain stays registered at Hostycare, and Hostycare's DNS points it at GitHub. No hosting plan is needed.

When a visitor opens `smartwatertank.com`, their browser asks DNS for the address. Hostycare's nameservers answer with GitHub's IPs. GitHub sees the domain name, matches it to the repo's custom domain, and serves the page with an HTTPS certificate.

| Item | Value |
| --- | --- |
| Domain | `smartwatertank.com` |
| Registrar and DNS | Hostycare (nameservers `ns50`–`ns53.hostycare.in`) |
| GitHub user | `ChanchalSakardeQH` (lowercase in URLs: `chanchalsakardeqh`) |
| Repository | `smartwatertank.com` |
| GitHub test URL | `https://chanchalsakardeqh.github.io/smartwatertank.com/` |
| Final URLs | `https://smartwatertank.com` and `https://www.smartwatertank.com` |
| GitHub Pages IPs | 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 |

Hostycare is only the company that sold the domain. Never enter `hostycare.com` anywhere in GitHub; always use your own domain.

## Prerequisites

- A domain bought at Hostycare, using Hostycare's own nameservers (the default).
- A GitHub account. A free account works for a public repository.
- The landing page files, with the home page named `index.html`.
- Windows Command Prompt (CMD) for the DNS checks with `nslookup`.

## Step 1 – Prepare the GitHub repository

1. On GitHub, create a public repository. The name can be anything; this setup uses `smartwatertank.com`.
2. Open the repository and click **Add file → Upload files**.
3. Drag in the landing page files. `index.html` must sit in the repository root.
4. Click **Commit changes**.

File tips:

- Use relative paths for images, CSS and scripts, such as `images/logo.png`. A leading slash (`/images/logo.png`) breaks the page on the github.io test URL.
- Add an empty file named `.nojekyll` in the root. It tells GitHub to publish the files as they are, without Jekyll processing.
- File names are case-sensitive on GitHub: `Logo.png` and `logo.png` are different files.
