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

### 🔍 Lab Description

The objective of this lab is to identify and exploit an unprotected admin interface in order to delete the user `carlos`.

---

### 📝 Steps to Solve

1. **Visited the application**  
   Accessed the lab-provided URL and confirmed the goal: delete user `carlos`.

2. **Checked `robots.txt` for hidden paths**

   ```txt
   User-agent: *
   Disallow: /administrator-panel
   ```

   This revealed a potentially sensitive admin area.

3. **Accessed the administrator panel**  
   Visited `/administrator-panel` directly and found **no** authentication or authorization checks.

4. **Found the Delete function**  
   The panel listed users (`wiener`, `carlos`) each with a **Delete** link.

5. **Deleted the target user**  
   Clicked **Delete** next to `carlos`.  
   The lab immediately marked as solved.

---

### 🧠 Takeaways

- **robots.txt** is for indexing, it is **not** a security check.
- All admin panel **must be** protected with authentication and RBAC.
- Such a simple failure can have a critical impact on production..

---

_Reported by Mariano | <https://marianoja.github.io/hacking-blog/>_

---

## 📝 References

- [PortSwigger Web Security Academy](https://portswigger.net/web-security-academy)
