# VISA EDM Implementation Guide

**Version:** 1.0  
**Date:** November 2025  
**Email Templates:** 2 EDMs (EDM 1: Service Uptime | EDM 2: Future Ready Commerce)

---

## 📋 Table of Contents

1. [Overview](#overview)
2. [What You Received](#what-you-received)
3. [Before You Start](#before-you-start)
4. [Step-by-Step Setup](#step-by-step-setup)
5. [Hosting Requirements](#hosting-requirements)
6. [Customization Guide](#customization-guide)
7. [Troubleshooting](#troubleshooting)


---

## 📖 Overview

You have received **2 HTML email templates** designed for the VISA Acceptance Platform (VAP) campaign. These templates are optimized for:

- ✅ Outlook (Windows, Mac, Web)
- ✅ Gmail (Web, iOS, Android)
- ✅ Apple Mail (iOS, macOS)
- ✅ Mobile responsive design

---

## 📦 What You Received

```
📁 VISA_EDM_Templates/
├── 📄 edm1_service_uptime.html          (EDM 1: Strengthen your business)
├── 📄 edm2_future_commerce.html         (EDM 2: Powering seamless commerce)
├── 📄 README.md                         (This file)
├── 📄 visa_edm_1.oft                    (EDM 1: oft file)
├── 📄 visa_edm_2.oft                    (EDM 2: oft file)
├── 📁 images/
│   ├── 🖼️ logo_2x.png                   (VISA logo)
│   ├── 🖼️ header1_2x.jpeg               (Hero image EDM 1)
│   ├── 🖼️ header2_2x.jpeg               (Hero image EDM 2)
│   ├── 🖼️ icon-11_2x.png                (Feature icon 1)
│   ├── 🖼️ icon-12_2x.png                (Feature icon 2)
│   ├── 🖼️ icon-13_2x.png                (Feature icon 3)
│   ├── 🖼️ icon-21_2x.png                (EDM 2 feature icon 1)
│   ├── 🖼️ icon-22_2x.png                (EDM 2 feature icon 2)
│   ├── 🖼️ icon-23_2x.png                (EDM 2 feature icon 3)
│   ├── 🖼️ learn-more_2x.png             (Learn more button)
│   ├── 🖼️ cta-bottom_2x.png             (Let's Connect button)
│   └── 🖼️ footer-bottom_2x.png          (Footer decorative bar)
└── 📁 fonts/
    ├── 📄 VisaDialect-Regular-Web.woff2
    ├── 📄 VisaDialect-Regular-Web.woff
    ├── 📄 VisaDialect-Medium-Web.woff2
    ├── 📄 VisaDialect-Medium-Web.woff
    ├── 📄 VisaDialect-Bold-Web.woff2
    └── 📄 VisaDialect-Bold-Web.woff
```

---

## ⚠️ Before You Start

### Required Actions:

1. **Host fonts and images** on your server or CDN
2. **Update all URLs** in the HTML files
3. **Test thoroughly** before sending
4. **Personalize content** (replace "Dear XX," etc.)
5. **Add tracking parameters** to links (optional)

### What You'll Need:

- ✅ Web server or CDN access
- ✅ FTP/SFTP client or file manager
- ✅ Text editor (Notepad++, VS Code, Sublime Text)
- ✅ Microsoft Outlook (for .OFT creation)

---

## 🚀 Step-by-Step Setup

### Step 1: Host Fonts on Your Server

**Upload font files to your server:**

```
Your Server Structure:
https://yourdomain.com/
└── edm/
    └── fonts/
        ├── VisaDialect-Regular-Web.woff2
        ├── VisaDialect-Regular-Web.woff
        ├── VisaDialect-Medium-Web.woff2
        ├── VisaDialect-Medium-Web.woff
        ├── VisaDialect-Bold-Web.woff2
        └── VisaDialect-Bold-Web.woff
```

**Update font URLs in HTML:**

Find this section in the `<head>` of **BOTH** HTML files:

```html
<!-- FIND THIS: -->
@font-face {
    font-family: 'VISA Font';
    src: url('https://raw.githubusercontent.com/nightawaitsday/edm/refs/heads/main/fonts/VisaDialect-Regular-Web.woff2') format('woff2'),
         url('https://raw.githubusercontent.com/nightawaitsday/edm/refs/heads/main/fonts/VisaDialect-Regular-Web.woff') format('woff');
    font-weight: 400;
}

<!-- REPLACE WITH: -->
@font-face {
    font-family: 'VISA Font';
    src: url('https://yourdomain.com/edm/fonts/VisaDialect-Regular-Web.woff2') format('woff2'),
         url('https://yourdomain.com/edm/fonts/VisaDialect-Regular-Web.woff') format('woff');
    font-weight: 400;
}
```

**Repeat for all 3 font weights:**
- Regular (400)
- Medium (600)
- Bold (700)

---

### Step 2: Host Images on Your Server

**Upload image files to your server:**

```
Your Server Structure:
https://yourdomain.com/
└── edm/
    └── images/
        ├── logo_2x.png
        ├── header1_2x.jpg
        ├── header2_2x.jpg
        ├── icon-11_2x.png
        ├── (all other images...)
        └── footer-bottom_2x.png
```

**Update image URLs in HTML:**

**Find and Replace:**

1. Open HTML file in text editor
2. Use "Find and Replace" function (Ctrl+H or Cmd+H)
3. Find: `https://raw.githubusercontent.com/nightawaitsday/edm/refs/heads/main/`
4. Replace with: `https://yourdomain.com/edm/`
5. Replace All

**Or manually replace each image URL:**

```html
<!-- BEFORE -->
<img src="https://raw.githubusercontent.com/nightawaitsday/edm/refs/heads/main/images/logo_2x.png">

<!-- AFTER -->
<img src="https://yourdomain.com/edm/images/logo_2x.png">
```

---

### Step 3: Create Outlook Template (.OFT)

**For Windows Outlook:**

1. Open the HTML file in a web browser
2. Right-click the HTML file → **Open with** → **Microsoft Outlook**
3. Once opened in Outlook:
   - Go to **File** → **Save As**
   - Change "Save as type" to **Outlook Template (*.oft)**
   - Name it: `VISA_EDM1_Service_Uptime.oft`
   - Click **Save**

4. Repeat for EDM 2

**Test the .OFT file:**
- Double-click the .oft file
- Check if all images load
- Verify all text is editable
- Click all links to test

**OR just upload the provided .oft file into the Templates folder for outlook.:**
Templates folder path example: 
C:\Users\username\AppData\Roaming\Microsoft\Templates

---

## 🌐 Hosting Requirements

### Image Hosting:

**Requirements:**
- ✅ HTTPS (secure SSL certificate)
- ✅ Direct image access allowed
- ✅ No authentication required
- ✅ CORS enabled (for cross-origin access)
- ✅ Reliable uptime (99.9%+)

**Recommended Hosting:**
- Your company CDN
- AWS S3 + CloudFront
- Azure Blob Storage
- Google Cloud Storage
- Cloudflare Images

**NOT recommended:**
- ❌ Google Drive
- ❌ Dropbox
- ❌ OneDrive
- ❌ WeTransfer

---

### Font Hosting:

**Requirements:**
- ✅ HTTPS
- ✅ Correct MIME types:
  - `.woff2` → `font/woff2`
  - `.woff` → `font/woff`
- ✅ CORS headers enabled

**Add CORS headers to your server:**

For Apache (.htaccess):
```apache
<FilesMatch "\.(woff|woff2)$">
    Header set Access-Control-Allow-Origin "*"
</FilesMatch>
```

For Nginx:
```nginx
location ~* \.(woff|woff2)$ {
    add_header Access-Control-Allow-Origin *;
}
```

---

## 🎨 Customization Guide

### Changing Text:

**All text is fully editable.** Simply find and replace in the HTML file:

```html
<!-- Main Heading -->
<h1 style="...">Strengthen your business with better service uptime</h1>

<!-- Body Text -->
<p style="...">Merchants today expect their payment partners...</p>

<!-- Stats -->
<p style="...">99.999%</p>
<p style="...">uptime</p>
```

**Important:** Keep the `style="..."` attributes intact when editing text.

---

### Changing Images:

**Button Images:**

To change button images (Learn More, Let's Connect):

1. **Create new button image:**
   - Dimensions: 2x size (e.g., 192×80px for 96×40px display)
   - Format: PNG with transparency
   - Design to match your brand

2. **Upload to your server**

3. **Update HTML:**
   ```html
   <img src="https://yourdomain.com/edm/images/your-new-button.png" 
        width="96" 
        height="40">
   ```

**Hero Images:**

Current dimensions:
- EDM 1: 576×364px (displays at 288×182px)
- EDM 2: 576×364px (displays at 288×182px)

Replace with your images keeping similar dimensions.

---

## 🔧 Troubleshooting

### Issue 1: Images Not Loading

**Symptoms:** Broken image icons, red X

**Solutions:**
1. Check image URLs are absolute (start with https://)
2. Verify images are publicly accessible (open URL in browser)
3. Check CORS headers on your server
4. Ensure HTTPS (not HTTP)
5. Verify no authentication required

---

### Issue 2: Fonts Not Displaying

**Symptoms:** Text shows in Arial/Helvetica instead of VISA Font

**Solutions:**
1. Check font URLs are correct and accessible
2. Verify CORS headers on font files
3. Check MIME types are correct
4. **Note:** Fonts won't work in:
   - Outlook Windows (will use fallback)
   - Gmail Web (will use fallback)
   - This is expected behavior

---

### Issue 3: Text Not Editable in Outlook

**Symptoms:** Can't edit text when opening .oft file

**Solutions:**
1. Make sure you're opening .oft file (not .html)
2. Double-click .oft file to open (don't right-click → edit)
3. Check text isn't inside an image
4. Try recreating .oft file from HTML

---

## 📝 Important Notes

### Font Fallback Strategy:

```
1. VISA Font (your brand font)
2. Open Sans (modern web font)
3. System fonts (-apple-system, Segoe UI)
4. Helvetica (classic fallback)
5. Arial (universal fallback)
```

---

### Image Optimization:

All images are **2x resolution** for retina displays:
- Logo: 246×82px (displays at 123×41px)
- Buttons: 192×80px (displays at 96×40px)
- Icons: ~90×90px (displays at ~45×45px)

**File size targets:**
- Logo: < 50KB
- Hero images: < 200KB each
- Icons: < 20KB each
- Buttons: < 30KB each
- **Total:** < 500KB recommended

---

## ✅ Final Checklist

Before launching your campaign:

**Setup:**
- [ ] Fonts hosted on your server
- [ ] Font URLs updated in HTML
- [ ] Images hosted on your server
- [ ] Image URLs updated in HTML
- [ ] All links updated to actual URLs
- [ ] "Dear XX" personalized
- [ ] .OFT templates created and tested

---

## 🎉 You're All Set!
