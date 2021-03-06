RDFimporter module
==================
RDFimporter is primarily a set of plugins for the [Feeds module][feeds] that can be used to import remote RDF resources and map their content to Drupal nodes. It can be used for both one-time imports and periodic data imports.

Most of the Drupal functionality comes from the Feeds module itself. All RDF fetching and parsing is handled by the [ARC2 RDF framework][arc2]. (Both great pieces of software)

This module is the result of work being done at Cornell University's [Mann Library][mann] to bring content from Cornell's [VIVO database][vivo] into Drupal. Our hope is that other groups and institutions will be able use this module to bring VIVO content into their Drupal sites. We also hope this code will be useful to others as RDF becomes more available on the Web.

[feeds]: http://drupal.org/project/feeds
[arc2]: http://arc.semsol.org/
[mann]: http://mannlib.cornell.edu
[vivo]: http://vivo.cornell.edu


Goals
=====
- Make it easy for site builders, including non-developers, to import remote RDF content
- Allow RDF to be mapped to standard Drupal structures (CCK, Taxonomy)
- Provide a way to update nodes manually or automatically


Features
========
- Support for Linked Data and SPARQL endpoints (via ARC2)
- Allows users to define mappings between RDF properties and Drupal node properties
- Requires very little knowledge about RDF and SPARQL
- Automatically fetches human-readable labels for object properties
- Automatically filters out content in languages different from the site (when language is explicitly set in RDF)
- Provides hooks to 'preprocess' retrieved data and hooks to expose additional node properties


Requirements
============
- **Drupal 7.x**
- **Feeds module** + dependencies
- **ARC2 PHP library**

**NOTE:** Some system settings for PHP and MySQL may also need to be changed. See the INSTALL.markdown file for more details.

Installation and usage
======================
See "INSTALL.markdown" for an overview of how to configure and use the module.


Documentation
=============
- Screencast #1: [Installing the module + requirements][screencast1]
- Screencast #2: [Basic usage, importing Linked Data from VIVO][screencast2]
- Screencast #3: [Importing from a SPARQL endpoint][screencast3]
- Screencast #4: [Setting up node mappings][screencast4]

Links to further documentation and screencasts will be added here as they become available.

[screencast1]: http://vimeo.com/16965880
[screencast2]: http://vimeo.com/16990421
[screencast3]: http://vimeo.com/21471842
[screencast4]: http://vimeo.com/21484234


Status
======
This code is experimental and is not stable or reliable. For now, the issue queue on GitHub seems like the best place to post problems and bugs.

We would love some feedback on various use cases, how something like this might be used, and how it could be improved.

Contact Miles via GitHub or directly at mw542@cornell.edu


Some future plans
=================
- Allow single nodes to be updated/re-imported independently.
- Make the mapping screen much easier to use, possibly by using JavaScript-based visual mapping.
- Come up with a way to import RDFa. ARC2 can parse it already, but the structure can be a little funny.
- Handle multi-valued fields.


Other modules
=============
There are some great modules available that provide similar functionality, including [SPARQL Views][sparql_views] and [Linked Data][linked_data]. One major difference is that RDFimporter can work without a SPARQL endpoint if RDF is available via Linked Data. However, compared to those modules, RDFimporter does things quite lazily. It requires far less familiarity with RDF or SPARQL, but this ultimately makes it inefficient in some cases. If the data you're after is available from a SPARQL endpoint and you can write SPARQL queries, you might be better off with something like [SPARQL Views + Feeds View Parser][sparql_views_screencasts].

[sparql_views]: http://drupal.org/project/sparql_views
[linked_data]: http://drupal.org/project/linked_data
[sparql_views_screencasts]: http://lin-clark.com/blog/importing-syncing-content-external-sites-wikipedia

