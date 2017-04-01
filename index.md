# Write Blog with Jekyll
  My [github](https://github.com/fcharmy)  
  Starts from Mar 31 2017, a new begining.
 
# Jekyll Help
  [Help]({{ site.baseurl }}{% post_url 2017-04-01-help %}) file

<h2>Recent Posts</h2>

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
