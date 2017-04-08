# Write Blog with Jekyll
  Starts from Mar 31 2017, a new begining.
 
# Recent Posts
<!---{% cycle 'info', 'default' %}--->

{% for post in site.posts limit:5 | sort: 'title', 'last' %}
  <div class="panel panel-info">
    <div class="panel-heading">
      <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    </div>
    <div class="panel-body">
      {{ post.excerpt }}
    </div>
  </div>
{% endfor %}
