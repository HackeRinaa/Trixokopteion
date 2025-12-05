# 📶 WiFi QR Code Generation Guide

## Option 1: Using QiFi.org (Recommended - Free & Easy)

### Steps:
1. Go to **https://qifi.org/**
2. Fill in the form:
   - **SSID**: Your WiFi network name (e.g., "TricoKopteion_Guest")
   - **Encryption**: Select "WPA/WPA2" (most common)
   - **Password**: Your WiFi password
   - **Hidden**: Leave unchecked (unless your network is hidden)
3. Click to generate the QR code
4. **Right-click** on the QR code → **Save image as...**
5. Save as `wifi-qr-code.png`
6. Place the file in the same folder as `index.html`

### Why QiFi?
- ✅ Free and open source
- ✅ No watermarks
- ✅ Works offline (client-side only)
- ✅ No registration required
- ✅ Privacy-friendly (nothing sent to server)

---

## Option 2: Using QR Code Generator

### Steps:
1. Go to **https://www.qr-code-generator.com/**
2. Select **"WiFi"** from the QR code types
3. Enter your details:
   - Network name (SSID)
   - Password
   - Encryption type (WPA/WPA2)
4. Customize appearance (optional):
   - Colors: Gold (#DAA520) to match your branding
   - Add shop logo in center (optional)
5. Download as PNG (high resolution)
6. Save as `wifi-qr-code.png`
7. Place in same folder as `index.html`

### Customization Options:
- Add your shop logo in the center
- Change QR code colors (recommend keeping high contrast)
- Add frame with text like "Scan for WiFi"

---

## Option 3: Automatic QR Code Generation (No File Needed)

### Use the Built-in Auto-Generation Feature:

1. Open `index.html` in a text editor
2. Find **line 447** (commented section)
3. Remove the `/*` before line 447
4. Remove the `*/` after line 457
5. Update your WiFi credentials at lines 432-433:
   ```javascript
   const WIFI_SSID = 'Your_Network_Name';
   const WIFI_PASSWORD = 'Your_WiFi_Password';
   ```
6. Save the file
7. The QR code will be generated automatically using Google's QR API

### This Section Should Look Like:
```javascript
function generateWifiQR() {
    const wifiString = `WIFI:T:WPA;S:${WIFI_SSID};P:${WIFI_PASSWORD};;`;
    const qrUrl = `https://api.qrserver.com/v1/create-qr-code/?size=250x250&data=${encodeURIComponent(wifiString)}`;
    document.getElementById('wifiQrImage').src = qrUrl;
}

// Call this function on page load
generateWifiQR();
```

### Pros & Cons:
- ✅ No need to generate/upload QR code file
- ✅ Updates automatically if you change credentials
- ✅ Always available (uses external API)
- ⚠️ Requires internet connection to load QR code
- ⚠️ Depends on external service

---

## Option 4: Advanced - Branded QR Code

### Using Canva (Free):
1. Go to **https://www.canva.com/**
2. Search for "QR Code" templates
3. Generate QR code with WiFi string format:
   ```
   WIFI:T:WPA;S:YourNetworkName;P:YourPassword;;
   ```
4. Customize with:
   - Shop colors (gold, brown, black)
   - Your logo
   - Text like "Free WiFi"
   - Border/frame
5. Download as PNG (1000x1000px minimum)
6. Save as `wifi-qr-code.png`

### Design Tips:
- Keep high contrast (dark QR on light background)
- Don't cover more than 30% of QR code with logo
- Test scanning before finalizing
- Use vector logo for best quality

---

## WiFi String Format Explained

### Standard Format:
```
WIFI:T:[ENCRYPTION];S:[SSID];P:[PASSWORD];H:[HIDDEN];;
```

### Parameters:
- **T**: Encryption type
  - `WPA` or `WPA2` (most common)
  - `WEP` (old, not recommended)
  - `nopass` (open network)
- **S**: Network name (SSID)
- **P**: Password
- **H**: Hidden network
  - `true` or `false`
  - Omit if not hidden

### Examples:

**Standard WPA2 Network:**
```
WIFI:T:WPA;S:TricoKopteion_Guest;P:Barber2024!;;
```

**Open Network (No Password):**
```
WIFI:T:nopass;S:TricoKopteion_Free;;
```

**Hidden Network:**
```
WIFI:T:WPA;S:TricoKopteion_Staff;P:SecretPass123;H:true;;
```

### Special Characters:
If your SSID or password contains these characters, escape them with `\`:
- `;` → `\;`
- `:` → `\:`
- `\` → `\\`
- `,` → `\,`
- `"` → `\"`

**Example with special characters:**
```
WIFI:T:WPA;S:Trico\;Kopteion;P:Pass\:word123;;
```

---

## Testing Your WiFi QR Code

### iOS (iPhone/iPad):
1. Open **Camera** app
2. Point at QR code
3. Tap notification banner
4. Tap "Join" to connect

### Android:
1. Open **Camera** app or
2. Use QR scanner in Quick Settings
3. Point at QR code
4. Tap notification
5. Confirm connection

### Test Checklist:
- ☐ QR code scans successfully
- ☐ Correct network name appears
- ☐ Device connects automatically
- ☐ Internet works after connecting
- ☐ QR code is readable at arm's length
- ☐ Works in shop lighting conditions

---

## Print Guidelines

### For Shop Display:

**Size Recommendations:**
- **Minimum**: 5cm x 5cm (2" x 2")
- **Recommended**: 10cm x 10cm (4" x 4")
- **Table card**: 7cm x 7cm (3" x 3")

**Print Quality:**
- Use high-resolution image (at least 300 DPI)
- Print on matte paper (less glare)
- Laminate or use acrylic stand for durability

**Placement Ideas:**
- Table tent cards
- Wall poster near entrance
- Counter display
- Mirror sticker
- Business card back
- Window decal

**Text to Include:**
```
📶 Δωρεάν WiFi
Free WiFi
Scan to Connect
```

---

## Security Recommendations

### Guest Network Best Practices:
1. **Create separate guest network**
   - Don't use your main business network
   - Isolate from business devices
   - Limit bandwidth if needed

2. **Use strong but shareable password**
   - At least 12 characters
   - Mix of letters, numbers, symbols
   - Memorable for verbal sharing
   - Example: `TricoBarber2024!`

3. **Regular password changes**
   - Change every 3-6 months
   - Update QR code when changed
   - Notify regular customers

4. **Network settings**
   - Enable WPA2 or WPA3
   - Hide SSID (optional, for staff network)
   - Set connection limits if possible
   - Monitor connected devices

### Two-Network Setup (Recommended):
```
Network 1 (Guest): TricoKopteion_Guest
→ For customers
→ QR code displayed
→ Regular password changes

Network 2 (Staff): TricoKopteion_Staff  
→ For business operations
→ Hidden network
→ Stronger password
→ No QR code
```

---

## Troubleshooting

### QR Code Won't Scan:
- **Check contrast**: Dark code on light background
- **Increase size**: Make QR code larger
- **Clean image**: No blur or distortion
- **Good lighting**: Avoid glare and shadows
- **Correct format**: Verify WiFi string syntax

### Connects But No Internet:
- **Check router**: Ensure internet is working
- **Guest isolation**: May be blocking certain services
- **Bandwidth limits**: May be very slow
- **Captive portal**: Some routers require additional login

### Wrong Network Appears:
- **Check SSID**: Verify exact spelling (case-sensitive)
- **Character encoding**: Use only standard characters
- **Escape special chars**: Use `\` before special characters

---

## Resources

### QR Code Generators:
- https://qifi.org/ (WiFi-specific, recommended)
- https://www.qr-code-generator.com/ (Feature-rich)
- https://www.qrcode-monkey.com/ (Custom designs)

### Testing Tools:
- https://zxing.org/w/decode (Test QR code online)
- Mobile: "QR Code Reader" apps

### WiFi String Validators:
- https://feeding.cloud.geek.nz/posts/encoding-wifi-access-point-passwords-qr-code/

---

## Quick Reference Card

```
┌─────────────────────────────────────────────┐
│  WIFI QR CODE QUICK SETUP                   │
├─────────────────────────────────────────────┤
│  1. Go to: https://qifi.org/               │
│  2. Enter SSID: [Your Network Name]        │
│  3. Enter Password: [Your WiFi Password]   │
│  4. Encryption: WPA/WPA2                   │
│  5. Download QR code                        │
│  6. Save as: wifi-qr-code.png              │
│  7. Put in same folder as index.html       │
│  8. Test scan with your phone              │
└─────────────────────────────────────────────┘
```

---

**Need Help?** Test your QR code before printing!

