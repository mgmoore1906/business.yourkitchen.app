YOURKITCHEN — B2B DEMO SITE
============================================

WHAT THIS IS
  A password-gated 4-page demo site:
    index.html       Overview + audience selector
    faith.html       Faith Community track  (Pool Console demo)
    payer.html       Payer & MCO track      (ROI brief + Enterprise + Member Detail demos)
    enterprise.html  Enterprise track       (Enterprise + Member Detail demos)
  Each page is fully self-contained — demos are embedded, no external files needed.

ACCESS CODE
  Default: covered2026
  Enter once per browser session; it carries across all pages.

  TO CHANGE THE PASSWORD:
    1. Pick a new password.
    2. Generate its SHA-256 hash, e.g. in a terminal:
         echo -n "yourNewPassword" | shasum -a 256
       (or any online SHA-256 tool)
    3. In EACH .html file, find:  var HASH="..."
       Replace the hash string with your new one. Done.

DEPLOY — RECOMMENDED (subdomain, professional)
  1. Create a new GitHub repo, e.g. yourkitchen-business.
  2. Add these 4 .html files.
  3. Enable GitHub Pages (Settings > Pages > main branch).
  4. Add a file named CNAME containing:  business.yourkitchen.app
  5. In your DNS, add a CNAME record:
       business  ->  <your-github-username>.github.io
  6. Live at https://business.yourkitchen.app

DEPLOY — FASTER (path on your existing landing site)
  Drop these files in a /business folder in your yourkitchen (landing) repo.
  Live at https://yourkitchen.app/business/

PASSWORD SECURITY — READ THIS
  The built-in gate is CLIENT-SIDE. It stops casual visitors, and the password
  is stored only as a hash (not plaintext) — but a determined person could bypass
  a client-side gate because the page content ships in the browser.

  For REAL protection on sensitive pricing/ROI content, put the site behind one of:
    - CLOUDFLARE ACCESS (best if your DNS is on Cloudflare): free for small teams,
      zero code, real email/OTP or password gate in front of the subdomain.
    - VERCEL: host the site as a Vercel project and enable password protection /
      middleware basic-auth (same pattern as your app).
  Use the built-in gate now to start sharing; harden with one of the above before
  sending links widely.

NOTE
  All numbers in the demos are illustrative sample data, not real customer records.
