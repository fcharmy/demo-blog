# Write Blog with Jekyll
  My [github](https://github.com/fcharmy)  
  Starts from Mar 31 2017, a new begining.
 
# Recent Posts
<ul>
  {% for post in site.posts limit:5 | sort: 'title', 'last' %}
    <li>
      <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
