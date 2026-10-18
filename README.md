# 🛒 SauceDemo E-Commerce – End-to-End Manual QA Testing Suite

[![Testing Type: Manual QA](https://img.shields.io/badge/Testing%20Type-Manual%20Functional%20QA-blue.svg)](https://www.saucedemo.com)
[![Requirements Coverage: 100%](https://img.shields.io/badge/Requirements%20Coverage-100%25-brightgreen.svg)]()
[![Test Cases: 62](https://img.shields.io/badge/Test%20Cases-62-orange.svg)]()
[![Test Scenarios: 47](https://img.shields.io/badge/Test%20Scenarios-47-yellow.svg)]()
[![Defects Logged: 7](https://img.shields.io/badge/Defects%20Logged-7%20Bugs-red.svg)]()
[![Status: Final Baseline](https://img.shields.io/badge/Status-Final%20Baseline-success.svg)]()

A comprehensive, industry-standard Software Quality Assurance (SQA) project demonstrating end-to-end manual testing across the **SauceDemo** e-commerce web platform[cite: 27]. This repository contains full-lifecycle test documentation—including High-Level Requirements (HLR)[cite: 23, 31], an IEEE 829-aligned Master Test Plan[cite: 27, 31], Test Scenarios, Detailed Test Cases, a bidirectional Requirement Traceability Matrix (RTM)[cite: 23, 31], and an evaluated Bug Report covering persona-based behavioral defects[cite: 28, 31].

---

## 📌 Table of Contents
1. [Project Overview](#-project-overview)
2. [Application Under Test (AUT) & User Personas](#-application-under-test-aut--user-personas)
3. [Testing Scope](#-testing-scope)
4. [STLC Deliverables & Project Architecture](#-stlc-deliverables--project-architecture)
5. [Requirement Traceability Matrix (RTM)](#-requirement-traceability-matrix-rtm)
6. [Test Design & Execution Metrics](#-test-design--execution-metrics)
7. [Defect Reporting & Triage Analysis](#-defect-reporting--triage-analysis)
8. [Test Environment & Tool Stack](#-test-environment--tool-stack)
9. [Key QA Insights & Takeaways](#-key-qa-insights--takeaways)

---

## 📖 Project Overview

The primary objective of this project is to perform exhaustive functional, boundary, negative, and exploratory testing on the **SauceDemo** web application[cite: 27, 28]. Testing verifies the stability of core transaction funnels—from authentication to multi-step checkout—while evaluating application resilience against varied user behaviors, network latencies, and input anomalies[cite: 27, 28].

* **Application Under Test:** [SauceDemo Storefront](https://www.saucedemo.com)[cite: 30]
* **Testing Methodology:** Black-Box Manual Functional, UI/UX, Persona, Regression, and Exploratory Testing[cite: 27, 28]
* **Baseline Coverage:** 100% requirements-to-test coverage (FR01–FR11, NFR01–NFR05)[cite: 23, 24, 25]
* **Test Author:** Kalp Shah / Arpan Sircar (QA Engineering)[cite: 22, 23, 27, 31]
* **Reviewed & Approved By:** QA Lead[cite: 22, 23, 27, 31]

---

## 👥 Application Under Test (AUT) & User Personas

SauceDemo provides 6 pre-configured user profiles designed to simulate real-world e-commerce edge cases, client-side anomalies, and security constraints[cite: 23, 28]:

| Username | Password | Persona Profile & System Behavior Expected |
| :--- | :--- | :--- |
| `standard_user`[cite: 28, 30] | `secret_sauce`[cite: 30] | **Baseline User:** Standard purchasing flows execute without visual or functional defects[cite: 28]. |
| `locked_out_user`[cite: 28] | `secret_sauce` | **Access Control:** System enforces account lockout with an explicit error banner[cite: 28]. |
| `problem_user`[cite: 28] | `secret_sauce` | **UI/Asset Failures:** Injected with mismatched image URLs and broken layout grids[cite: 28]. |
| `performance_glitch_user`[cite: 28] | `secret_sauce` | **Latency Resilience:** Simulates delayed API responses, catalog lag, and sorting delays[cite: 28]. |
| `error_user`[cite: 28] | `secret_sauce` | **Functional Disruption:** Client-side JavaScript exceptions on checkout actions[cite: 28]. |
| `visual_user`[cite: 28] | `secret_sauce` | **Cosmetic Defects:** Misaligned UI elements, layout shifts, and inconsistent CSS styling[cite: 28]. |

---

## 🎯 Testing Scope

### ✅ In-Scope Modules
* **User Authentication:** Login form validation, empty-state errors, credentials sanitization, and logout session termination[cite: 23, 24, 27].
* **Product Catalog:** Inventory card loading, pricing accuracy, product descriptions, and dynamic sorting (Price / Name)[cite: 23, 27].
* **Cart Operations:** Item addition/removal from catalog and cart views, badge synchronization, and subtotal calculation[cite: 24, 27].
* **Checkout Funnel:**
  * **Step 1 (Customer Information):** Mandatory field checks (First Name, Last Name, Postal Code) and validation messaging[cite: 24, 27].
  * **Step 2 (Order Overview):** Itemized breakdown, tax estimation, and final total validation[cite: 24, 27].
  * **Order Confirmation:** Order completion screen, confirmation banner, and cart reset verification[cite: 24, 27].
* **User-Persona Testing:** Comprehensive behavioral matrix testing across all 6 demo accounts[cite: 23, 28].
* **UI/UX & Desktop Layout:** Viewport resizing, button alignment, and font/color consistency at 1920×1080 resolution[cite: 23, 24, 28, 30].

### ❌ Out-of-Scope Items
* Multi-browser compatibility testing (baselined exclusively to Google Chrome desktop)[cite: 25, 28, 32].
* Mobile devices and responsive touch emulations[cite: 28].
* Direct backend API validation and SQL database manipulation[cite: 28, 30].
* Automated script development (Selenium/Playwright/Cypress)[cite: 28].
* Load, stress, and penetration security audits[cite: 28].

---

## 📂 STLC Deliverables & Project Architecture# SauceDemo
