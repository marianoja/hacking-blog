---
layout: post
title: "Lab: Unprotected Admin Functionality"
date: 2025-04-25 04:15:00 +0000
---

## 🧪 Lab: Unprotected Admin Functionality

**Platform:** PortSwigger Web Security Academy  
**Difficulty:** _Very easy_  
**Category:** Access Control / Information Disclosure

---

## 🔍 Lab Description

The objective of this lab is to identify and exploit an unprotected admin interface in order to delete the user `carlos`.

---

## 📝 Steps to Solve

1. **Visited the application**

   Accessed the lab-provided URL and confirmed the goal: delete user `carlos`.

2. **Checked for sensitive paths**

   Navigated to `/robots.txt` and found the following directive:

   User-agent: \* Disallow: /administrator-panel

This indicated a potentially sensitive or hidden admin area.

3. **Accessed the administrator panel**

Visited `/administrator-panel` directly.  
Found an admin interface with no authentication or authorization controls.

4. **Located user deletion options**

The admin panel displayed a list of users (`wiener`, `carlos`) with a **Delete** link.

5. **Deleted the target user**

Clicked on the **Delete** link for user `carlos`.  
The action completed successfully, and the lab was marked as solved.

---

## 🧠 Takeaways

- `robots.txt` can inadvertently expose sensitive paths; it’s a privacy mechanism, **not a security control**.
- Admin panels should always be protected by **authentication** and **role-based access control (RBAC)**.
- Even low-hanging bugs like this can have critical impact in real-world applications.

---
