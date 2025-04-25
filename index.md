---
layout: default
title: Mariano's Hacking Blog
---

# 🧠 Welcome to my Pentest & Bug Bounty Lab

This is my personal blog where I document:

- 🧪 Web Security Academy labs
- 💰 Bug bounty findings
- ⚙️ Recon techniques
- 🛠️ Tools and automation tips

---

## 📚 Latest Writeups

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
