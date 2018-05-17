Implement Schema Markup For Blogger
========================

At previous guide we can understand how Blogger generate xml markup and add a layout structure, but we need a schema markup for fast indexing in search engine.

Schema.org is a collaborative, community activity with a mission to create, maintain, and promote schemas for structured data on the Internet, on web pages, in email messages, and beyond.

Schema.org vocabulary can be used with many different encodings, including RDFa, Microdata and JSON-LD. These vocabularies cover entities, relationships between entities and actions, and can easily be extended through a well-documented extension model. Over 10 million sites use Schema.org to markup their web pages and email messages. Many applications from Google, Microsoft, Pinterest, Yandex and others already use these vocabularies to power rich, extensible experiences.

Founded by Google, Microsoft, Yahoo and Yandex, Schema.org vocabularies are developed by an open community process, using the public-schemaorg@w3.org mailing list and through GitHub.

A shared vocabulary makes it easier for webmasters and developers to decide on a schema and get the maximum benefit for their efforts. It is in this spirit that the founders, together with the larger community have come together - to provide a shared collection of schemas.

For more information visit |schema|.

.. |schema| raw:: html

   <a href="http://schema.org/" target="_blank">Schema</a>
   
This is a basic xml blogger markup structure::

<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE html>
<html b:version='2' class='v2' expr:dir='data:blog.languageDirection' xmlns='http://www.w3.org/1999/xhtml' xmlns:b='http://www.google.com/2005/gml/b' xmlns:data='http://www.google.com/2005/gml/data' xmlns:expr='http://www.google.com/2005/gml/expr' xmlns:og='http://ogp.me/ns#'>
<head>
<meta charset="UTF-8"/>
<title><data:blog.title/></title>
</head>
<body>
<div id="wrapper">
<header id="header-wrapper">
<b:section class='header' id='header' maxwidgets='1'>
<b:widget id='Header1' locked='true' title='Basic Blogger Template (Header)' type='Header'></b:widget>
</b:section>
</header>
<nav id="navigation>
<ul>
<li><a href="">Home</a></li>
<li><a href="">About</a></li>
</ul>
</nav>
<div class='clearfix'/>
<section id="outer-wrapper>
<article id="article-wrapper">
<b:section class='main' id='main'>
<b:widget id='Blog1' locked='true' title='Blog Posting' type='Blog'></b:widget>
</b:section>
</article>
</section>
<div class='clearfix'/>
<aside id="sidebar-wrapper">
<b:section class='sidebar' id='sidebar' showaddelement='yes'></b:section>
</aside>
<div class='clearfix'/>
<footer id="footer-wrapper">
<b:section class='footer' id='footer' showaddelement='yes'></b:section>
</footer>
</div>
</body>
</html>

We need to add a schema markup to this layout structure, this is a schema markup for Blogger::

<body class='index' itemscope='' itemtype='http://schema.org/WebPage'>
<header id='header-wrapper' itemscope='itemscope' itemtype='http://schema.org/WPHeader'>
<nav id='navigation' itemscope='itemscope' itemtype='http://schema.org/SiteNavigationElement' role='navigation'>
<article id='article-wrapper' itemscope='itemscope' itemtype='http://schema.org/Blog' role='main'>
<div class='post hentry uncustomized-post-template' itemscope='itemscope' itemtype='http://schema.org/BlogPosting'>
<article class='post hentry' expr:id='data:post.id' itemscope='' itemtype='http://schema.org/BlogPosting'>
<span class='fn author' itemprop='author' itemscope='itemscope' itemtype='http://schema.org/Person'>
<aside id='sidebar-wrapper' itemscope='itemscope' itemtype='http://schema.org/WPSideBar'>
<footer id='footer-wrapper' itemscope='itemscope' itemtype='http://schema.org/WPFooter'>

This is a basic blogger template with implementing schema markup using schema markup for Blogger::

