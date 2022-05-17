---
short_name: website
name: This Website
taxonomy: website
toc: true
---
This is a meta posting about the making of this website. My plan with this site was to have a place to centralize and showcase
my work as I build a portfolio in software development. Keeping this site static and linking to demos was fine enough for me, and there are plenty of free hosting options for static websites.

### "Tech Stack"
I feel embarassed calling this a tech stack, since all these tools are basically plug-n-play, but this is how the site is built:

| Version control | | GitHub |
| Host | | GitHub Pages |
| Scaffolding | | Jekyll |
| Posts | | Markdown |
| Environment| | VS Code |

{% for post in site.posts %}
<p>
    <a href="{{ post.url }}">{{ post.title }}</a>
</p>
{% endfor %}

