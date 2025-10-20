# Detailed EmailJS Setup - Step by Step

Follow these exact steps to get your EmailJS credentials and set up email sending.

## Step 1: Create EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click "Sign Up" 
3. Enter your email and create a password
4. Verify your email address by clicking the link in your inbox

## Step 2: Get Your PUBLIC KEY

1. After logging in, you'll see your dashboard
2. Look for "Account" in the left sidebar and click it
3. You'll see a section called "API Keys"
4. Copy the **Public Key** (starts with `user_` followed by random characters)
   - Example: `user_abc123def456ghi789`
   - This is your **YOUR_PUBLIC_KEY**

## Step 3: Create Email Service (Get SERVICE_ID)

1. In the left sidebar, click "Email Services"
2. Click the "Add New Service" button
3. Choose your email provider:
   - **Gmail**: Most common choice
   - **Outlook**: If you use Outlook/Hotmail
   - **Yahoo**: If you use Yahoo Mail
   - **Custom SMTP**: For other providers

### For Gmail (Recommended):
1. Select "Gmail" from the list
2. Click "Connect Account"
3. Sign in with your Gmail account (maheshgodike17@gmail.com)
4. Allow EmailJS to access your Gmail
5. You'll see a success message
6. **Copy the Service ID** (starts with `service_` followed by random characters)
   - Example: `service_abc123def`
   - This is your **YOUR_SERVICE_ID**

## Step 4: Create Email Template (Get TEMPLATE_ID)

1. In the left sidebar, click "Email Templates"
2. Click "Create New Template"
3. Fill in the template details:

### Template Settings:
- **Template Name**: "Contact Form Submission"
- **Subject**: `New Contact Form Submission - {{from_name}}`

### Template Content:
```
From: {{from_name}} ({{from_email}})
Company: {{company_name}}
Industry: {{industry}}

Message:
{{message}}

---
This email was sent from your Privexa AI website contact form.
```

4. Click "Save" at the bottom
5. **Copy the Template ID** (starts with `template_` followed by random characters)
   - Example: `template_xyz789abc`
   - This is your **YOUR_TEMPLATE_ID**

## Step 5: Update Your Code

Open `script.js` and find these lines (around line 163 and 183):

```javascript
// Replace this line:
emailjs.init('YOUR_PUBLIC_KEY');

// With your actual public key:
emailjs.init('user_abc123def456ghi789');
```

```javascript
// Replace this line:
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', {

// With your actual IDs:
emailjs.send('service_abc123def', 'template_xyz789abc', {
```

## Step 6: Test Your Setup

1. Save your `script.js` file
2. Open your website in a browser
3. Go to the contact form at the bottom of the page
4. Fill out the form with test data:
   - Name: Test User
   - Email: your-email@example.com
   - Company: Test Company
   - Industry: Select any option
   - Message: This is a test message
5. Click "Send Message"
6. You should see a success notification
7. Check your email (maheshgodike17@gmail.com) for the form submission

## Troubleshooting

### If you get an error:
1. **Check browser console** (F12 → Console tab) for error messages
2. **Verify all three IDs** are correctly copied and pasted
3. **Make sure your email service** is properly connected
4. **Check your spam folder** for the test email

### Common Issues:
- **"Invalid public key"**: Double-check you copied the public key correctly
- **"Service not found"**: Make sure your email service is active
- **"Template not found"**: Verify the template ID is correct
- **No email received**: Check spam folder and verify Gmail connection

## Your Credentials Summary

After completing the setup, you should have:

1. **Public Key**: `user_xxxxxxxxx` (from Account → API Keys)
2. **Service ID**: `service_xxxxxxxxx` (from Email Services)
3. **Template ID**: `template_xxxxxxxxx` (from Email Templates)

## Need Help?

- EmailJS Documentation: [https://www.emailjs.com/docs/](https://www.emailjs.com/docs/)
- EmailJS Support: [https://www.emailjs.com/support/](https://www.emailjs.com/support/)

---

**Important**: Keep these credentials secure. The public key is safe to use in your website code, but don't share your private keys with anyone.
