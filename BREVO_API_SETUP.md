# Brevo API Setup Guide

## 🚀 Using Brevo API (Recommended)

Brevo API is better than SMTP because:
- ✅ No connection timeouts
- ✅ Works perfectly on Render/cloud
- ✅ Faster and more reliable
- ✅ Better error messages
- ✅ No SMTP port blocking issues

## Setup Steps

### 1. Get Your Brevo API Key

1. Sign up at https://www.brevo.com (free account)
2. Go to **SMTP & API** → **API Keys**
3. Click **Generate a new API key**
4. Copy the API key (starts with `xkeysib-...`)

### 2. Set Environment Variables in Render

Add these to your Render dashboard → Environment Variables:

```env
BREVO_API_KEY=xkeysib-your-api-key-here
EMAIL_FROM=noreply@yourdomain.com
EMAIL_FROM_NAME=Login Authentication System
FRONTEND_URL=https://your-frontend-url.com
```

**Important:**
- `BREVO_API_KEY` - Your Brevo API key
- `EMAIL_FROM` - Must be a verified sender email in Brevo
- `EMAIL_FROM_NAME` - Display name (optional)

### 3. Verify Sender Email in Brevo

1. Go to **Senders** in Brevo dashboard
2. Add your sender email (the one you'll use in `EMAIL_FROM`)
3. Verify it via the confirmation email

### 4. Redeploy

After adding environment variables, redeploy your service.

## How It Works

- Uses Brevo REST API (not SMTP)
- No connection timeouts
- Works on any cloud platform
- Fast and reliable

## Test It

1. Register a new account
2. Check your email inbox
3. You should receive the verification email!

## Troubleshooting

### "Invalid API key"
- Verify `BREVO_API_KEY` is correct
- Make sure there are no extra spaces

### "Sender not verified"
- Go to Brevo → Senders
- Verify the email in `EMAIL_FROM`

### "Email not sending"
- Check Render logs for error messages
- Verify API key has sending permissions
- Check Brevo dashboard for delivery status

---

**That's it!** Brevo API is much more reliable than SMTP on cloud platforms. 🎉

