# tomerporian.com

Source for Tomer Porian's personal homepage: a single static page (`index.html` + `style.css`) with no JavaScript, build step or external dependencies. It reproduces the original Wix site.

## Preview locally
- Open `index.html` in a browser, or
- run `python3 -m http.server 8000` in this folder and visit http://localhost:8000

## Edit
- Bio text and links: edit the `<section class="about">` block in `index.html`.
- Add a publication: copy one `<p class="pub">…</p>` block inside `<section class="publications">`, paste it above the others (newest first), and change the title, links, authors and venue.
- Photo and icons live in `images/` (`photo.jpg` is the 482×508 web version; `photo-original.jpg` is the full-size original).
- Colors, fonts and spacing are set at the top of `style.css`.

## Deploy
Served by GitHub Pages from the public repo `Tomerporian/tomerporian.github.io` (Settings → Pages → Deploy from a branch: `main`, `/ (root)`). `.nojekyll` makes Pages serve the files unchanged.

Custom domain: `www.tomerporian.com`, set in Settings → Pages (GitHub then commits a `CNAME` file; `git pull` after). The bare `tomerporian.com` redirects to www.

DNS records (at whichever DNS host is authoritative):

| Type  | Host                                   | Value |
|-------|----------------------------------------|-------|
| A     | `@`                                    | 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 |
| AAAA  | `@` (optional)                         | 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, 2606:50c0:8003::153 |
| CNAME | `www`                                  | `tomerporian.github.io` |
| TXT   | `_github-pages-challenge-tomerporian`  | code from GitHub → Settings → Pages → verified domains (keep forever) |

No wildcard records. Keep "Enforce HTTPS" on.
