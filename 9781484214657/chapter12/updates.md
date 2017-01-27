---
layout: page
Title: Live Updates
---

### **Current Updates** - {{ site.current_crisis }} - [Live reporting](http://jekyll-mini-blog.github.io/)

---

### **Previous updates:**

<ul>
{% for disease in site.data.previous %}
  <li>
    {{ disease.name }} - {{ disease.link }}
    </a>
  </li>
{% endfor %}
</ul>