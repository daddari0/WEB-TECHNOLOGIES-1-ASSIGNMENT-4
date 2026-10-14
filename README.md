# Assignment #4: Forms and Validation (HTML + Bootstrap)

> **Course:** Web Technologies 1 (Front End) &bull; Fall 2026  
> **Instructor:** Alexey Fedenko  
> **Student:** Abay Amirzhanuly  
> **Group:** IT-2510  
> **Institution:** Astana IT University  

---

## 📌 Project Overview

This repository contains the complete implementation for **Assignment #4: Forms and Validation (HTML + Bootstrap)**. The assignment focuses on building responsive form layouts, implementing native HTML5 validation constraints with CSS `:user-invalid` without JavaScript or regex `pattern` attributes, and conducting an accessibility & usability audit of a legacy form.

---

## 🗂️ Project Structure

```text
assignment4web/
├── index.html          # Overview landing portal with criteria breakdown
├── task1.html          # Task 1: Book a train ticket (Bootstrap forms + custom CSS)
├── task2.html          # Task 2: Registration for AITU Hack 2026 (Native HTML5 validation)
├── task3.html          # Task 3: Fix a bad form (14-point audit & rebuilt accessible form)
├── css/
│   └── style.css       # Core styling, Montserrat font, :user-invalid/:user-valid rules
├── .gitignore          # Ignores screenshots, local docx reports, and caches
└── README.md           # Documentation and defense cheatsheet
```

---

## 🚀 How to Run Locally

You can run any static HTTP server from the project directory:

```bash
cd ~/assignmentswebt/assignment4web
python3 -m http.server 8080
```

Open your browser and navigate to:
* **Overview:** `http://localhost:8080/index.html`
* **Task 1:** `http://localhost:8080/task1.html`
* **Task 2:** `http://localhost:8080/task2.html`
* **Task 3:** `http://localhost:8080/task3.html`

---

## 🎯 Task Highlights & Defense Cheat Sheet

### Task 1: Book a train ticket
* **Color Palette:** `#0F6B5F`, `#F2A93B`, `#16302B`, `#F4F7F5`, `#E6EFEC`.
* **Font:** Google Fonts *Montserrat*.
* **Radio Segmented Pill:** Two native radio inputs (`trip_type`) styled as toggle pills with full keyboard focus support.
* **Responsive Button Ordering:**
  * Implemented using Bootstrap utilities: `d-flex flex-column-reverse flex-md-row justify-content-md-end gap-2`.
  * On a phone (<576px / 375px), **"Find trains" is above "Clear"** without changing the HTML DOM order.
* **Fields:** Required validation on From, To, Departure, Carriage class, Phone (+7 addon), Email, and Rules agreement. "Clear" button is `type="reset"`.

### Task 2: AITU Hack 2026 Registration
* **Strict Constraint:** 100% native HTML5 attributes only. **No JavaScript, no `novalidate`, and no regex `pattern` attribute**.
* **Key Attributes Used:**
  * `step="1800"` for `<input type="time">` enforces 30-minute intervals (1800 seconds) between 09:00 and 18:00.
  * `min="16" max="30" step="1"` for whole-number age.
  * `min="1" max="4" step="1"` for team size.
  * `min="0" max="5000" step="500"` for entry fee.
  * `min="2026-11-20" max="2026-11-22"` for arrival date.
  * `minlength="50" maxlength="300"` for motivation statement.
* **User-Friendly Error Timing:**
  * Bootstrap hides `.invalid-feedback` by default.
  * Pure CSS rule: `input:user-invalid ~ .invalid-feedback { display: block; }` ensures errors and red borders appear **only after the user interacts with the field**, never on page load.

### Task 3: Fix a bad form
* **14 Distinct Defects Audited:**
  1. Missing `<label>`, `id`, `name` on Name field.
  2. Wrong `type="text"` instead of `type="email"` (no mobile `@` key, no validation).
  3. Disconnected `<label>` on phone (no `for="phone"` attribute) and `type="text"` instead of `type="tel"`.
  4. ID Mismatch between `<label for="guests">` and `<input id="people">` (plus alternative fix).
  5. Duplicate ID `id="date"` on lines 10 and 12 violating W3C standards.
  6. Date input using `type="text"` instead of `type="date"`.
  7. Radio buttons with different `name` attributes (`name="inside"` vs `name="terrace"`), breaking exclusive selection.
  8. Radio buttons with text outside labels (tiny unclickable tap targets).
  9. Non-semantic `<p>Seating:</p>` instead of `<fieldset>` and `<legend>`.
  10. `<select>` missing label, name, id, and option values.
  11. `<textarea>` missing label, id, and name.
  12. Checkbox missing label connection and `required` attribute.
  13. Fake button built with `<div>` instead of `<button type="submit">` (plus alternative fix).
  14. `<form>` missing `action` and `method` attributes.
* **2 Alternative Fixes Provided:**
  * For Problem #4 (Guests label mismatch) and Problem #13 (Div fake button) with thorough architectural reasoning.
* **W3C Valid & Keyboard Accessible:** Form passes W3C markup validation and is 100% navigable with Tab, Space, and Enter keys.
# WEB-TECHNOLOGIES-1-ASSIGNMENT-4
