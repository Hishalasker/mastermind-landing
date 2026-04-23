# Email Form Field Reference

## Form Endpoint

**Service**: Formspree (free tier)  
**Current Form ID**: `mbjenkgj` (placeholder — will be generated for you)  
**Form URL**: `https://formspree.io/f/mbjenkgj`  
**Email destination**: `hishamalasker@gmail.com`

---

## Form Fields (as deployed)

### 1. Name (Required)
- **Field name**: `name`
- **Type**: Text input
- **Placeholder**: "Alice Chen"
- **Validation**: Required
- **In email**: Appears as "From: [name]"

### 2. Email (Required)
- **Field name**: `email`
- **Type**: Email input
- **Placeholder**: "alice@company.com"
- **Validation**: Required, valid email format
- **In email**: Appears as "Reply-To: [email]"

### 3. Company / Project (Optional)
- **Field name**: `company`
- **Type**: Text input
- **Placeholder**: "Acme AI Inc (optional)"
- **Validation**: None
- **In email**: Included as "Company: [company]"

### 4. Tell Us About Your Setup (Required)
- **Field name**: `message`
- **Type**: Textarea (multiline)
- **Placeholder**: "E.g., We're running 3 AI agents and need an approval system. We're currently on..."
- **Validation**: Required, min 10 chars recommended
- **In email**: Full text in email body

### 5. When Do You Need This? (Optional)
- **Field name**: `timeline`
- **Type**: Select dropdown
- **Options**:
  - "This week"
  - "This month"
  - "Next quarter"
  - "Just exploring"
- **Validation**: None
- **In email**: Included as custom field

---

## Email Layout (What You'll Receive)

When a prospect submits:

```
From: Alice Chen <alice@company.com>
To: hishamalasker@gmail.com
Subject: New contact form submission

Name: Alice Chen
Email: alice@company.com
Company: Acme AI Inc
Message: We're running 3 AI agents and need an approval system...
Timeline: This month

---
Reply directly to this email to respond to the prospect.
Sent via Formspree (https://formspree.io)
```

---

## Modifying Form Fields

To add/remove/edit fields, update `index.html` section:

```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
    <!-- Add field here -->
    <div class="form-group">
        <label for="field_name">Display Label</label>
        <input type="text" id="field_name" name="field_name" required>
    </div>
</form>
```

### Input Types Supported
- `text` — Single-line text
- `email` — Email validation
- `tel` — Phone number
- `textarea` — Multi-line text
- `select` — Dropdown
- `checkbox` — Yes/no
- `radio` — Single option
- `number` — Numeric input
- `date` — Date picker

### Example: Add Phone Field
```html
<div class="form-group">
    <label for="phone">Phone (optional)</label>
    <input type="tel" id="phone" name="phone" placeholder="+1 (555) 123-4567">
</div>
```

### Example: Add Budget Field
```html
<div class="form-group">
    <label for="budget">Budget Range</label>
    <select id="budget" name="budget">
        <option value="">Select budget...</option>
        <option value="<1k">Less than $1k</option>
        <option value="1-5k">$1k - $5k</option>
        <option value="5-10k">$5k - $10k</option>
        <option value=">10k">$10k+</option>
    </select>
</div>
```

---

## Formspree Submission Data

After Formspree confirmation, you can:

1. **View submissions** on Formspree dashboard:
   - https://formspree.io → Your account → Submissions
   - See all form data, timestamps, IP addresses
   - Export as CSV

2. **Set up notifications**:
   - Email on each submission (default)
   - Slack webhook (paid feature)
   - Discord webhook (via Zapier)
   - Telegram (via Zapier)

3. **Auto-responses**:
   - Configure in Formspree settings
   - Send auto-reply to prospect
   - Include Calendly link for quick booking

---

## Testing Form Submission

### Test Data
```
Name: Test User
Email: test@example.com
Company: Test Company
Message: This is a test submission to verify form is working.
Timeline: Just exploring
```

### Expected Behavior
1. Click "Send Message" button
2. Form validates (all required fields checked)
3. Submit button shows loading state
4. Page redirects (optional, configurable)
5. You receive email at `hishamalasker@gmail.com`
6. Prospect receives auto-reply (if configured)

### Verify Success
- [ ] Form clears after submit (UX confirmation)
- [ ] Email arrives within 1-2 minutes
- [ ] All fields appear correctly in email
- [ ] Subject line readable
- [ ] Reply-To is prospect email

---

## Security & Privacy

### Formspree Privacy
- ✅ GDPR compliant
- ✅ No 3rd-party tracking on form
- ✅ Data stored on Formspree servers (US-based)
- ✅ SSL encrypted in transit
- ✅ Can export/delete submissions anytime

### Data Handling
- Email addresses are **not** sold
- Prospect data **not** shared with marketers
- Only you (and Formspree admins) see submissions
- Prospect aware: "We respect your privacy. No spam, no selling your data."

### GDPR Compliance
- Add to privacy policy: "Form submissions via Formspree, GDPR compliant"
- Prospect email stored only in Formspree dashboard
- Can request deletion via Formspree

---

## Analytics Integration

### Track in Google Analytics
```javascript
// Track form submissions
document.querySelector('form').addEventListener('submit', function() {
  gtag('event', 'contact_form_submit', {
    'event_label': 'Master Mind CTA'
  });
});

// Track Calendly clicks
document.querySelector('a[href*="calendly"]').addEventListener('click', function() {
  gtag('event', 'calendly_click', {
    'event_label': 'Self-schedule CTA'
  });
});
```

---

## Customization Ideas

### To increase conversion:
1. **Shorter form** (remove "Company" if not needed)
2. **Field labels as hints** ("Tell us about your current setup...")
3. **Progress indicator** (if form gets longer)
4. **Conditional fields** ("If you have a budget, tell us...")
5. **File upload** (let prospects attach current config)

### Current form is optimized for:
- ✅ Speed (4 fields, ~30 seconds to fill)
- ✅ Intent (timeline field = sales qualification)
- ✅ Context (setup details = qualify leads)
- ✅ Urgency (timeline = sales signal)

---

## Troubleshooting

| Issue | Cause | Solution |
|-------|-------|----------|
| Form doesn't submit | Invalid Formspree ID | Copy correct ID from Formspree dashboard |
| Email not received | Formspree account not confirmed | Confirm email link sent by Formspree |
| Field not appearing in email | Field name mismatch | Ensure `name="field_name"` in HTML |
| Auto-reply not sending | Not configured in Formspree | Set up in Formspree → Settings → Auto-response |
| Form appears broken on mobile | CSS issue | Check responsive styling in index.html |

---

## Reference Links

- **Formspree docs**: https://formspree.io/help/forms/
- **Form HTML spec**: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form
- **GDPR & Formspree**: https://formspree.io/blog/formspree-gdpr/

---

**Summary**: Form is production-ready. Just confirm Formspree email and test once. All fields are optional in code, but recommended for qualification.
