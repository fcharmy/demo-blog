# Write Blog with Jekyll
  My [github](https://github.com/fcharmy)  
  Starts from Mar 31 2017, a new begining.
 
# Recent Posts
{% for post in site.posts limit:5 | sort: 'title', 'last' %}
  <div class="panel panel-default">
    <div class="panel-heading">
      <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    </div>
    <div class="panel-body">
      {{ post.excerpt }}
    </div>
  </div>
{% endfor %}
