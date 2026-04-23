# Landing Page CTA — Quick Setup Checklist

**Status**: Code deployed ✅ | Email form needs 1-click setup ⚠️

---

## Immediate Actions (5 minutes)

### Step 1: Confirm Formspree Email
- [ ] Go to https://formspree.io/signup
- [ ] Sign up with `hishamalasker@gmail.com`
- [ ] Click confirmation link in email (Formspree sends it)
- [ ] Create project "Master Mind Landing"
- [ ] Copy form ID from dashboard
- [ ] **Status**: Forms now send emails to your inbox ✅

### Step 2: Verify Calendly
- [ ] Go to https://calendly.com/hishamalasker
- [ ] Confirm "15-min Setup Call" event exists
- [ ] Check availability hours (should match your timezone)
- [ ] Test booking by trying to schedule on your own account
- [ ] **Status**: Calendly ready for prospect bookings ✅

### Step 3: Test Both Paths
- [ ] Open landing page in browser: https://hishalasker.github.io/mastermind-landing/
- [ ] Click "Book a Walkthrough" → lands on #contact
- [ ] Click "Open Calendly" → opens booking widget
- [ ] Click "Send Message" → form appears
- [ ] Fill test form & submit
- [ ] Check email: Should see test submission at `hishamalasker@gmail.com`
- [ ] **Status**: Both conversion paths working ✅

---

## Calendly Setup (if starting fresh)

If you don't have a Calendly account:

- [ ] Go to https://calendly.com/signup
- [ ] Email: `hishamalasker@gmail.com`
- [ ] Create password
- [ ] Create event type:
  - [ ] Name: "15-min Setup Call" (or "Product Walkthrough")
  - [ ] Duration: 15 minutes
  - [ ] Meeting link: Zoom / Google Meet / your preferred platform
  - [ ] Availability: Set your actual working hours
  - [ ] Calendar: Connect Google Calendar or Outlook (auto-sync)
- [ ] Share link: https://calendly.com/hishamalasker/15min
- [ ] Test: Try booking on your own account
- [ ] **Status**: Ready ✅

---

## Email Flow (After Formspree Confirmation)

### Inbound
- **Email form** → Formspree → `hishamalasker@gmail.com` (plus Formspree dashboard)
- **Calendly booking** → Calendly → `hishamalasker@gmail.com` (calendar invite)

### Outbound (optional)
- [ ] Set auto-reply in Formspree (suggest: "Thanks for reaching out, we'll respond in 24 hours")
- [ ] Set auto-reply in Calendly (built in: "Your meeting is confirmed")
- [ ] Or route through CRM for auto-response

---

## Optional: Track Everything

### Google Analytics
- [ ] Add tracking code to landing page
- [ ] Create custom event: "cta_click"
- [ ] Create custom event: "form_submit"
- [ ] Weekly check dashboard

### Metrics Dashboard
- [ ] Formspree dashboard: Form submissions per week
- [ ] Calendly analytics: Bookings per week
- [ ] Email open rate: Check with `hishamalasker@gmail.com` email client
- [ ] Conversion funnel: Page views → CTA click → Email/Booking

---

## Optional: Enhance Response

### Auto-Reply Template (Formspree)
```
Subject: Thanks for reaching out

Hi [Name],

Thanks for your interest in Master Mind Core. We'll be in touch within 24 hours.

In the meantime, you can also book a time directly:
https://calendly.com/hishamalasker/15min

Best,
Master Mind Team
```

### Thank You Page (optional)
- [ ] Create `/thank-you.html` in landing-deploy/
- [ ] Configure Formspree to redirect there after submit
- [ ] Offer: "Or book now →" link to Calendly

---

## Deployment Verification

- [ ] Landing page loads: https://hishalasker.github.io/mastermind-landing/
- [ ] Header CTA visible: "Book a 15-min walkthrough"
- [ ] Nav has "Get Started" link
- [ ] Scroll to #contact section works
- [ ] Both buttons responsive on mobile
- [ ] Form submits without errors
- [ ] Calendly opens in new tab

---

## When to Add to Outreach

After completing checklist above, add landing page to:
- [ ] LinkedIn profile (in About)
- [ ] Email signature ("Learn more:")
- [ ] Product hunt if launching
- [ ] Twitter/X if applicable
- [ ] Personal website
- [ ] Sales emails (add near end: "Learn more at [link]")

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Form not sending | Confirm Formspree email (check spam folder) |
| Calendly showing no slots | Check timezone + availability hours in settings |
| Email goes to spam | Whitelist `noreply@formspree.io` |
| Button doesn't link | Check Formspree form ID in HTML matches |
| Mobile layout broken | Test on phone (should stack 2-column → 1-column) |

---

## Files Modified

- `index.html` — Added contact section, form, styling
- `CTA_INTEGRATION_GUIDE.md` — Full docs (this folder)
- `SETUP_CHECKLIST.md` — Quick reference (this file)

**Deployed to**: https://github.com/hishalasker/mastermind-landing (auto-deploys to GitHub Pages)

---

## Next Steps (After Setup)

1. ✅ Complete checklist above
2. ✅ Monitor first week of submissions
3. ✅ Adjust form questions if needed
4. ✅ Update response template based on real questions
5. ✅ Add tracking (Google Analytics)
6. ✅ Scale outreach (LinkedIn, email signatures, etc.)

---

**Timeline**: ~5 min setup, 1 week validation, then optimize based on real data.
