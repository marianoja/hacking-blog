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

- **robots.txt** es para indexación, **no** es un control de seguridad.
- Todo admin panel **debe** protegerse con autenticación y RBAC.
- Un fallo tan sencillo puede tener impacto crítico en producción.

---

_Reported by Mariano | <https://marianoja.github.io/hacking-blog/>_

---

## 📝 References

- [PortSwigger Web Security Academy](https://portswigger.net/web-security-academy)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP ZAP](https://www.owasp.org/index.php/OWASP_ZAP_Project)
- [OWASP Dependency Check](https://owasp.org/www-project-dependency-check/)
- [OWASP Dependency Check - Maven Plugin](https://github.com/owasp/dependency-check-maven)
- [OWASP Dependency Check - Gradle Plugin](https://github.com/OWASP/dependency-check-gradle)
- [OWASP Dependency Check - Gradle Plugin](https://github.com/
