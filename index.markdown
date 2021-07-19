---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

{% assign sorted_posts = site.categories | sort %}
{% for category in sorted_posts %}
  <h2>{{ category[0] }}</h2>
  <ul>
    {% assign sorted_posts = category[1] | sort: post.title %}
    {% for post in sorted_posts %}
      <li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}