# README.md

This repository contains the static files for the Ziv Holdings (Pty) Ltd verification website.

## Deployment Steps

1. Create a GitHub account at https://github.com if you don't have one.
2. Go to https://github.com/new and create a new repository. Name it `zivholdings` (or any name; it doesn't affect the custom domain).
3. Clone the repository to your local machine using Git: `git clone https://github.com/YOUR_USERNAME/zivholdings.git` (replace YOUR_USERNAME with your GitHub username).
4. Add the `index.html` and `style.css` files to the repository root.
5. Commit and push: `git add .`, `git commit -m "Initial commit"`, `git push origin main`.
6. Go to the repository on GitHub > Settings > Pages (under "Code and automation").
7. Under "Source", select "Deploy from a branch", choose "main" (or your default branch), and "/ (root)", then click "Save".
8. Under "Custom domain", enter `zivholdings.com` and click "Save". GitHub will check DNS and enforce HTTPS (this may take a few minutes; if it fails, check DNS setup below).
9. Wait for the site to deploy (usually instant). The temporary URL is https://YOUR_USERNAME.github.io/zivholdings/ but use the custom domain once DNS propagates.

## DNS Records for Namecheap

1. Log in to Namecheap at https://www.namecheap.com/myaccount/login/.
2. Go to "Domain List" > Click "Manage" next to zivholdings.com.
3. Go to the "Advanced DNS" tab.
4. Delete any existing A, AAAA, or CNAME records for @ and www to avoid conflicts.
5. Add these exact records (from GitHub's official IPs; verify at https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#dns-records-for-your-custom-domain if they change):

   - Type: A, Host: @, Value: 185.199.108.153, TTL: Automatic
   - Type: A, Host: @, Value: 185.199.109.153, TTL: Automatic
   - Type: A, Host: @, Value: 185.199.110.153, TTL: Automatic
   - Type: A, Host: @, Value: 185.199.111.153, TTL: Automatic
   - Type: AAAA, Host: @, Value: 2606:50c0:8000::153, TTL: Automatic
   - Type: AAAA, Host: @, Value: 2606:50c0:8001::153, TTL: Automatic
   - Type: AAAA, Host: @, Value: 2606:50c0:8002::153, TTL: Automatic
   - Type: AAAA, Host: @, Value: 2606:50c0:8003::153, TTL: Automatic
   - (Optional for www subdomain) Type: CNAME, Host: www, Value: YOUR_USERNAME.github.io., TTL: Automatic (note the trailing dot)

6. Save changes. DNS propagation can take 30 minutes to 48 hours, but often faster.

## Confirm Site is Live

1. After DNS updates, visit https://zivholdings.com in a browser.
2. Clear browser cache or use incognito mode if needed.
3. Check for HTTPS lock icon (GitHub enforces it).
4. Verify no errors: Page loads fully, no broken links, all text visible.
5. Use tools like https://www.whatsmydns.net to check if A/AAAA records propagated globally.
6. In GitHub Pages settings, the custom domain should show a green checkmark once verified.

This setup uses GitHub Pages (free), meets all constraints, and ensures the site is static, simple, and compliant.