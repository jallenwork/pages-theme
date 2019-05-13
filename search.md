---
layout: docs
---
<h1>Search Results</h1>
<p>Your search term was found on the following pages:</p>
<div>
<ul id="search-results"></ul>
<script>
  window.store = {
    {% for doc in site.docs %}
      "{{ doc.url | slugify }}": {
        "title": "{{ doc.title | xml_escape }}",
        "author": "{{ doc.author | xml_escape }}",
        "category": "{{ doc.category | xml_escape }}",
        "content": {{ doc.content | strip_html | strip_newlines | jsonify }},
        "url": "{{ site.github.url }}{{ doc.url }}"
      }
      {% unless forloop.last %},{% endunless %}
    {% endfor %},
    {% for doc in site.tutorials %}
      "{{ doc.url | slugify }}": {
        "title": "{{ doc.title | xml_escape }}",
        "author": "{{ doc.author | xml_escape }}",
        "category": "{{ doc.category | xml_escape }}",
        "content": {{ doc.content | strip_html | strip_newlines | jsonify }},
        "url": "{{ site.github.url }}{{ doc.url }}"
      }
      {% unless forloop.last %},{% endunless %}
    {% endfor %},
    {% for doc in site.api %}
      "{{ doc.url | slugify }}": {
        "title": "{{ doc.title | xml_escape }}",
        "author": "{{ doc.author | xml_escape }}",
        "category": "{{ doc.category | xml_escape }}",
        "content": {{ doc.content | strip_html | strip_newlines | jsonify }},
        "url": "{{ site.github.url }}{{ doc.url }}"
      }
      {% unless forloop.last %},{% endunless %}
    {% endfor %},
    {% for doc in site.posts %}
      "{{ doc.url | slugify }}": {
        "title": "{{ doc.title | xml_escape }}",
        "author": "{{ doc.author | xml_escape }}",
        "category": "{{ doc.category | xml_escape }}",
        "content": {{ doc.content | strip_html | strip_newlines | jsonify }},
        "url": "{{ site.github.url }}{{ doc.url }}"
      }
      {% unless forloop.last %},{% endunless %}
    {% endfor %}
  };
</script>
<script src="{{ site.github.url }}/js/lunr.js"></script>
<script src="{{ site.github.url }}/js/search.js"></script>
</div>
