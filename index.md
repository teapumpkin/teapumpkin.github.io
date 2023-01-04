---
#
# By default, content added below the "---" mark will appear in the home page
# between the top bar and the list of recent posts.
# To change the home page layout, edit the _layouts/home.html file.
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#
layout: home
---


<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first | slugsize }}{% endcapture %}   
{% comment %} 
    <div id="#{{ category_name | slugize }}">hellobob-slugify-defaut {{ category | slugify: "default" }} </div>
    <div id="#{{ category_name | slugize }}">hellobob-slugify-raw {{ category | slugify: "raw" }} </div>
{% endcomment %}
    <div id="#{{ category_name | slugize }}">hellobob-slugsize {{ category | slugsize }} </div>
    <div id="#{{ category_name | slugize }}">hellobob-slugize {{ category | slugize }} </div>
    <p></p>

    <h3 class="category-head">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      <h4><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></h4>
    </article>
    {% endfor %}
  </div>
{% endfor %}
</div>

--------


