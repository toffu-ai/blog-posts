---
source: local
title: "Toffu Now Works in Your Own Chrome"
description: "Client portals, Looker Studio, dashboards with no integration: Toffu can now open them in a Toffu tab of your own Chrome, with your logins, while you watch."
date: "2026-11-10"
image: "https://raw.githubusercontent.com/toffu-ai/blog-posts/main/images/toffu-in-your-own-chrome-hero.png"
slug: "toffu-in-your-own-chrome"
---

*Client portals, Looker Studio, dashboards with no integration: Toffu can now open them in a Toffu tab of your own Chrome, with your logins, while you watch.*

---

Every agency has the same gap. Google Ads, Meta and GA4 are connected, so Toffu can read them and act on them. But a good part of the work still sits behind a login with no API: the client's reporting portal, a Looker Studio report someone else built, a partner dashboard, an affiliate network, the client's own back office.

Until now, that part ended with "export it as a CSV and upload it here." This week we close that gap.

## Two browsers, one request

Toffu can now work in a browser in two ways.

**Toffu's browser** runs in the cloud. You see it in a panel next to the chat. When a step needs you, like a login or a 2FA code, Toffu stops and you do that step in the panel. The login is then saved for you, so the next task, and every scheduled run, starts already logged in.

**Your own Chrome** is new. Install the Toffu Chrome extension, and Toffu can work in a tab of the Chrome you already use: same logins, same sessions, same office network. That matters for the sites that do not trust a new browser: a portal that sends a code to your phone on every new device, a tool that only opens from your office network, or a dashboard on your own computer.

You choose with one phrase. Ask as usual, and add "use my own Chrome":

```
Use my own Chrome. Open the client portal, read October's leads by campaign, and compare them with what Google Ads reports for the same campaigns.
```

## One tab, and you see every click

Giving an AI agent your browser should not mean giving it your browser. So the extension works in one tab only: the tab of a purple **Toffu** tab group. If there is no such tab, the extension opens one. Your email, your other clients and every other tab stay out of reach. To hand Toffu a page you already have open, drag that tab into the group.

![Toffu working in the Toffu tab of your own Chrome](https://raw.githubusercontent.com/toffu-ai/blog-posts/main/images/toffu-in-your-own-chrome-tab.png)

While Toffu works, you see it:

- A purple cursor moves to each button and field before Toffu clicks or types.
- Chrome shows a bar that says Toffu is working in the browser. **Cancel** on that bar stops Toffu at once.

Toffu never types a password. When it reaches a login, a code or a captcha, it asks you in the chat, you do that step in the Toffu tab, and Toffu continues from there.

![The chat asks you to do a step in the Toffu tab](https://raw.githubusercontent.com/toffu-ai/blog-posts/main/images/toffu-in-your-own-chrome-takeover.png)

The extension does not read your cookies, saved passwords, history or other tabs. It refuses every browser command except the five it needs to read a page and operate it. The [privacy policy](https://toffu.ai/privacy#chrome-extension) lists exactly what it reads and how long anything is kept.

## Which one to use

Use **Toffu's browser** for tasks that should run when you are not there, like a weekly pull from a client portal on a schedule. Log in once, and Toffu keeps the login.

Use **your own Chrome** when the site needs your own session or your own computer, or when you want to watch the work happen in front of you.

## Get started

The browser is part of the **Browser** add-on. On an agency account, an admin of the agency turns it on once in [AI Settings → Browser logins](https://toffu.ai/ai-settings/browser-logins), and it then works in every client workspace.

For your own Chrome, install the [Toffu extension](CHROME_WEB_STORE_URL) and sign in to [toffu.ai](https://toffu.ai) in the same Chrome. It connects by itself.

Setup, takeovers, saved logins and troubleshooting are in the [Browser guide](https://toffu.ai/academy/browser).
