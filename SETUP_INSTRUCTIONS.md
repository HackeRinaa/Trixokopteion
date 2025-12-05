# Τρίχο Κοπτείον - Landing Page Setup Instructions

## 📋 Overview
This is a responsive landing page designed for QR code access at your barber shop. The page features three main action buttons and is optimized for mobile viewing.

## 🎨 Design Features
- **Color Scheme**: Warm browns, gold (#DAA520), and black - matching your shop's aesthetic
- **Responsive Design**: Optimized for mobile devices (QR code scanning)
- **Smooth Animations**: Fade-in effects and hover transitions
- **Modern UI**: Rounded buttons, gradient backgrounds, and clean typography

## 🔧 Configuration Steps

### 1. Add Your Shop Image
Replace the placeholder image reference in the HTML:
- **Line 174**: Find `<img src="barber-shop-image.jpg">`
- Replace `"barber-shop-image.jpg"` with your actual image filename
- Place your image file in the same folder as `index.html`

### 2. Configure IRIS Payment Link
- **Line 424**: Find `const IRIS_LINK = 'https://your-iris-payment-link-here.com';`
- Replace with your actual IRIS payment URL

### 3. Configure Google Reviews Link
- **Line 428**: Find `const GOOGLE_REVIEW_LINK = 'https://your-google-review-link-here.com';`
- Replace with your Google Business review URL
- To get your Google review link: Go to your Google Business Profile → Share review form

### 4. Setup WiFi Credentials

#### Option A: Manual WiFi Info (Simpler)
- **Line 432**: Update `const WIFI_SSID = 'TricoKopteion_Guest';`
- **Line 433**: Update `const WIFI_PASSWORD = 'YourPassword123';`

#### Option B: WiFi QR Code (Recommended)
You have two options:

**Option B1: Upload Your Own QR Code**
1. Generate a WiFi QR code using a tool like:
   - https://www.qr-code-generator.com/solutions/wifi-qr-code/
   - https://qifi.org/
2. Save the QR code image as `wifi-qr-code.png`
3. Place it in the same folder as `index.html`
4. Update **Line 440**: `const WIFI_QR_IMAGE_PATH = 'wifi-qr-code.png';`

**Option B2: Auto-Generate QR Code**
1. Find the commented section starting at **Line 447**
2. Uncomment lines 447-457 (remove the `/*` and `*/`)
3. Update the WiFi credentials at lines 432-433
4. The QR code will be generated automatically using an online API

## 📁 File Structure
```
Your-Folder/
├── index.html                  (Main landing page)
├── barber-shop-image.jpg       (Your shop image)
├── wifi-qr-code.png           (Optional: WiFi QR code)
└── SETUP_INSTRUCTIONS.md      (This file)
```

## 🚀 Deployment Options

### Option 1: GitHub Pages (Free & Easy)
1. Create a GitHub repository
2. Upload `index.html` and images
3. Go to Settings → Pages → Enable GitHub Pages
4. Your URL will be: `https://yourusername.github.io/repository-name`

### Option 2: Netlify Drop (Instant & Free)
1. Go to https://app.netlify.com/drop
2. Drag and drop your folder
3. Get instant URL

### Option 3: Your Own Hosting
1. Upload all files to your web hosting
2. Ensure `index.html` is in the root directory

## 📱 Testing
1. Open the page on your phone
2. Test all three buttons:
   - IRIS Payment button should redirect to payment page
   - Google Reviews should open Google
   - WiFi button should show modal with QR code/credentials
3. Verify responsive layout looks good
4. Test WiFi QR code scanning with your phone

## 🔗 Generating Google Review Link
1. Go to https://business.google.com/
2. Select your business location
3. Click "Home" → "Get more reviews"
4. Copy the review link
5. Or use this format: `https://search.google.com/local/writereview?placeid=YOUR_PLACE_ID`

## 🎯 QR Code Generation
To create a QR code pointing to your landing page:
1. Once hosted, copy your page URL
2. Use https://www.qr-code-generator.com/
3. Paste your URL
4. Download and print the QR code
5. Place it in your shop

## 📝 Customization Tips

### Change Colors
Find the color codes in the `<style>` section and modify:
- Gold: `#DAA520` (lines with this color)
- Dark brown: `#2c1810`
- Button colors: Look for `background: linear-gradient(...)` in `.btn-*` classes

### Change Button Text
Find the button HTML around lines 181-195 and modify the Greek text.

### Change Shop Name
Update "Τρίχο Κοπτείον" at:
- Line 165 (Header)
- Line 228 (Footer)
- Line 6 (Page title)

## ⚠️ Important Notes
- Keep all files in the same folder
- Image formats supported: JPG, PNG, WebP
- For best QR scanning, use high contrast QR codes
- Test on multiple phone models before printing QR codes
- Keep WiFi password secure - consider guest network

## 🆘 Troubleshooting

**Issue**: Images not showing
- **Solution**: Check file names match exactly (case-sensitive)

**Issue**: Buttons not working
- **Solution**: Verify URLs are correct and include `https://`

**Issue**: WiFi QR not working
- **Solution**: Ensure QR code format is correct: `WIFI:T:WPA;S:SSID;P:PASSWORD;;`

**Issue**: Page looks weird on phone
- **Solution**: Clear browser cache, ensure viewport meta tag is present

## 📞 Support
If you need help customizing further, you can:
1. Test in browser DevTools (F12) for mobile view
2. Check browser console for errors
3. Validate HTML at https://validator.w3.org/

---

**Current Year Auto-Update**: The footer year updates automatically via JavaScript.

**Last Updated**: December 2025

