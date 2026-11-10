# Portfolio site (static, no server needed)

Files: index.html (site), admin/index.html (dashboard), data/content.json (all your content), uploads/ (PDFs and images).
Lists are ordered by year. Change oldest-first or newest-first in the dashboard under Profile.

## 1. Put it on GitHub
1. Create a GitHub repository (e.g. `portfolio`). Upload everything in this folder, including `.nojekyll`.

## 2A. GitHub Pages (free)
Repo Settings > Pages > Deploy from branch > main, folder / (root).
Custom domain: in the same page enter your domain, tick Enforce HTTPS. At your domain registrar add:
- A records for the root domain: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
- CNAME record: `www` pointing to `YOUR-USERNAME.github.io`
GitHub then creates a file named CNAME in the repo. Keep it.

## 2B. Netlify (free)
Add new site > Import from Git > pick the repo (no build command, publish directory `.`). Do NOT use drag-and-drop, or dashboard saves will not publish.
Then Domain management > Add a domain and follow its DNS instructions.

## 3. Dashboard (yourdomain/admin/)
1. GitHub > Settings > Developer settings > Fine-grained tokens > new token. Choose only this repository, permission Contents: Read and write.
2. Open /admin/, expand Connect GitHub, enter username, repository, branch and the token.
3. Add, edit or delete entries, upload PDFs, press Save changes. The site rebuilds in 1 to 2 minutes.
The token stays in that browser only. Use the dashboard on your own device and press "Forget token" afterwards on shared ones.
Deleting an entry does not delete an uploaded file from `uploads/`; remove it in GitHub if needed.
Test locally with: python3 -m http.server (then open http://localhost:8000).
