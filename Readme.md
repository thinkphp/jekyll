# Creating a Jekyll App on Heroku Cedar

## Setup Jekyll

Install the jekyll gem.

```
gem install jekyll
```

## Create the site structure

```
mkdir jekyll-app
cd jekyll-app
touch index.md
mkdir _posts
mkdir _layouts
touch _layouts/default.html
```

## Hello World Jekyll

Let's create a layout. Open _layouts/default.html and add:

```
<!DOCTYPE html>
<html>
<head>
  <meta charset=utf-8 />
  <link href='/css/screen.css' rel='stylesheet' type='text/css' />
  <title>Adrian Statescu - {{ page.title }}</title>
</head>
<body>
  <header>
    <h1><a href='/index.html'>Adrian Statescu</a></h1>
    <nav>
      <a href='/index.html'>blog</a>
      -
      <a href='/projects/index.html'>projects</a>
    </nav>
  </header>
  <div id='content'>
    {{ content }}
  </div>
  <footer>
    <a href='contact.html'>contact</a>
    -
    <a href='https://github.com/thinkphp'>github</a>
    -
    <a href='http://twitter.com/#!/thinkphp'>twitter</a>
    -
    <a href='http://www.linkedin.com/in/statescuadrian'>linked in</a>
    -
    <a href='http://thinkphp.ro/+'>google+</a>
  </footer>
</body>
</html>
```

We need an index page. Open index.md and add:

```
---
layout: default
title: home
---

{% for post in site.posts %}
[{{ post.date | date: "%B %d, %Y" }} - {{ post.title }}]({{ post.url }})
{% endfor %}

```
