# Quiz Questions and Answers

## 📊 Data Anonymization

**What is the primary goal of data anonymization?**

The main goal is to **protect private information** by:
- Removing or hiding details that link data to a specific person
- Allowing data to remain useful for research
- Making it extremely difficult to identify individuals involved

---

## 🏛️ The Havasupai Tribe Case

**What is the Havasupai Tribe case about?**

Researchers from **Arizona State University** collected blood samples from the Havasupai Tribe to study diabetes. 

**What went wrong:**
- Samples were used for **unapproved research** on:
  - Schizophrenia
  - Ancestry
- No permission was requested
- Violated the tribe's trust and rights
- **Result:** Lawsuit and settlement in **2010**

---

## 🚨 Largest Health Data Breach

**What was the largest health data breach in history?**

> **Anthem Inc. (2015)**
> - Hackers accessed personal information
> - **78.8 million people** affected

---

## 🩺 Pulse Oximeter Controversy

**What is the pulse oximeter controversy about?**

Studies found pulse oximeters were **nearly 3x more likely** to miss low blood oxygen levels in Black patients compared to White patients.

**Why this happened:**
- Device algorithms based mostly on data from light-skinned individuals
- Example of **algorithmic bias** in medical devices

---

## 🔬 Institutional Review Board (IRB)

**What is the role of an IRB in research?**

An IRB reviews research plans to ensure they are ethical. They serve as:
- **Gatekeepers** to protect participants
- Protectors of rights and safety
- Ethical oversight committee

---

## 💻 Spreadsheet vs Database Software

**What is the difference between spreadsheet software and database software for health data management?**

> ⚠️ *The provided text does not contain information about the differences between spreadsheet and database software.*

---

## ⚖️ Conflict of Interest

**What is a conflict of interest in public health research?**

A conflict of interest happens when a researcher has a **secondary interest** that might unfairly influence their work:
- Financial gain
- Personal advancement
- Other competing interests

### Main Concern
The primary worry is that these conflicts can lead to:
1. **Biased results**
2. Compromise of research integrity
3. Damage to public trust in health institutions

### Managing Conflicts of Interest

**Step 1: Transparency**
- Researchers must **openly disclose** any potential conflicts
- Financial ties
- Personal relationships
- Must be disclosed **before starting work**

**Step 2: Independent Oversight**
- Separate committee reviews and monitors research
- Adds extra layer of scrutiny
- Ensures conflicts don't negatively affect the study

**Step 3: Mitigation Strategies**
- **Divestment:** Researcher sells off or removes the financial interest causing the conflict

**Consequences of Poor Management:**
- Biased research findings
- Loss of public confidence in science
- Damage to reputation of research community

---

## 🔐 Informed Consent

**What is informed consent in the context of health data collection?**

Informed consent means providing individuals with **enough information** to make an educated choice about sharing their data.

**Must include:**
- Purpose of the collection
- How the data will be used
- Any potential risks

---

## 🎭 De-identification Techniques

### Data Masking

**What is data masking?**
- Replacing personal details with random characters
- Removing details completely
- **Example:** A name might be replaced with XXX

### K-Anonymity

**What is the principle of k-anonymity?**

This technique **groups data** so that each category contains at least a certain number of records.

**How it works:**
- Makes it hard to single out any specific individual
- Each person is indistinguishable from at least *k-1* other records
- **Example:** If k=5, you cannot tell a specific person apart from at least 4 others with the same:
  - Age range
  - Zip code
  - Gender

---

# 📋 Case Studies

## 1️⃣ The Misuse of Health Data: Project Nightingale

### Event
**Project Nightingale** involved a partnership between **Google and Ascension** (a large Catholic health system).

**Timeline:** 2018-2019

**Data collected:**
- Personal health records of **millions of Americans** across **21 states**
- Names
- Dates of birth
- Lab results
- Hospitalization records

**Purpose:** Google used this data to:
- Design new software
- Train artificial intelligence

### Ethical Issues
The main issue was **lack of transparency**:
- ❌ Patients were NOT informed
- ❌ Doctors were NOT informed
- ✅ Technically followed HIPAA privacy laws
- ⚠️ Raised concerns about patient trust and data sharing without explicit permission

### Prevention
This could have been prevented by:
1. **Requiring explicit patient consent** before sharing identifiable data with third parties
2. **Removing personal identifiers** (anonymization) before transferring data
3. Protecting patient privacy through de-identification

---

## 2️⃣ Breaches in Health Data Security: Change Healthcare

### Event
**February 2024** - Change Healthcare (subsidiary of UnitedHealth Group) suffered a **massive cyberattack**

**Attacker:** BlackCat ransomware group

**Vulnerability:** Attackers gained access through a remote portal that **did NOT have multi-factor authentication** enabled

### Consequences
- **1 in 3 Americans** had their data compromised
- Paralyzed **US healthcare billing system for weeks**
- Prevented pharmacies from processing prescriptions
- Stopped payments to hospitals
- **Stolen data:**
  - Social Security numbers
  - Medical records
  - Other sensitive information

### Prevention
**Primary method:** Enforce **multi-factor authentication (MFA)** on all remote access points

**Additional measures:**
- Regular security audits
- Better network segmentation
- Limited hacker movement within systems

---

## 3️⃣ Bias in Health Data: Kidney Function Formula (eGFR)

### Event
For years, the formula used to measure **kidney function (eGFR)** included a **race adjustment**.

**The problem:**
- Mathematical calculation automatically scored Black patients as having **better kidney function** than non-Black patients
- Based on **flawed assumptions** about muscle mass differences
- Same blood test results = different interpretations based on race

### Consequences
This bias led to:
- Black patients diagnosed with kidney disease at **later stages**
- Kidney function was **overestimated**
- **Delays in:**
  - Getting referred to specialists
  - Being placed on transplant waitlists
  - Starting dialysis

### Prevention
Medical institutions can prevent this by:
1. **Removing race variables** from clinical algorithms
   - *National Kidney Foundation recommended this in 2021*
2. Using **alternative markers** like **cystatin C**
   - Does not rely on race
   - Provides more fair and accurate assessment for everyone

---

## 4️⃣ Anonymization of Health Data: K-Anonymity Technique

### Technique
**K-anonymity**

### Description
This method involves **grouping data** so that any individual record is indistinguishable from at least **k-1 other records** in the same dataset.

**Example:**
If k = 5, a researcher looking at the data **cannot tell a specific person apart** from at least 4 other people who share the same:
- Age range
- Zip code
- Gender

**Benefit:**
Makes it much harder to **re-identify someone** by combining health data with public records like voter lists.

---

# 🏛️ The George Washington University Office of Human Research

## Overview
The **Office of Human Research (OHR)** at George Washington University serves as administrative support for the university's **Institutional Review Boards (IRBs)**.

## Primary Purpose
**Protect the rights and welfare of human subjects** involved in research

## Key Responsibilities

The office ensures that all research conducted by GW faculty, staff, and students complies with:
- ✅ Ethical standards
- ✅ Federal regulations

### Before Any Study Begins
The OHR reviews the proposal to confirm:
1. Participants are treated **fairly**
2. Risks are **minimized**
3. **Informed consent** is properly obtained

## Role
They act as the **ethical gatekeepers** for the university's research community.

---

## 📝 Summary

> This document covers critical topics in health data ethics, including anonymization techniques, historical cases of data misuse, security breaches, algorithmic bias, and the role of institutional oversight in protecting research participants.