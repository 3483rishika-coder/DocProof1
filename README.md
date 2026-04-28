

***

# 🛡️ DocProof | The Cryptographic Standard

**DocProof** is a high-security, browser-based cryptographic vault designed for the post-truth era. It converts digital assets into immutable cryptographic facts by anchoring them to a distributed ledger. Using a "Zero-Knowledge" architecture, DocProof processes all sensitive data locally in your browser—your files never leave your device, only their cryptographic fingerprints do.



## 🚀 Live Demo
**[doc-proof.netlify.app]**

---

## ✨ Key Features

### 🛡️ Core Verification
* **SHA-256 Anchoring:** Generates unique cryptographic fingerprints for any file type.
* **Shannon Entropy Analysis:** Real-time calculation of data randomness to detect encryption or compression levels.
* **Distributed Ledger:** Permanent, real-time synchronization of "Sealed" nodes using Supabase.
* **IPFS Integration:** Automatic generation of Content Identifiers (CIDv1) for decentralized storage readiness.

### 🔐 Advanced Security Modules
* **WebAuthn Bio-Link:** Bind a document’s signature to your physical identity using FaceID, TouchID, or Windows Hello.
* **AES-256 Encryption:** Secure files with military-grade encryption directly in the browser.
* **Zero-Trust Sharding:** Split binary buffers into multiple unreadable shards for distributed storage.
* **Steganographic Vault:** Hide secret text messages inside the raw bytes of any file.
* **GPS Anchor:** Cryptographically bind real-world coordinates to a file's metadata.

### 🖼️ Forensic Tools
* **Neural Watermarking:** Protect images from AI scraping by injecting mathematical noise.
* **EXIF Sanitizer:** Strip all hidden metadata (GPS, camera info, timestamps) from image files.
* **Live Byte Frequency:** Real-time histogram visualization of file binary data.
* **Self-Destruct Sequence:** Wipe file buffers from browser memory on a customizable timer.

---

## 🛠️ Tech Stack

* **Frontend:** [React.js](https://reactjs.org/) (via CDN)
* **Styling:** [Tailwind CSS](https://tailwindcss.com/)
* **Database & Auth:** [Supabase](https://supabase.com/)
* **Icons:** [Lucide React](https://lucide.dev/)
* **Cryptography:** Web Crypto API (Native Browser)
* **Deployment:** [Vercel](https://vercel.com/) / [Netlify](https://www.netlify.com/):

## Core Languages
* **HTML5**: Used for the foundational structure of the document, including the `head` metadata and the `root` container for the React application.
* **CSS3**: Used for custom styling, including complex animations (like the laser sweep), glassmorphism effects (`liquid-glass`), and the custom cursor behavior.
* **JavaScript (ES6+)**: The primary language for the application logic, handling file processing, cryptographic functions (SHA-256 hashing), and integration with the Supabase database.

---

## Language Extensions & Frameworks
* **JSX (JavaScript XML)**: Used within the React components to write HTML-like code directly inside JavaScript.
* **Tailwind CSS**: A utility-first CSS framework used via a CDN script for rapid UI development and layout management.
* **Babel**: While a compiler rather than a language, it is used here to transpile the **JSX** and modern JavaScript so the browser can execute it.

## Technical Details
The file also interfaces with several **web APIs** using JavaScript, which are essential to its functionality:
* **Web Crypto API**: For generating SHA-256 hashes and AES-256 encryption.
* **WebAuthn API**: For the biometric DNA-link simulation.
* **Geolocation API**: To capture coordinates for the GPS Anchor.
* **Canvas API**: Used to render the "Forensic Ghost Image" byte frequency histogram.



---

## ⚙️ Local Setup

Since DocProof is a single-page application, getting it running is simple:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/YOUR_USERNAME/docproof.git
    ```
2.  **Navigate to the folder:**
    ```bash
    cd docproof
    ```
3.  **Open in Browser:**
    Simply open `index.html` in any modern web browser.

---

## 🔌 Database Configuration

To use your own backend, update the following constants in `index.html`:

```javascript
const supabaseUrl = 'https://rjnolzmhitlcawtsgvwk.supabase.co';
const supabaseKey = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InJqbm9sem1oaXRsY2F3dHNndndrIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzcyMDcxNDEsImV4cCI6MjA5Mjc4MzE0MX0.TMatVjTaxuPRCxUDdfmXJ2xSaxNY32rzNZa91ghKGfI';
```

### Required Database Schema
Create a table named `registry` in your Supabase SQL editor:

```sql
create table registry (
  id uuid default uuid_generate_v4() primary key,
  created_at timestamp with time zone default timezone('utc'::text, now()) not null,
  name text,
  hash text,
  author text,
  metadata jsonb
);
```

---
