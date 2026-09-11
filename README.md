# EPF Dashboard — Tool Directory

A single static `index.html` — the front door at epf-dashboard.online. Each
card links straight to a subdomain (or an off-site domain for apps like
epf-admin-dashboard that live elsewhere).

No backend, no build step, no database.

## Add a new tool

Open `index.html`, find the `TOOLS` array near the bottom, and add an entry:

```js
{
  tag: "New",
  name: "Your Tool Name",
  description: "One short line about what it does.",
  url: "https://your-subdomain.epf-dashboard.online",
}
```

Add `offsite: true` if the tool lives on a different domain (like
epf-dashboard.xyz) rather than an epf-dashboard.online subdomain — that just
swaps the top accent bar from red to navy so off-site links read differently
at a glance.

## Deploy on Coolify

This is a static site, so it's simpler than the Flask apps:

1. Push this folder to a new repo, e.g. `EPFRAGHU/epf-dashboard-hub`.
2. In Coolify: **New Resource → Public Repository**, point at that repo.
3. Build pack: choose **Static** (or **Nixpacks** — it also serves a bare
   `index.html` fine via a static file server; no `requirements.txt` or
   `Procfile` needed either way).
4. Domain: set this one to the **root** domain, `epf-dashboard.online`
   (not a subdomain) — that's what makes it the front door.
5. Deploy.
