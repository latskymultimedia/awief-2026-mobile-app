# AWIEF 2026 conference app (PWA)
Static site: host the folder on Cloudflare Pages / Netlify / GitHub Pages (HTTPS required).

**Update content:** edit `schedule.json` (times, TBA panels) and `announcements.json` (in-app updates). Bump `C='awief-v1'` in `sw.js` when you change app files.
**Map:** drop the CTICC floor plan in as `map.jpg`; it appears on the Info tab.
**Push:** create an OneSignal web app, paste the App ID into `CFG.onesignal` in index.html. iPhone users must add the app to their Home Screen first.
**Photo wall (Supabase):** create a public Storage bucket `moments`, and a table `moments(id, path text, approved bool default false, created_at timestamptz default now())`. Allow anon INSERT on the table and the bucket, anon SELECT only where approved = true. Approve photos in the Supabase table editor. Paste URL + anon key into `CFG`.
**Analytics:** add a Plausible/Umami script tag where marked in index.html.
