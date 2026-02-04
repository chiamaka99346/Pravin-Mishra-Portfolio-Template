# DMI Portfolio Website (Static HTML/CSS)

This repository contains a clean, professional-looking **static portfolio website** used in **DevOps Micro Internship (DMI)** Week 1 to practice:
- Linux basics
- Nginx hosting
- Deployment proof / ownership
- Production-style checks

✅ Students deploy this website on an Ubuntu VM using Nginx and keep it live for 24 hours.

---

## Who is this for?
- DMI students (beginner → intermediate)
- Anyone learning how to host a static site with Nginx on Linux

---

## What you will build
A portfolio-style website hosted on:
- **Ubuntu VM**
- **Nginx**
- Accessible via: `http://<public-ip>`

---

## Mandatory Ownership Proof (DMI Rule)
Before you deploy, you MUST edit the footer and add your details:

Original:

```html
<p>Crafted with <span>cloud</span> excellence by Pravin Mishra</p>
```

Add this line (example):

```html
<p><strong>Deployed by:</strong> DMI Cohort 2 | Rahul Sharma | Group 4 | Week 1 | 16-01-2026</p>
```

✅ This proof must be visible in your browser screenshot submission.

---

## Footer requirement ✅

- **Add a visible "Deployed by" line** in the footer using this format:
  `Deployed by: <Cohort> | <Your Name> | <Group> | <Week> | <DD-MMM-YYYY>` (example: `DMI Cohort 2 | Rahul Sharma | Group 4 | Week 1 | 16-Feb-2026`).
- Place this line near the bottom of the footer so it is included in your deployment screenshot.
- **Keep** the existing `Crafted with <span>cloud</span> excellence by ...` line — do not remove it.
- If you want the date to be filled automatically, include a `<span id="deployDate"></span>` where you want the date to appear.

## How date is generated 🕒

- The site uses a small inline script to set the deploy date automatically. Current implementation sets the date in **YYYY-MM-DD** (ISO) format, for example `2026-02-03`:

```html
<script>
  const d = new Date();
  const formattedDate = d.toISOString().split('T')[0]; // YYYY-MM-DD
  document.getElementById("deployDate").textContent = formattedDate;
  // Optionally set the © year automatically:
  // document.getElementById("year").textContent = d.getFullYear();
</script>
```

- If you prefer `DD-MMM-YYYY` (e.g., `03-Feb-2026`), replace the formatting line with:

```js
const months = ["Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"];
const formattedDate = `${String(d.getDate()).padStart(2,'0')}-${months[d.getMonth()]}-${d.getFullYear()}`;
```

- Make sure to commit your footer changes and include a screenshot that clearly shows the `Deployed by` line and date when you submit.
