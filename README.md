# - CMS Versioning (CMSver) DRAFT -

Index of pages:
---------------

* [Summary](/README.md#Summary)
* [Introduction](/README.md#Introduction)
* [CMS Versioning (CMSver)](/VERSIONING.md)
* [Why Explicit Versioning](/WHY.md)
* [FAQ](/FAQ.md)
* [ABOUT](/ABOUT.md)
* [Who is using CMS Versioning?](/USERS.md)

# - CMS Versioning (CMSver) DRAFT -


# <a name="Summary"></a>Summary

Given a version number RELEASE.MAJOR.MINOR.PATCH, increment the:

1. RELEASAE is incremented when changing the API, changing the UX, switching to a new recommended version or ending support for previous versions,
1. MAJOR is incremented when adding, changing or removing code while breaking compatibility with previous versions or changing the UX,
1. MINOR is incremented when adding, changing or removing code while remaining compatible with previous versions,
1. FIX is incremented when a bug is fixed, or a security gap is solved.

Additional labels for pre-release, release candidate and build metadata are available as extensions to the RELEASE.MAJOR.MINOR.PATCH format.

**If you'd like to leave feedback, please [open an issue on GitHub](https://github.com/colomet/CMSver/issues).**
  
# - CMS Versioning (CMSver) DRAFT -  

# <a name="Introduction"></a>Introduction

In the world of software management there exists a dread place called "dependency hell." The bigger your system grows and the more packages you integrate into your software, the more likely you are to find yourself, one day, in this pit of despair.

In systems with many dependencies, releasing new package versions can quickly become a nightmare. If the dependency specifications are too tight, you are in danger of version lock (the inability to upgrade a package without having to release new versions of every dependent package). If dependencies are specified too loosely, you will inevitably be bitten by version promiscuity (assuming compatibility with more future versions than is reasonable).
Dependency hell is where you are when version lock and/or version promiscuity prevent you from easily and safely moving your project forward.

**In CMS (WordPress, Joomla, Drupal) also exist the problem of the complements (Modules, Aplications, Plugins, Components, add-ons ...) where we need to take care of the code once we integrate our development in the CMS.** Also Wordpress offer a last digit where nothing change but a security or bug fix. Such situation give us the security nothing wrong could happen after the update.

Another problem we find is about SEMVER, Semantic Versioning is too API focus and some times the developers do just code.

As a solution to this problem, I propose a simple set of rules and requirements that dictate how version numbers are assigned and incremented in a base of 4 digit instead of the 3 digits of [Semantic Versioning](http://semver.org/), in that way we split in a different digit each one of the situations.

These rules are based on but not necessarily limited to pre-existing widespread common practices in use in both closed and open-source software.

For this system to work, you first need to declare a public API. This may consist of documentation or be enforced by the code itself. Regardless, it is important that this API be clear and precise. Once you identify your public API, you communicate changes to it with specific increments to your version number. Consider a version format of W.X.Y.Z (Release.Feature.Enhanced.Patch). Bug fixes not affecting the API increment the PATCH version, backwards compatible additions/changes increment the MINOR version, backwards incompatible changes increment the MAJOR version and backwards incompatible API changes increment the RELEASE version.

I call this system ["CMS Versioning (CMSver)](/VERSIONING.md) Under this scheme, version numbers and the way they change convey meaning about the underlying code and what has been modified from one version to the next.

   <a href="https://twitter.com/share" class="twitter-share-button" data-show-count="false">Tweet</a><script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>|<script src="https://apis.google.com/js/platform.js" async defer></script>
   <g:plus action="share"></g:plus>
   ------ | ------
   fb
   <div class="fb-share-button" data-href="{{site.url}}{{page.url}}" data-layout="button_count" style="position: relative; top: -8px; left: 33px;"></div>
   1
   <!-- Inserta esta etiqueta donde quieras que aparezca Botón Compartir. -->
   <div class="g-plus" data-action="share" data-height="24"></div>
   2
   
   3
   <g:plus action="share" ...></g:plus>

///// old---
1. RELEASE version when you make incompatible API changes,
1. MAJOR version when you add functionality in a backwards-incompatible manner,
1. MINOR version when you add functionality in a backwards-compatible manner, and
1. PATCH version when you make backwards-compatible bug fixes.






We recently moved this blog from WordPress to Jekyll and created a site structure from the plain vanilla install of Jekyll. The first thing I noticed after moving our posts from WordPress was the absence of plugins for adding share buttons in blog posts and pages, so I made a simple static one of my own.

You can read about why we made the choice of moving from WordPress to Jekyll in my previous blog post. In this post I will share the code snippet I am using to create pretty little share buttons for sharing my posts on Twitter, Facebook and Google Plus. I will also show how you can extend it to add more services like Reddit, LinkedIn, Tumblr etc.
Share buttons in Jekyll posts

In order to add share buttons to my posts, I used the share URLs of the social networking sites such as Twitter, Facebook and Google Plus which simply use the GET parameters passed with the URL to create the share dialog.
Step 1: Partial include file for share buttons

I created a partial HTML file in _includes folder called _ share-page.html which I added at the end of the post or page layouts after content. Find below the contents of this file. Notice the use of liquid tags such as {{ page.title }} and {{ page.url }} to automatically fetch the title and URL of the current post or page.

<div class="share-page">
    Share this on &rarr;
    <a href="https://twitter.com/intent/tweet?text={{ page.title }}&url={{ site.url }}{{ page.url }}&via={{ @_Colomet }}&related={{ site.twitter_username }}" rel="nofollow" target="_blank" title="Share on Twitter">Twitter</a>
    <a href="https://facebook.com/sharer.php?u={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank" title="Share on Facebook">Facebook</a>
    <a href="https://plus.google.com/share?url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank" title="Share on Google+">Google+</a>
	<a href="http://www.linkedin.com/shareArticle?mini=true&url={{ site.url }}{{ page.url }}" rel="nofollow" target="_blank" title="Share on LinkedIn">LinkedIn+</a>
</div>



http://twitter.com/share?text=<TITLE>&url=<URL>&via=<TWITTER-HANDLE>&related=<TWITTER-HANDLE>
Facebook

http://www.facebook.com/sharer.php?u=<URL>&p[title]=<TITLE>
Google Plus

https://plus.google.com/share?url=<URL>
Pinterest

http://pinterest.com/pin/create/button/?url=<URL>&description=<TITLE>
LinkedIn

http://www.linkedin.com/shareArticle?mini=true&url=<URL>&title=<TITILE>&summary=<DESCRIPTION>&source=<DOMAIN>
Tumblr

http://www.tumblr.com/share/link?url=<URL>&name=<TITLE>&description=<DESCRIPTION>
Reddit

http://www.reddit.com/submit?url=<URL>&title=<TITLE>


[Start page](./)
