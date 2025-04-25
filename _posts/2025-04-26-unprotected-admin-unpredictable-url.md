---
layout: post
title: "Lab: Unprotected Admin Functionality with Unpredictable URL"
date: 2025-04-26 21:00:00 +0000
---

## 🧪 Lab: Unprotected Admin Functionality with Unpredictable URL

**Platform:** PortSwigger Web Security Academy  
**Difficulty:** _Easy_  
**Category:** Access Control / Information Disclosure

---

### 🔍 Lab Description

This lab features an unprotected admin panel hidden behind an unpredictable URL. Your goal is to discover the hidden route and use it to delete the user `carlos`.

---

### 📝 Steps to Solve

1. **Visited the application**  
   Accessed the lab URL and confirmed the presence of normal user functionality.

2. **Inspected the page source**  
   Viewed the HTML/JavaScript and found this snippet:

   ```js
   var isAdmin = false;
   if (isAdmin) {
     var topLinksTag = document.getElementsByClassName("top-links")[0];
     var adminPanelTag = document.createElement("a");
     adminPanelTag.setAttribute("href", "/admin-zhpiyi");
     adminPanelTag.innerText = "Admin panel";
     topLinksTag.append(adminPanelTag);
     var pTag = document.createElement("p");
     pTag.innerText = "|";
     topLinksTag.appendChild(pTag);
   }
   ```

   Although `isAdmin` is set to `false`, the code reveals that the admin panel lives at `/admin-zhpiyi`.

3. **Accessed the hidden admin panel**  
   Navigated directly to `/admin-zhpiyi`.  
   No authentication or RBAC checks were enforced.

4. **Located the user deletion function**  
   The panel listed `wiener` and `carlos`, each with a **Delete** link.

5. **Deleted the target user**  
   Clicked **Delete** next to `carlos`.  
   The lab immediately marked as solved.

---

### 🧠 Takeaways

- Client-side scripts may leak secrets or hidden routes; **never** trust them as protection.
- Even “unpredictable” URLs must be secured with **authentication** and **authorization** checks.
- Simple misconfigurations can lead to critical account manipulations in production.

---

_Reported by Mariano | <https://marianoja.github.io/hacking-blog/>_

---

## 📝 References

- [PortSwigger Web Security Academy](https://portswigger.net/web-security-academy)
