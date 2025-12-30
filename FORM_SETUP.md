# Form Setup Instructions

## Current Status
The forms on your website are currently set up but need Formspree endpoints to actually send emails. Right now, they will show success/error messages but won't actually send anything until you complete the setup below.

## Setup Steps

### 1. Sign up for Formspree
1. Go to https://formspree.io
2. Sign up for a free account (50 submissions/month on free tier)
3. Verify your email address

### 2. Create Forms
1. After logging in, click "New Form"
2. Create two forms:
   - **Subscribe Form** - for email subscriptions
   - **Contact Form** - for contact form submissions

### 3. Get Your Endpoint URLs
1. For each form, Formspree will give you an endpoint URL like:
   - `https://formspree.io/f/YOUR_FORM_ID`
2. Copy these URLs

### 4. Update Your Website
1. Open `index.html`
2. Find the line that says: `const response = await fetch('YOUR_FORMSPREE_ENDPOINT', {`
3. Replace `'YOUR_FORMSPREE_ENDPOINT'` with your subscribe form endpoint URL
4. Open `contact.html`
5. Find the same line and replace it with your contact form endpoint URL

### Example:
```javascript
// Before:
const response = await fetch('YOUR_FORMSPREE_ENDPOINT', {

// After:
const response = await fetch('https://formspree.io/f/abc123xyz', {
```

## How It Works
- When someone subscribes or contacts you, the form data is sent to Formspree
- Formspree will email you the submission
- The user sees a success message on the website
- You can also view submissions in your Formspree dashboard

## Alternative Options
If you don't want to use Formspree, you can:
- Use EmailJS (https://www.emailjs.com) - sends emails directly
- Use Netlify Forms (if you move to Netlify hosting)
- Set up your own backend server

## Testing
After updating the endpoints:
1. Test the subscribe form on the homepage
2. Test the contact form on the contact page
3. Check your email for the submissions
4. Check your Formspree dashboard

