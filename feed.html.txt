---
#  feed.txt format; see https://feedtxt.github.io for more

layout: null
---
|<<<
 title:         {{ site.title }}
 home_page_url: {{ "/" | absolute_url }}
 feed_url:      {{ "/feed.txt" | absolute_url }}
 </>
 {% for post in site.posts limit:10 %}
  id:    {{ post.url | absolute_url }}
  title: {{ post.title }}
  url:   {{ post.url | absolute_url }}
  published: {{ post.date | date_to_xmlschema }}
  ---
{{ post.content }}
  {% if forloop.last == false %}</>{% endif %}
{% endfor %}
>>>|
