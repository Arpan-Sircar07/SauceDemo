# 🛒 SauceDemo E-Commerce – End-to-End Manual QA Testing Suite

[![Testing Type: Manual QA](https://img.shields.io/badge/Testing%20Type-Manual%20Functional%20QA-blue.svg)](https://www.saucedemo.com)
[![Requirements Coverage: 100%](https://img.shields.io/badge/Requirements%20Coverage-100%25-brightgreen.svg)]()
[![Test Cases: 62](https://img.shields.io/badge/Test%20Cases-62-orange.svg)]()
[![Test Scenarios: 47](https://img.shields.io/badge/Test%20Scenarios-47-yellow.svg)]()
[![Defects Logged: 7](https://img.shields.io/badge/Defects%20Logged-7%20Bugs-red.svg)]()
[![Status: Final Baseline](https://img.shields.io/badge/Status-Final%20Baseline-success.svg)]()

A comprehensive Software Quality Assurance (SQA) project demonstrating end-to-end manual testing across the **SauceDemo** e-commerce web platform. This repository contains full-lifecycle test documentation—including High-Level Requirements (HLR), an IEEE 829-aligned Master Test Plan, Test Scenarios, Detailed Test Cases, a bidirectional Requirement Traceability Matrix (RTM), and an evaluated Bug Report covering persona-based behavioral defects.

---

## 📌 Table of Contents
1. [Project Overview](#-project-overview)
2. [Application Under Test (AUT) & User Personas](#-application-under-test-aut--user-personas)
3. [Testing Scope](#-testing-scope)
4. [Project Deliverables & Repository Structure](#-project-deliverables--repository-structure)
5. [Requirement Traceability Matrix (RTM)](#-requirement-traceability-matrix-rtm)
6. [Test Design & Execution Metrics](#-test-design--execution-metrics)
7. [Defect Reporting & Triage Analysis](#-defect-reporting--triage-analysis)
8. [Test Environment & Technical Setup](#-test-environment--technical-setup)
9. [Key QA Insights](#-key-qa-insights)

---

## 📖 Project Overview

The primary objective of this project is to perform exhaustive functional, boundary, negative, and exploratory testing on the **SauceDemo** web application. Testing verifies the stability of core transaction funnels—from authentication to multi-step checkout—while evaluating application resilience against varied user behaviors, network latencies, and input anomalies.

* **Application Under Test:** [SauceDemo Storefront](https://www.saucedemo.com)
* **Testing Methodology:** Black-Box Manual Functional, UI/UX, Persona, Regression, and Exploratory Testing
* **Baseline Coverage:** 100% requirements-to-test coverage (FR01–FR11, NFR01–NFR05)
* **Test Author:** Kalp Shah / Arpan Sircar (QA Engineering)
* **Reviewed & Approved By:** QA Lead

---

## 👥 Application Under Test (AUT) & User Personas

SauceDemo provides 6 pre-configured user profiles designed to simulate real-world e-commerce edge cases, client-side anomalies, and security constraints:

| Username | Password | Persona Profile & Expected System Behavior |
| :--- | :--- | :--- |
| `standard_user` | `secret_sauce` | **Baseline User:** Standard purchasing flows execute without visual or functional defects. |
| `locked_out_user` | `secret_sauce` | **Access Control:** System enforces account lockout with an explicit error banner. |
| `problem_user` | `secret_sauce` | **UI/Asset Failures:** Injected with mismatched image URLs and broken layout grids. |
| `performance_glitch_user` | `secret_sauce` | **Latency Resilience:** Simulates delayed API responses, catalog lag, and sorting delays. |
| `error_user` | `secret_sauce` | **Functional Disruption:** Client-side JavaScript exceptions on checkout actions. |
| `visual_user` | `secret_sauce` | **Cosmetic Defects:** Misaligned UI elements, layout shifts, and inconsistent CSS styling. |

---

## 🎯 Testing Scope

### In-Scope Modules
* **User Authentication:** Login form validation, empty-state errors, credential sanitization, and logout session termination.
* **Product Catalog:** Inventory card loading, pricing accuracy, product descriptions, and dynamic sorting (Price / Name).
* **Cart Operations:** Item addition/removal from catalog and cart views, badge synchronization, and subtotal calculation.
* **Checkout Funnel:**
  * **Step 1 (Customer Information):** Mandatory field checks (First Name, Last Name, Postal Code) and validation messaging.
  * **Step 2 (Order Overview):** Itemized breakdown, tax estimation, and final total validation.
  * **Order Confirmation:** Order completion screen, confirmation banner, and cart reset verification.
* **User-Persona Testing:** Comprehensive behavioral matrix testing across all 6 demo accounts.
* **UI/UX & Desktop Layout:** Viewport resizing, button alignment, and font/color consistency at 1920×1080 resolution.

### Out-of-Scope Items
* Multi-browser compatibility testing (baselined exclusively to Google Chrome desktop).
* Mobile devices and responsive touch emulations.
* Direct backend API validation and SQL database manipulation.
* Automated script development (Selenium/Playwright/Cypress).
* Load, stress, and penetration security audits.

---

## 📂 Project Deliverables & Repository Structure

The complete test lifecycle artifacts included in this repository:

```text
├── 📄 SauceDemo_Requirements_.pdf        # High-Level Requirements (FR01-FR11, NFR01-NFR05)
├── 📄 SauceDemo_TestPlan.pdf             # Master Test Plan (Scope, Strategy, Entry/Exit Criteria)
├── 📄 TEST PLAN – SAUCEDEMO WEBSITE.docx # Editable Word Document of the Master Test Plan
├── 📊 SauceDemo_Test_Scenarios.xlsx      # 47 High-Level Test Scenarios across 11 functional modules
├── 📊 SauceDemo_TestCases.xlsx           # 62 Detailed Test Cases (Steps, Test Data, Expected Results)
├── 🔗 RTM - SAUDEMO WEBSITE.xlsx         # Bidirectional Requirements Traceability Matrix
├── 🐞 SauceDemo_Bug_Report.xlsx          # 7 Documented Bugs with Steps, Severity, Priority & Evidence
└── 📘 README.md                          # Project Documentation and Summary Showcase
```

---

## 🔗 Requirement Traceability Matrix (RTM)

The RTM ensures bidirectional traceability linking functional requirements (`SauceDemo_Requirements_.pdf`) to test scenarios (`SauceDemo_Test_Scenarios.xlsx`), test cases (`SauceDemo_TestCases.xlsx`), and logged execution results:

| Req ID | Requirement Description | Test Scenarios | Test Cases | Execution Status | Core QA Findings & Status |
| :---: | :--- | :---: | :---: | :---: | :--- |
| **FR01** | User Login Functionality | TS01–TS07 | TC01–TC07 | Pass / Blocked | Normal login passes; `locked_out_user` correctly blocked. |
| **FR02** | Demo User Behavior Verification | TS08–TS14 | TC08–TC14 | Mixed (Pass/Fail) | Successfully captured expected anomalies across demo personas. |
| **FR03** | Product Listing & Details | TS15–TS19 | TC15–TC19 | Fail (problem_user) | Broken/mismatched image assets identified for `problem_user`. |
| **FR04** | Catalog Sorting Functionality | TS20–TS23 | TC20–TC23 | Fail (glitch_user) | Sorting delays and latency issues isolated for `performance_glitch_user`. |
| **FR05** | Cart Operations & Badge Sync | TS24–TS29 | TC24–TC29 | Pass | Stable cart addition and removal behavior verified. |
| **FR06** | Cart Summary & Calculations | TS30–TS32 | TC30–TC32 | Pass | Subtotal, item calculations, and pricing display accurately. |
| **FR07** | Checkout Step 1 (User Details) | TS33–TS35 | TC33–TC35 | Fail (error_user) | Form field submission blocked on `error_user` account. |
| **FR08** | Checkout Step 2 (Order Summary)| TS36–TS39 | TC36–TC39 | Fail (error_user) | Overview validation fails under `error_user` account. |
| **FR09** | Order Completion & Receipt | TS40–TS42 | TC40–TC42 | Fail (error_user) | Order dispatch fails to finalize for `error_user`. |
| **FR10** | Logout & Session Termination | TS43–TS44 | TC43–TC44 | Pass | Session cache terminates securely; direct URL access restricted. |
| **FR11** | UI/UX & Layout Integrity | TS45–TS47 | TC45–TC47 | Fail (visual/problem) | Misalignments, typography shifts, and broken spacing logged. |

---

## 📊 Test Design & Execution Metrics

### 1. Test Case Distribution by Module (62 Test Cases Total)
* **Demo Users:** 8 Test Cases
* **Login & Authentication:** 7 Test Cases
* **Product Catalog:** 7 Test Cases
* **Catalog Sorting:** 6 Test Cases
* **Cart Operations:** 6 Test Cases
* **Checkout Step 2 (Overview):** 5 Test Cases
* **Order Completion:** 5 Test Cases
* **Cart Summary Calculations:** 4 Test Cases
* **Checkout Step 1 (User Info):** 4 Test Cases
* **UI & Responsive Layout:** 3 Test Cases
* **Security & Session Management:** 3 Test Cases
* **Logout Verification:** 2 Test Cases
* **Performance & Latency:** 2 Test Cases

### 2. Test Case Distribution by Priority
* **High Priority (P1):** 26 Test Cases (41.9%)
* **Medium Priority (P2):** 22 Test Cases (35.5%)
* **Low Priority (P3):** 14 Test Cases (22.6%)

### 3. Test Cases by Scenario Type
* **Functional:** 29
* **UI / Layout:** 13
* **Negative:** 6
* **Security:** 5
* **Performance:** 3
* **Validation:** 3
* **Positive:** 2
* **Exploratory:** 1

---

## 🐞 Defect Reporting & Triage Analysis

A total of **7 defects** were identified, categorized, and recorded in `SauceDemo_Bug_Report.xlsx`:

| Bug ID | Module | Affected Persona | Severity | Priority | Defect Summary / Observed Behavior | Status |
| :---: | :--- | :--- | :---: | :---: | :--- | :---: |
| **BUG-001** | Products | `problem_user` | Medium | P2 | Broken/mismatched image assets loaded on the product inventory grid. | **OPEN** |
| **BUG-002** | UI / Products | `problem_user` | Low | P3 | Product grid layout shifts; irregular item spacing disrupts visual consistency. | **OPEN** |
| **BUG-003** | Sorting | `performance_glitch_user` | Medium | P2 | Sorting options experience unhandled UI delay or fail to rearrange promptly. | **OPEN** |
| **BUG-004** | Performance | `performance_glitch_user` | Medium | P2 | Navigation between inventory and detail views exhibits significant system lag. | **OPEN** |
| **BUG-005** | Checkout | `error_user` | High | P1 | Critical failure during Checkout steps; unhandled error blocks order submission. | **OPEN** |
| **BUG-006** | Login | `locked_out_user` | High | P1 | User account locked out; all downstream end-to-end scenarios blocked. | **BLOCKED** |
| **BUG-007** | UI / Styles | `visual_user` | Medium | P2 | Fonts, button borders, and styling attributes deviate from UI baselines. | **OPEN** |

### Severity & Priority Classification Standards
* **Critical / Blocker (P1):** Complete system blockage or broken transaction funnels with no viable workaround.
* **High (P1/P2):** Significant operational defect heavily impairing primary shopping flows.
* **Medium (P2):** Secondary workflow degradation, latency lag, or non-blocking functional flaws.
* **Low (P3):** Cosmetic inconsistencies, font deviations, or minor alignment flaws.

---

## 💻 Test Environment & Technical Setup

* **Operating System:** Microsoft Windows 11 Pro 64-bit (Build 26200, UEFI, Secure Boot Enabled)
* **Hardware Platform:** HP ProBook 440 G9 (Intel Core i5-1235U, 12th Gen, 10 Cores, 16 GB RAM)
* **Target Web Browser:** Google Chrome Version 142.0.7444.176 (Official Build, 64-bit)
* **Display Configuration:** 1920 × 1080 (Full HD, 100% DPI Scaling)
* **Network Baseline:** High-Speed Broadband / Wi-Fi (Direct connection, no VPN/Proxy)
* **QA Tools:** Microsoft Excel, Microsoft Word, Chrome DevTools, Windows Snipping Tool

---

## 💡 Key QA Insights

1. **User Persona Testing:** Utilizing specific user profiles allowed targeted isolation of distinct failure modes—from client-side JavaScript execution errors (`error_user`) to asset delivery issues (`problem_user`) and network latency simulations (`performance_glitch_user`).
2. **Defect-Driven Traceability:** Implementing a bidirectional RTM linked test coverage directly to requirement IDs, making test progression transparent and identifying release-blocking defects quickly.
3. **Boundary Value & Negative Testing:** Form boundary checks on postal codes and customer details demonstrated the importance of validating client-side input sanitization before requests reach the order summary stage.
4. **Structured Test Documentation:** Creating formalized IEEE 829-aligned test plans ensured clear entry, suspension, and exit criteria across all execution cycles.
