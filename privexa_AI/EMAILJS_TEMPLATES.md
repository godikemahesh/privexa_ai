# EmailJS Templates for Privexa AI

You need to create TWO email templates in your EmailJS dashboard - one for the contact form and one for the demo booking form.

## Template 1: Contact Form Submission

**Template Name**: Contact Form Submission  
**Subject**: New Contact Form Submission - {{from_name}}

**Template Content**:
```
From: {{from_name}}
Email: {{from_email}}
Company: {{company_name}}
Industry: {{industry}}

Message:
{{message}}

---
This email was sent from your Privexa AI website contact form.
```

## Template 2: Demo Booking Request

**Template Name**: Demo Booking Request  
**Subject**: New Demo Booking Request - {{from_name}} ({{company_name}})

**Template Content**:
```
Demo Booking Request

From: {{from_name}}
Email: {{from_email}}
Company: {{company_name}}
Industry: {{industry}}
Demo Type: {{demo_type}}
Preferred Date & Time: {{preferred_datetime}}

Demo Focus / Questions:
{{demo_focus}}

---
This email was sent from your Privexa AI demo booking form.
```

## How to Create These Templates

1. **Go to your EmailJS dashboard**
2. **Navigate to Email Templates**
3. **Click "Create New Template"**
4. **Create Template 1** with the contact form content above
5. **Create Template 2** with the demo booking content above
6. **Note down both Template IDs** (they'll look like `template_abc123` and `template_xyz789`)

## Update Your Code

### For Contact Form (index.html):
Replace in `script.js`:
```javascript
emailjs.send('YOUR_SERVICE_ID', 'YOUR_CONTACT_TEMPLATE_ID', {
```

### For Demo Form (schedule-demo.html):
Replace in the demo page script:
```javascript
emailjs.send('YOUR_SERVICE_ID', 'YOUR_DEMO_TEMPLATE_ID', {
```

## What You'll Receive

### Contact Form Emails:
```
Subject: New Contact Form Submission - John Doe

From: John Doe
Email: john@company.com
Company: ABC Corp
Industry: Healthcare & Pharma

Message:
We need help implementing a private LLM for our medical records system...

---
This email was sent from your Privexa AI website contact form.
```

### Demo Booking Emails:
```
Subject: New Demo Booking Request - Jane Smith (Tech Corp)

Demo Booking Request

From: Jane Smith
Email: jane@techcorp.com
Company: Tech Corp
Industry: Banking & Finance
Demo Type: banking
Preferred Date & Time: 2025-01-15T14:30

Demo Focus / Questions:
We're interested in learning about fraud detection capabilities and how it integrates with our existing systems.

---
This email was sent from your Privexa AI demo booking form.
```

## Important Notes

- Use the **same Service ID** for both templates
- Use **different Template IDs** for each form
- Both forms will send emails to `maheshgodike17@gmail.com`
- Make sure to replace all placeholder values in your code

