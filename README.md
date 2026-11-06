# Program Believe – Backup Website

A standby site hosted free on GitHub Pages: https://program-believe.github.io/program-believe-backup/

## Automatic failover
The **Automatic failover** task (Actions tab) checks https://program-believe.base44.app every 5 minutes.
- If the main site fails 3 checks in a row, it points **program-believe.org** and **www.program-believe.org** at this backup site.
- When the main site passes 3 checks in a row again, it points the domain back to Base44.

It only works once the domain's DNS is on Cloudflare and these two repository secrets exist
(Settings → Secrets and variables → Actions):
- `CLOUDFLARE_API_TOKEN` – a Cloudflare API token with "Zone → DNS → Edit" for program-believe.org
- `CLOUDFLARE_ZONE_ID` – shown on the program-believe.org overview page in Cloudflare

In Cloudflare, set SSL/TLS mode to **Full** so the backup loads over https.

You can also run it by hand: Actions → Automatic failover → Run workflow.

Donations go straight to Stripe (https://donate.stripe.com/eVq8wQ5Yt67T5Yp5u6eME08), so they work even when Base44 is down.
