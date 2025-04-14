# 🕵️‍♂️ Digital Forensics & OSINT Challenge: Metadata & Reverse Image Analysis

This repository contains a step-by-step walkthrough of how I used **ExifTool** and **Yandex Reverse Image Search** to analyze two image files in a digital forensics challenge. The goal was to extract valuable intelligence from seemingly benign media files.

## 📁 Files in This Repository 

- `uploaded_1.JPG` – Image with altered metadata
- `uploaded_2.JPG` – Image used for reverse image search
- `Final_Report.md` – Full write-up of findings and methods

> 🔽 **Download the files above** to follow the steps locally password is btlo.

---

## 🛠️ Tools Required
- [ExifTool](https://exiftool.org/) – for extracting metadata
- [Yandex Reverse Image Search](https://yandex.com/images/) – for image-based location analysis
- (Optional) Any coordinate conversion or mapping tool like Google Maps or [LatLong.net](https://www.latlong.net/)

---

## 🧪 Steps to Reproduce the Analysis

### 1. 📸 Analyze the First Image (Metadata Analysis)

```bash
exiftool uploaded_1.JPG > Exif_Report.txt
```

From the output, observe the following:
- **Camera Model**: Canon EOS 550D
- **Timestamp**: `2021:11:02 13:20:23`
- **User Comment**: `relying on altered metadata to catch me?`
- **GPS Coordinates**: `32 deg 40' 3.87" S, 279 deg 29' 31.87" W`

> Note: The GPS coordinates are not valid (longitude > 180), suggesting intentional tampering.

### 2. 🌍 Attempt to Validate GPS Coordinates (Spoof Detection)
- Use online coordinate converters to check if the position is real.
- Discover that longitude `279°` is invalid — longitude ranges from 0° to 180°.
- Confirm metadata was altered to mislead the investigator.

### 3. 🔍 Reverse Image Search (Second Image)
Use **Yandex Reverse Image Search** to investigate the second image:

1. Go to [Yandex Images](https://yandex.com/images/)
2. Upload `uploaded_2.JPG`
3. Review visual matches and landmarks

> The results point to **Kathmandu, Nepal** based on location similarities and structure patterns.

---

## ✅ Final Answers

| Question | Answer |
|----------|--------|
| Camera Model | Canon EOS 550D |
| Date Picture Taken | 2021:11:02 13:20:23 |
| Metadata Comment | relying on altered metadata to catch me? |
| Suspected Location | Kathmandu, Nepal |

---

## 📌 What This Demonstrates
- Image metadata extraction with CLI tools
- Detection of tampered metadata (spoofed GPS)
- Use of OSINT tools for location tracing
- Methodical forensic investigation techniques

---

Feel free to reference it in your own cybersecurity portfolio.

> ⭐ **If you found this helpful, give it a star!**
