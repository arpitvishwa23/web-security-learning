# 🧪 DOM-Based XSS (DVWA Lab)

---

## 📌 Objective
To identify and exploit DOM-Based Cross-Site Scripting (XSS) vulnerability in DVWA using URL manipulation and client-side JavaScript injection.

---

## 🛠️ Tools Used
- DVWA (Damn Vulnerable Web Application)
- Browser (Chrome/Firefox)
- Developer Tools (Inspect Element)
- Burp Suite (optional)

---

## 📖 Vulnerability Overview
DOM XSS occurs when JavaScript takes input from the URL and directly injects it into the webpage DOM without sanitization. The attack happens completely on the client side.

---

## ⚙️ Lab Setup
- Security Level: Low
- Module: XSS (DOM Based)

---

# 🚀 Practical Steps

---

## 🔹 Step 1: Open DVWA DOM XSS Page

### 📸 Screenshot:
![DOM XSS Page](../screnshots/01-dom-xss-page.png)

---

## 🔹 Step 2: URL Manipulation

### 📸 Screenshot:
![URL Manipulation](../screnshots/02-url-manipulation.png)

---

## 🔹 Step 3: Inject Basic Payload

### Payload:
```html
#<script>alert(1)</script>