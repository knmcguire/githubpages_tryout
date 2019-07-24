---
title: This is my title
layout: post
---

testtest
  {% for top_menu in site.data.menu %}
     {% if top_menu.subs %}
           <a title=“{{top_menu.title}}” href=“#”
              data-target=“#” data-toggle=“dropdown”
              class=“dropdown-toggle”>{{top_menu.title}}<span class=“caret”></span></a>
               {% include menu_ul.html subs=top_menu.subs %}
           {% else %}
               {% assign p = site.pages | where:“page_id”,top_menu.page_id | first %}
           <a title=“{{p.title}}” href=“{{p.url}}“>{{p.title}}</a>
           {% endif %}

  {% endfor %}
