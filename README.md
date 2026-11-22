# 🔮 Liquid Glass Settings for Samsung One UI

<div align="center">

<img src="https://raw.githubusercontent.com/haithemxt/Liquid-Glass-Settings/main/icon.png" alt="Liquid Glass Icon" width="128" height="128" onerror="this.src='https://img.icons8.com/fluency/144/layers.png'" />

### Transform Samsung One UI Settings into Ultra-Premium 3D Liquid Glass
**Pure Translucent Acrylic Glass • Specular 3D Lighting • Seamless Canonical Grouping • SubSettings & Connected Apps**

[![One UI Versions](https://img.shields.io/badge/One%20UI-8.0%20%7C%208.5%20%7C%209.0-0c66e4.svg?style=for-the-badge&logo=samsung)](https://www.samsung.com)
[![Android](https://img.shields.io/badge/Android-14%20%7C%2015%20%7C%2016-34A853.svg?style=for-the-badge&logo=android)](https://www.android.com)
[![LSPosed](https://img.shields.io/badge/LSPosed-API%20102%20Modern%20%2F%20Vector-blueviolet.svg?style=for-the-badge)](https://github.com/mywalkb/LSPosed_mod)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.0-7F52FF.svg?style=for-the-badge&logo=kotlin)](https://kotlinlang.org)
[![Tested Devices](https://img.shields.io/badge/Verified-S24%20%7C%20S22%20%7C%20A36%20%7C%20A16%20%7C%20A15-success?style=for-the-badge)](https://github.com/haithemxt/Liquid-Glass-Settings)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)

[**Download Latest Release (APK)**](https://github.com/haithemxt/Liquid-Glass-Settings/releases) • [**تقرير باللغة العربية**](#-ملخص-المشروع-باللغة-العربية)

</div>

---

## 🌟 Overview

**Liquid Glass Settings** is a cutting-edge Xposed / LSPosed customization module engineered exclusively for **Samsung One UI**. It transforms the default flat Samsung Settings interface into an ultra-premium, **100% transparent 3D Liquid Glass** experience inspired by futuristic translucent design aesthetics.

Unlike generic transparent themes or fake wallpaper-sampling overlays, Liquid Glass renders authentic **optical light physics**: curved specular surface glares, double-layered caustic borders, smooth corner bevels, and canonical card grouping across both the main Settings homepage and all SubSettings pages (About Phone, Display, Connections, etc.).

---

## 📱 Tested & Verified Devices Matrix

Liquid Glass Settings has undergone extensive testing across multiple Samsung hardware platforms (Flagships to Mid-range and Budget series) on the latest **One UI 8.0, One UI 8.5, and One UI 9.0** firmware:

| Device Model | Model Codes | Chipset Architecture | One UI 8.0 | One UI 8.5 | One UI 9.0 | Status |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: |
| **Samsung Galaxy S24** | `SM-S921x` / `SM-S926x` / `SM-S928x` | Snapdragon 8 Gen 3 / Exynos 2400 | ✅ | ✅ | ✅ | **Fully Verified** |
| **Samsung Galaxy S22** | `SM-S901x` / `SM-S906x` / `SM-S908x` | Snapdragon 8 Gen 1 / Exynos 2200 | ✅ | ✅ | ✅ | **Fully Verified** |
| **Samsung Galaxy A36** | `SM-A366x` | Exynos 1380 / Dimensity | ✅ | ✅ | ✅ | **Fully Verified** |
| **Samsung Galaxy A16** | `SM-A165x` / `SM-A166x` | MediaTek Helio G99 / Dimensity 6300 | ✅ | ✅ | ✅ | **Fully Verified** |
| **Samsung Galaxy A15** | `SM-A155x` / `SM-A156x` | MediaTek Helio G99 / Dimensity 6100+ | ✅ | ✅ | ✅ | **Fully Verified** |

> [!NOTE]
> Also compatible with other Samsung Galaxy devices (S23, S21, A55, A54, Z Fold, Z Flip) running One UI 6.x through One UI 9.x.

---

## ✨ Key Features & Technical Highlights

### 💎 1. Authentic 3D Liquid Glass Material
- **Pure Transparent Optical Body:** Smooth translucent gradient layer giving natural glass refraction and density without washing out.
- **Top Curvature Specular Glare:** 3D convex light reflection arc dynamically drawn along top curved edges, replicating molded optical glass.
- **Caustic Rim & Refractive Bevel:** Outer luminous electric-blue rim + delicate `0.9dp` inner refractive bevel for tangible physical depth.
- **Natural Light Interaction:** Eliminates fake screen-slice sampling; true view transparency allows backgrounds and animations to shine through cleanly.

### 📐 2. Canonical Card Grouping & Fusion
- **Zero Card Fragmentation:** Automatically categorizes list preferences into Canonical Glass Groups:
  - `TOP`: Rounded top corners with straight bottom edge.
  - `MIDDLE`: Flat glass shelves with hairline translucent dividers.
  - `BOTTOM`: Straight top edge with smooth rounded bottom corners.
  - `SINGLE`: Fully rounded standalone glass capsules (e.g., Samsung Account, Device Care).
- **OEM Override Shield:** Neutralizes Samsung's internal `HighlightableTopLevelPreferenceAdapter` and `RoundCorner` masks from overriding glass backgrounds or collapsing capsules.

### 📱 3. Complete SubSettings & Connected Apps Visibility
- **Intelligent Spacer Filtering:** Precisely eliminates OEM empty dividers while preserving all critical SubSettings headers, custom illustrations, battery charts, and device identification cards.
- **Full About Phone (`SecDeviceInfoTopPreference`) Support:** Device name, status cards, IMEI information, and regulatory badges remain fully visible and properly styled in liquid glass.
- **Developer Options Clearance:** Dynamically expands bottom padding (`150dp` bottom clearance with `clipToPadding = false`), ensuring the last preferences are never obstructed by the floating search capsule.

### 🔤 4. Universal High-Contrast Typography
- **Hardware-Accelerated Text Shadowing:** Automatically applies drop shadows to titles, summaries, and captions.
- **100% Legibility:** Crystal-clear text readability over any wallpaper—from deep OLED blacks to bright white gradients and colorful landscapes.

### ⚙️ 5. Dynamic LSPosed Scope & Companion Manager
- **Open Dynamic Scope:** No hardcoded module scope locks. Easily select and hook Samsung Settings, One UI Home (`com.sec.android.app.launcher`), Wallpaper & Style, and connected system tools.
- **Interactive Manager App:**
  - Adjust glass opacity, blur radius, edge intensity, and corner curvature in real time.
  - Custom wallpaper picker with high-resolution center-crop processing.
  - Quick Root Settings reboot button to apply changes instantly.

---

## 🛠️ Architecture & Hook Engine

```
                          ┌────────────────────────┐
                          │   LSPosed Framework    │
                          └───────────┬────────────┘
                                      │ Injects into com.android.settings
            ┌─────────────────────────┴─────────────────────────┐
            ▼                                                   ▼
┌─────────────────────────┐                           ┌─────────────────────────┐
│     HomepageHook        │                           │     SubSettingsHook     │
│ ─────────────────────── │                           │ ─────────────────────── │
│ • Canonical Tagging     │                           │ • Header Spacer Filter  │
│ • View Hierarchy Hooks  │                           │ • Bottom 150dp Padding  │
│ • Layout Injection      │                           │ • About Phone Enabler   │
└───────────┬─────────────┘                           └───────────┬─────────────┘
            │                                                   │
            └─────────────────────────┬─────────────────────────┘
                                      │ Styles Views with
                                      ▼
                        ┌───────────────────────────┐
                        │    LiquidGlassDrawable    │
                        │ ───────────────────────── │
                        │ • Translucent Acrylic Core│
                        │ • 3D Convex Glare Arc     │
                        │ • Dual Caustic Rim Bevel  │
                        │ • Smooth Press Feedback   │
                        └───────────────────────────┘
```

---

## 🚀 Installation & Setup

### Prerequisites:
1. A Samsung Galaxy device running **One UI 8.0 / 8.5 / 9.0** (or One UI 6 / 7).
2. Root access via **Magisk**, **KernelSU**, or **APatch**.
3. **LSPosed (Zygisk)** or **LSPosed Mod / Vector Active** installed and active.

### Steps:
1. **Download:** Grab the latest `LiquidGlassSettings.apk` from the [Releases](https://github.com/haithemxt/Liquid-Glass-Settings/releases) page.
2. **Install:** Install the APK on your device.
3. **Activate:**
   - Open **LSPosed Manager**.
   - Navigate to the **Modules** tab and enable **Liquid Glass Settings**.
   - In the module scope, select **Settings** (`com.android.settings`) and optionally **One UI Home** (`com.sec.android.app.launcher`).
4. **Configure:**
   - Open the **Liquid Glass** app from your app drawer.
   - Select your preferred glass style, opacity, or pick a custom wallpaper.
   - Tap **"Apply & Restart Settings"** (Root).

---

## 🌍 ملخص المشروع باللغة العربية

### تحويل كامل لإعدادات سامسونج One UI إلى زجاج سائل ثلاثي الأبعاد (3D Liquid Glass)

تم تطوير موديل **Liquid Glass Settings** ليعمل عبر منصة **LSPosed** خصيصاً لهواتف سامسونج جالاكسي، حيث يحول واجهة الإعدادات التقليدية إلى زجاج أكريليكي شفاف ثلاثي الأبعاد يتمتع بفيزياء ضوئية حقيقية وانكسارات إضاءة حواف مبهرة.

### الأجهزة التي تم اختبارها وتأكيد عمل الموديل عليها بنجاح:
تم عمل اختبارات مكثفة والتأكد من استقرار الموديل بنسبة 100% على الأجهزة التالية:
- **Samsung Galaxy S24** (One UI 8.0 / 8.5 / 9.0)
- **Samsung Galaxy S22** (One UI 8.0 / 8.5 / 9.0)
- **Samsung Galaxy A36** (One UI 8.0 / 8.5 / 9.0)
- **Samsung Galaxy A16** (One UI 8.0 / 8.5 / 9.0)
- **Samsung Galaxy A15** (One UI 8.0 / 8.5 / 9.0)

### أبرز المزايا في التحديث الجديد:
1. **خامة زجاج سائل شفافة 100% (Pure Liquid Glass):** انعكاس ضوئي علوي مقوس (Glare Arc) مع حواف مشعة مزدوجة بدون تشويه أو لصق صور غير متناسقة.
2. **الدمج الكبسولي الذكي (Canonical Grouping):** تجميع عناصر الإعدادات بسلاسة في كبسولات أنيقة (`TOP` و `MIDDLE` و `BOTTOM` و `SINGLE`) لمنع تفكك القوائم أو ظهور خلفيات سامسونج الرمادية فوق الزجاج.
3. **دعم كامل لصفحة "معلومات الهاتف" والصفحات الفرعية:** حل مشكلة اختفاء معلومات الهاتف (About Phone) وأرقام الـ IMEI مع الحفاظ على شفافية البطاقات.
4. **حل نزول القوائم (Developer Options Padding):** زيادة مساحة التمرير السفلية لمنع اختفاء خيارات المطورين أو العناصر الأخيرة خلف شريط البحث العائم.
5. **نطاق ديناميكي حر (Dynamic LSPosed Scope):** إمكانية تفعيل الموديل بحرية على تطبيق الإعدادات وتطبيقات النظام المرتبطة.

---

## 👨‍💻 Developer & Contributions

- **Lead Developer:** [**Haythem Ahmed (@haithemxt)**](https://github.com/haithemxt)
- **Repository:** [https://github.com/haithemxt/Liquid-Glass-Settings](https://github.com/haithemxt/Liquid-Glass-Settings)
- Contributions, bug reports, and pull requests are warmly welcome!

---

## 📄 License

This project is open-source and released under the [MIT License](LICENSE).
