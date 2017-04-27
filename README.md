# - PHP CMS Versioning DRAFT -

Index of pages:
---------------

* [Summary](/README.md#Summary)
* [Introduction](/README.md#Introduction)
* [PHP CMS Versioning (PHPVer)](/VERSIONING.md)
* [Why Explicit Versioning](/WHY.md)
* [FAQ](/FAQ.md)
* [ABOUT](/ABOUT.md)

# - PHP CMS Versioning DRAFT -


# <a name="Summary"></a>Summary

Given a version number RELEASE.ENHANCED.FEATURE.PATCH, increment the:

1. RELEASE version when you make incompatible API changes,
1. ENHANCED version when you add functionality in a backwards-incompatible,
1. FEATURE version when you make backwards-compatible manner, and
1. PATCH version when you fix bugs.

Additional labels for pre-release, release candidate and build metadata are available as extensions to the RELEASE.ENHANCED.FEATURE.PATCH format.

**If you'd like to leave feedback, please [open an issue on GitHub](https://github.com/colomet/php-cms-versioning/issues).**

Given 1.0.0.0 as the first version for a Production Release:

* RELEASE:
  * Major Code Overhaul that impacts a significant number of end points in the Public Api will increment version to 2.0.0.0.
  * Major UX change that impacts in a significant way the usability will increment version to 2.0.0.0.
* ENHANCED:
  * Any Breaking Code Change will increment version to 1.1.0.0.
  * UX change that impacts the usability will increment version to 1.1.0.0.  
* FEATURE:
  * New Features will increment version to 1.0.1.0.
  * Refracting Code that do not impact Public Api will increment version to 1.0.1.0.
  * Deprecating Code that do not impact Public Api will increment version to 1.0.1.0.
  * Removing Code that do not impact Public Api will increment version to 1.0.1.0.
* PATCH:
  * Security Fix(es) will increment version to 1.0.0.1.
  * Bug Fix(es) will increment version to 1.0.0.1.
  
# - PHP CMS Versioning DRAFT -  

# <a name="Introduction"></a>Introduction

In the world of software management there exists a dread place called "dependency hell." The bigger your system grows and the more packages you integrate into your software, the more likely you are to find yourself, one day, in this pit of despair.

In systems with many dependencies, releasing new package versions can quickly become a nightmare. If the dependency specifications are too tight, you are in danger of version lock (the inability to upgrade a package without having to release new versions of every dependent package). If dependencies are specified too loosely, you will inevitably be bitten by version promiscuity (assuming compatibility with more future versions than is reasonable).
Dependency hell is where you are when version lock and/or version promiscuity prevent you from easily and safely moving your project forward.

**In CMS (WordPress, Joomla, Drupal) also exist the problem of the complements (Modules, Aplications, Plugins, Components, add-ons ...) where we need to take care of the code once we integrate our development in the CMS.** Also Wordpress offer a last digit where nothing change but a security or bug fix. Such situation give us the security nothing wrong could happen after the update.

As a solution to this problem, I propose a simple set of rules and requirements that dictate how version numbers are assigned and incremented in a base of 4 digit instead of the 3 digits of [Semantic Versioning](http://semver.org/), in that way we split in a different digit each one of the situations.

These rules are based on but not necessarily limited to pre-existing widespread common practices in use in both closed and open-source software.

For this system to work, you first need to declare a public API. This may consist of documentation or be enforced by the code itself. Regardless, it is important that this API be clear and precise. Once you identify your public API, you communicate changes to it with specific increments to your version number. Consider a version format of W.X.Y.Z (Release.Enhanced.Feature.Patch). Bug fixes not affecting the API increment the patch version, backwards compatible additions/changes increment the Feature version, backwards incompatible changes increment the Breaking version and backwards incompatible API changes increment the Release version.

I call this system ["PHP CMS Versioning" (PHPVer)](/VERSIONING.md) Under this scheme, version numbers and the way they change convey meaning about the underlying code and what has been modified from one version to the next.




[Start page](./)
