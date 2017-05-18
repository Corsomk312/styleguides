{% assign url_parts = page.url | split: '/' %}
      {% assign url_parts_size = url_parts | size %}
      {% if url_parts_size != 0 %}
        {% assign rm = url_parts | last %}
        {% assign base_url = page.url | replace: rm %}
      {% else %}
        {% assign base_url = page.url %}
      {% endif %}
      <ul>
      {% for node in site.pages %}
        {% assign node_url_parts = node.url | split: '/' %}
        {% assign node_url_parts_size = node_url_parts | size %}
        {% assign filename = node_url_parts | last %}
       
        {% if node_url_parts_size == 2  %}
            <li>
            <a class="sidebar-nav-item{% if page.url == node.url %} active{% endif %}" href="{{ node.url }}">{{ node.title }}</a></li>
            {% if page.url contains node.url %}
              <ul>
              {% for node2 in site.pages %}
                {% if node2.url contains node.url %}
                  <li><a href='{{node2.url}}'>{{node2.title}}</a></li>
                {% endif %}
              {% endfor %}
              </ul>
            {% endif %}
        {% endif %}
      {% endfor %}
      {% for num in (1...menu_level) %}
        </ul>
      {% endfor %}
      </ul>


## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Corsomk312/styleguides/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Corsomk312/styleguides/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
