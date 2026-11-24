# KITCULT

Custom sportswear designer: kitcult.club

Static site: `index.html` (no build step). Hosted on Vercel, code on GitHub.

## Deploy (first time)
1. **GitHub**: create a new repository called `kitcult` → *uploading an existing file* → drag in ALL files from this folder (`index.html`, `favicon.svg`, `vercel.json`, `README.md`, `.gitignore`) → *Commit changes*.
   (Hidden `.gitignore` may not show on Mac; it's optional.)
2. **Vercel**: vercel.com → *Add New → Project* → *Import* the `kitcult` repo → Framework preset: **Other** → leave build settings empty → **Deploy**.
   You get a link like `kitcult.vercel.app`.
3. **Domain**: Vercel project → *Settings → Domains* → add `kitcult.club` (and `www.kitcult.club`).
   Vercel shows the DNS records. In **Namecheap** → *Domain List → kitcult.club → Manage → Advanced DNS*:
   - `A` record, Host `@`, Value `76.76.21.21`
   - `CNAME` record, Host `www`, Value `cname.vercel-dns.com`
   (Use whatever Vercel shows if it's different.) Delete Namecheap's default parking records. HTTPS turns on automatically.

## Updating the site
Edit `index.html` on GitHub (pencil icon) → *Commit* → Vercel redeploys automatically in ~30 seconds.

## Edit your details
Search `const SHOP` in `index.html`:
```js
const SHOP = { name:'KITCULT', email:'orders@kitcult.club', instagram:'@kitcult', line:'@kitcult' };
```
Replace with your real email / Instagram / LINE.

## Prices
Search `const PRICE` in `index.html`:
```js
const PRICE = { single:59, team:45, teamMin:10, removeLogo:12, premiumFont:5 };
```
Free vs premium fonts: `premium:true` in `const STYLES`.

## Roadmap
- Orders saved to a database (Supabase) + email notification
- Online payment (Stripe / Omise / 2C2P)
- Customer accounts, public design gallery, creator payouts, gym stores
