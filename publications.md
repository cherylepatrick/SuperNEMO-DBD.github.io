---
layout: page
title: Publications
---

List papers and other media such as presentations. Title could be "Media" 
or a better word to reflect the mix.

Formatting/layout very basic, just illustrates that we can generate a list
from a [Jekyll collection](http://jekyll.tips/jekyll-casts/introduction-to-collections/) 
of simple Markdown/YAML files. Each element in the collection is simply
stuck into a list. We could also output each element to a separate
page with short links here.

Another way to do this would be though [Jekyll data](http://jekyll.tips/jekyll-casts/data-files/)
if maintaining a JSON/CSV list is easier.

Publications
------------
{% assign pubs_by_date = (site.publications | sort:"date") | reverse %}
{% for pub in pubs_by_date %}
- **{{ pub.title }}**
  - __{{ pub.journal }}__
  - {{ pub.date }}
  - {{pub.abstract}}
{% endfor %}
