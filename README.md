# UIU Student Rental & Roommate Seeking System

[![Institution](https://img.shields.io/badge/Institution-United%20International%20University%20(UIU)-purple.svg)](https://www.uiu.ac.bd)
[![Frontend](https://img.shields.io/badge/Frontend-HTML5%20%7C%20CSS3%20%7C%20JavaScript%20(ES6)-orange.svg)](#technology-stack)
[![UI Framework](https://img.shields.io/badge/UI%20Framework-Bootstrap%20%7C%20Flexbox%20%7C%20Grid-blue.svg)](#technology-stack)
[![Dark Mode](https://img.shields.io/badge/Theme-Light%20%26%20Dark%20Mode-yellow.svg)](#interactive-house-listings--discovery)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Author](https://img.shields.io/badge/Author-robiultamim-blue.svg)](https://github.com/robiultamim)

An integrated, responsive web platform designed specifically for **United International University (UIU)** students and local property owners in the **Madani Avenue, Vatara, Badda, and 100 Feet** areas of Dhaka. The system streamlines **student accommodation discovery**, **seat/flat reservations**, **roommate matching by academic department and trimester standing**, **landlord property management**, and **interactive tenant feedback**.

---

<p align="center">
  <img src="main/img/home.png" alt="UIU Rental System Showcase" width="70%" />
</p>

---

## Table of Contents

- [Overview & Problem Statement](#overview--problem-statement)
- [Key Features](#key-features)
- [System Architecture & Workflow](#system-architecture--workflow)
- [Core Application Modules](#core-application-modules)
  - [1. Main Landing Portal](#1-main-landing-portal)
  - [2. Dual-Role Authentication Portal](#2-dual-role-authentication-portal)
  - [3. Student Registration & Academic Profile](#3-student-registration--academic-profile)
  - [4. Property Owner Onboarding](#4-property-owner-onboarding)
  - [5. Student Operations Dashboard](#5-student-operations-dashboard)
  - [6. Property Owner Management Dashboard](#6-property-owner-management-dashboard)
  - [7. Interactive House Listings & Discovery](#7-interactive-house-listings--discovery)
  - [8. Landlord Property Listing & Flat Specification](#8-landlord-property-listing--flat-specification)
  - [9. Seat & Room Booking Reservation Flow](#9-seat--room-booking-reservation-flow)
  - [10. Roommate Seeking & Peer Matching](#10-roommate-seeking--peer-matching)
  - [11. Interactive Animated Reaction Feedback](#11-interactive-animated-reaction-feedback)
  - [12. Document & Image Verification Uploader](#12-document--image-verification-uploader)
- [Technology Stack](#technology-stack)
- [Project Directory Structure](#project-directory-structure)
- [Installation & Local Deployment Guide](#installation--local-deployment-guide)
- [Target Demographics & Academic Context](#target-demographics--academic-context)
- [Contributing & License](#contributing--license)

---

## Overview & Problem Statement

Every trimester, hundreds of undergraduate and graduate students at **United International University (UIU)** face severe hurdles when seeking safe, affordable accommodation near the permanent campus at United City, Madani Avenue:
- **Scattered Information:** Accommodation notices are fragmented across Facebook groups, notice boards, and informal word-of-mouth channels.
- **Security & Hidden Costs:** Students frequently encounter hidden utility bills, lack of transparency regarding building security (CCTV, guards), and unverified landlord listings.
- **Roommate Incompatibility:** Finding compatible roommates who share similar study schedules, academic disciplines, and lifestyle habits often leads to friction.
- **Landlord Administrative Overhead:** Local house owners struggle to market vacant flats specifically to verified university students and manage occupancy records.

### The UIU Rental Solution
The **UIU Student Rental System** bridges this divide by providing a unified, centralized web platform tailored to the university community:
1. **Academic Verification:** Collects student IDs, official `@uiu.ac.bd` emails, department affiliations, and completed trimester counts to build a trusted student community.
2. **Comprehensive Flat Attributes:** Mandates detailed property specifications including floor locations, tiled washrooms, balcony availability, lifts, generators, and service charges in BDT (Tk).
3. **Smart Roommate Board:** Dedicated filters matching roommates by gender, trimester status, and department.
4. **Dual-Role Architecture:** Cleanly segregated workflows and dashboards for university students and residential property owners.

---

## Key Features

- 🎓 **Tailored for UIU Campus Life:** Designed specifically around the academic calendar, trimester system, and geography of United International University.
- 👥 **Dual-Role Ecosystem:** Specialized portals for **Students** (searching, booking, roommate requests) and **Property Owners** (listing properties, tracking revenue, managing tenants).
- 🌓 **Dynamic Dark / Light Mode Switch:** One-click instant theme toggle with animated SVG sun and moon icons on house catalog pages.
- 📱 **Fully Responsive Layout:** Optimized for mobile phones, tablets, and desktops using Bootstrap, CSS Grid, and custom Flexbox.
- 🏘️ **Detailed Apartment Specification Form:** Multi-attribute landlord form tracking floor numbers, rooms, washroom tiling, kitchen facilities, CCTV security, 24/7 security guards, elevator access, and monthly service charges.
- 🤝 **Peer Roommate Matching Engine:** Enables students to publish roommate requirement posts specifying university ID, department, trimester count, habits, and budget.
- 🎭 **Interactive Animated Reaction Feedback:** Pure CSS/SVG animated emoji feedback system with dynamic eye-tracking and mouth expressions (Angry, Sad, OK, Good, Happy).
- 📊 **Owner Business Intelligence Dashboard:** Financial KPI cards tracking total rental revenue (in Tk), student tenant counts, and occupancy status.
- 📁 **Drag-and-Drop Document Verification:** Client-side drag-and-drop file uploader component with instant selection previews for student IDs and rental agreements.

---

## System Architecture & Workflow

```
                               ┌─────────────────────────────────────────┐
                               │           UIU Rental Platform           │
                               │               index.html                │
                               └────────────────────┬────────────────────┘
                                                    │
                                                    ▼
                               ┌─────────────────────────────────────────┐
                               │       Main Landing Portal (main/)       │
                               │    Hero • Search • Reviews • Navbar     │
                               └────────────────────┬────────────────────┘
                                                    │
                                                    ▼
                               ┌─────────────────────────────────────────┐
                               │     Authentication Portal (Sign in/)    │
                               │     Sliding Double-Panel Container      │
                               └──────────┬───────────────────┬──────────┘
                                          │                   │
                        Select: "Student" │                   │ Select: "Owner"
                                          ▼                   ▼
                     ┌──────────────────────────┐    ┌──────────────────────────┐
                     │   Student Registration   │    │    Owner Registration    │
                     │       (student/)         │    │         (owner/)         │
                     │  • University ID & Email │    │  • Property Count & City │
                     │  • Department & Trimester│    │  • Contact & Credentials │
                     └────────────┬─────────────┘    └────────────┬─────────────┘
                                  │                               │
                                  ▼                               ▼
                     ┌──────────────────────────┐    ┌──────────────────────────┐
                     │    Student Dashboard     │    │     Owner Dashboard      │
                     │ (dashboard of student/)  │    │  (dashboard of owner/)   │
                     │  • Roommate Seeking Board│    │  • Revenue & Occupancy   │
                     │  • Favorite Houses       │    │  • Tenant Request Table  │
                     │  • Profile & Photo Upload│    │  • New House Creation    │
                     └────────────┬─────────────┘    └────────────┬─────────────┘
                                  │                               │
          ┌───────────────────────┴───────────────┐               │
          ▼                                       ▼               ▼
┌──────────────────┐                    ┌──────────────────┐ ┌──────────────────┐
│  House Catalog   │                    │ Roommate Finder  │ │  Add Flat Form   │
│     (house/)     │                    │   (roommate/)    │ │    (house_1/)    │
│ • Dark/Light Mode│                    │ • UIU ID & Dept  │ │ • Floor, Rooms   │
│ • Modal Details  │                    │ • Trimester Rank │ │ • CCTV, Lift, BDT│
└─────────┬────────┘                    └──────────────────┘ └──────────────────┘
          │
          ▼
┌──────────────────┐                    ┌──────────────────┐ ┌──────────────────┐
│ Booking Checkout │                    │ Emotion Feedback │ │  Doc Uploader    │
│   (booking/)     │                    │    (rating/)     │ │   (check.html)   │
│ • Rent in Tk     │                    │ • Animated SVGs  │ │ • Drag-and-Drop  │
│ • Move-in Dates  │                    │ • Star/Emoji Rate│ │ • File Previews  │
└──────────────────┘                    └──────────────────┘ └──────────────────┘
```

---

## Core Application Modules

### 1. Main Landing Portal
- **Location:** `main/index.html`, `main/style.css`, `main/vs.js`
- **Features:**
  - Modern branded navigation bar with UIU Student Rental System insignia.
  - Compelling hero callout: *"Need A Comfortable Space while Studying? Home Like Experience!"*
  - Quick action CTA buttons for direct Sign In and Sign Up routing.
  - Interactive multi-slide customer and corporate review carousel (`#myCarousel`) powered by jQuery and Bootstrap.

### 2. Dual-Role Authentication Portal
- **Location:** `Sign in/sg.html`, `Sign in/sg.css`, `Sign in/sg.js`
- **Features:**
  - Double sliding overlay panel container that smoothly transitions between Sign In and Registration modes.
  - Role dropdown selector ensuring correct provisioning as an **Owner** or **Student**.
  - Social authentication buttons and clean form input states.

### 3. Student Registration & Academic Profile
- **Location:** `student/st.html`, `student/st.css`
- **Features:**
  - Multi-attribute university registration form capturing:
    - Full Student Name
    - Official University Email (`@uiu.ac.bd`)
    - University Student ID Number
    - Department Name (CSE, EEE, BBA, Civil, etc.)
    - Mobile Contact
    - Present and Permanent Addresses

### 4. Property Owner Onboarding
- **Location:** `owner/ow.html`, `owner/ow.css`
- **Features:**
  - Comprehensive registration form for residential landlords and hostel managers.
  - Captures owner contact details, property count, municipal state, city, and full street address.

### 5. Student Operations Dashboard
- **Location:** `dashboard of student/dos.html`, `dashboard of student/dos.css`, `dashboard of student/dos.js`
- **Features:**
  - Responsive collapsible sidebar navigation with mobile toggle support (`dos.js`).
  - Dropdown menu for **Roommate Seeking** (`Requests` and `Make a Post`).
  - Direct links to house catalogs, rating system, and avatar management.

### 6. Property Owner Management Dashboard
- **Location:** `dashboard of owner/doo.html`, `dashboard of owner/doo.css`
- **Features:**
  - Enterprise-grade CRM interface built on modern Bootstrap utility frameworks.
  - Financial metric cards:
    - **Total Rent Revenue:** `75,000 Tk` (+13% growth indicator)
    - **New Student Tenants:** `5 Active Students` (+30% growth indicator)
    - **Hours Logged & Occupancy:** Operational health indicators
  - Tenant application table with interactive status pills (`Paid`, `Pending`, `Scheduled`).
  - Quick action toolbar (`Create Listing`, `Edit Details`).

### 7. Interactive House Listings & Discovery
- **Location:** `house/hs.html`, `house/hs.css`, `house/hs.js`
- **Features:**
  - Grid card gallery displaying rental properties with pricing formatted in Bangladeshi Taka (`Starts from: Tk 1000`).
  - Dynamic **Dark/Light Mode** switcher toggling root CSS classes with animated SVG sun and moon icons.
  - Modal window inspection (`#modal-window`) allowing students to view expanded property photography, address details, and booking triggers.

### 8. Landlord Property Listing & Flat Specification
- **Location:** `house_1/hs.html`, `house_1/hs.css`, `house_1/hs.js`
- **Features:**
  - In-depth apartment auditing form capturing:
    - Number of available flats
    - Price range in BDT (Tk)
    - Exact House Number and Road Number
    - Floor location (e.g., 2nd Floor, 4th Floor)
    - Total room count
    - Washroom specifications (Tiled vs. Non-tiled)
    - Balcony and Kitchen availability
    - Drawing and Dining room spaces
    - Security amenities: 24/7 CCTV surveillance, security guard presence, elevator/lift access
    - Monthly service charge breakdown (Tk)

### 9. Seat & Room Booking Reservation Flow
- **Location:** `booking/bk.html`, `booking/bk.css`
- **Features:**
  - Formal student reservation form capturing house numbers, target check-in dates, and agreed monthly rent.
  - Built-in house policy checklist highlighting tenant conduct agreements.

### 10. Roommate Seeking & Peer Matching
- **Location:** `roommate/rm.html`, `roommate/rm.css`
- **Features:**
  - Peer discovery form designed to find compatible flatmates.
  - Captures academic progress parameters:
    - University ID and University Email
    - Department Name
    - Number of Trimesters Completed (e.g., 3rd trimester, 8th trimester)
    - Gender preference (Male / Female bachelor mess)
    - Personal contact details and budget expectations

### 11. Interactive Animated Reaction Feedback
- **Location:** `rating/rt.html`, `rating/rt.css`
- **Features:**
  - Highly expressive SVG reaction rating component.
  - 5 interactive sentiment stages: **Angry (1)**, **Sad (2)**, **OK (3)**, **Good (4)**, and **Happy (5)**.
  - Features real-time eye tracking and mouth transformation animations on radio selection.

### 12. Document & Image Verification Uploader
- **Location:** `check.html`
- **Features:**
  - Interactive drag-and-drop file selection zone with dashed focus styling.
  - Instant file queue inspection displaying selected filenames and document payloads for student ID cards and rental deeds.

---

## Technology Stack

- **Markup & Semantics:** HTML5 (semantic layout, custom data attributes, accessible form controls)
- **Styling & Layout:**
  - CSS3 (Custom Variables, Flexbox, CSS Grid, 3D Transforms, Transition Curves)
  - Normalize.css & Meyer Reset
  - Twitter Bootstrap 3.3.7 & 4.5.2
- **Interactivity & Logic:**
  - Vanilla JavaScript (ES6+ Event Listeners, Class Toggling, DOM Selection)
  - jQuery 3.2.1 / 3.5.1
- **Icons & Typography:**
  - FontAwesome 5.14 & 5.15
  - Unicons by IconScout
  - Google Fonts (Inter, Roboto, Open Sans)

---

## Project Directory Structure

```
UIU-Rental-System/
├── index.html                     # Root entry point redirector
├── check.html                     # Drag-and-drop file & ID verification uploader
├── .gitignore                     # Git exclusion rules
├── LICENSE                        # MIT Open-Source License
├── README.md                      # Comprehensive project documentation
├── booking/                       # Room reservation & booking module
│   ├── bk.css                     # Booking form styling
│   └── bk.html                    # Booking form layout
├── dashboard of owner/            # Landlord CRM & business intelligence
│   ├── doo.css                    # Dashboard stylesheet
│   └── doo.html                   # Metrics, revenue & tenant management table
├── dashboard of student/          # Student portal & navigation
│   ├── dos.css                    # Student dashboard stylesheet
│   ├── dos.html                   # Navigation, roommate links & profile view
│   └── dos.js                     # Mobile responsive menu controller
├── house/                         # Public property catalog & discovery
│   ├── hs.css                     # Listing grid & modal stylesheet
│   ├── hs.html                    # Property cards & dark/light mode layout
│   └── hs.js                      # Theme switcher & modal controller
├── house_1/                       # Landlord property listing form
│   ├── hs.css                     # Flat details form stylesheet
│   ├── hs.html                    # Multi-attribute apartment creation form
│   ├── hs.js                      # Input validation helper
│   └── script.js                  # Additional helper scripts
├── main/                          # Public landing page
│   ├── index.html                 # Main website homepage & hero banner
│   ├── style.css                  # Homepage master stylesheet
│   ├── vs.js                      # Review carousel controller
│   └── img/                       # Graphic assets
│       ├── home.ai                # Vector artwork source
│       ├── home.png               # Hero illustration graphic
│       └── logo.png               # Platform logo
├── owner/                         # Owner registration portal
│   ├── ow.css                     # Owner signup stylesheet
│   └── ow.html                    # Owner registration form
├── rating/                        # Interactive review & feedback module
│   ├── rt.css                     # Animated SVG reaction stylesheet
│   └── rt.html                    # Expressive 5-stage emoji feedback
├── roommate/                      # Roommate matching module
│   ├── rm.css                     # Roommate seeking form stylesheet
│   └── rm.html                    # Academic & roommate preference form
├── Sign in/                       # Dual-role authentication portal
│   ├── sg.css                     # Double-sliding panel stylesheet
│   ├── sg.html                    # Sign In / Sign Up container layout
│   └── sg.js                      # Sliding animation controller
└── student/                       # Student onboarding portal
    ├── st.css                     # Student registration stylesheet
    └── st.html                    # Student registration form
```

---

## Installation & Local Deployment Guide

Because the application is built entirely on modern client-side standards (HTML5, CSS3, JavaScript), it requires **zero build tools, zero bundlers, and zero server-side runtimes** to view.

### Option 1: Direct Browser Launch
1. Clone or download the repository to your local machine:
   ```bash
   git clone https://github.com/robiultamim/Student-Room-Rental-System.git
   cd Student-Room-Rental-System
   ```
2. Double-click `index.html` or `main/index.html` to open it in your default web browser (Chrome, Edge, Firefox, Safari).

---

### Option 2: Local HTTP Server (Recommended)

#### Using Python (Built-in)
```bash
# In the project root directory:
python -m http.server 8000
```
Then visit: **[http://localhost:8000](http://localhost:8000)**

#### Using PHP (Built-in)
```bash
php -S localhost:8000
```
Then visit: **[http://localhost:8000](http://localhost:8000)**

#### Using VS Code Live Server
1. Open the project folder in **Visual Studio Code**.
2. Right-click `index.html` and click **"Open with Live Server"**.

---

### Option 3: GitHub Pages Deployment (Free Live Hosting)
1. In your GitHub repository, navigate to **Settings ➔ Pages**.
2. Under **Build and deployment** ➔ **Source**, select **`Deploy from a branch`**.
3. Choose branch: **`main`** and folder: **`/ (root)`**.
4. Click **Save**. Your site will be live at `https://robiultamim.github.io/Student-Room-Rental-System/`.

---

## Target Demographics & Academic Context

This platform was designed as an academic project at **United International University (UIU)**, catering specifically to:
- **UIU Students:** Freshers and continuing students relocating to Dhaka who need verified bachelor accommodations near campus.
- **Local Flat Owners:** Landlords in Madani Avenue, Satarkul, Beraid, Natun Bazar, and Kuril seeking reliable university student tenants.
- **Student Mess Managers:** Senior students seeking batchmates to share apartment expenses and study environments.

---

## Contributing & License

Contributions, feature suggestions, and pull requests are welcome!

1. Fork the Project.
2. Create your Feature Branch (`git checkout -b feature/NewFeature`).
3. Commit your Changes (`git commit -m 'Add NewFeature'`).
4. Push to the Branch (`git push origin feature/NewFeature`).
5. Open a Pull Request.

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for more information.

---

<p align="center">
  <b>Developed by <a href="https://github.com/robiultamim">Robiul Islam Tamim</a></b><br>
  <sub>United International University (UIU) • Department of Computer Science & Engineering</sub><br>
  <sub>Contact: <a href="mailto:robiulislamtamim12345@gmail.com">robiulislamtamim12345@gmail.com</a></sub>
</p>
