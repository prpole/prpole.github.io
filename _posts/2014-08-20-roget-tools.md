---
layout: post
title: Roget Tools
description: "The first iteration of Roget Tools for Python"
modified: 2014-08-20
tags: [Roget, thesaurus, Roget's thesaurus, python, NLP, natural language processing]
comments: false
image:
  feature: texture-feature-06.jpg
---

<section id="table-of-contents" class="toc">
  <header>
    <h3>Contents</h3>
  </header>
<div id="drawer" markdown="1">
*  Auto generated table of contents
{:toc}
</div>
</section><!-- /#table-of-contents -->


##Overview

Following on [Simon DeDeo et al. (2014)'s work on the "Old Bailey" records](http://www.pnas.org/content/111/26/9419.full), the Roget tools are a Python library for tracking broad semantic categories in bodies of text using the top-down hierarchical structure of Peter Mark Roget's *Thesaurus*. These tools were derived from the 1911 index to and full text of the *Thesaurus* [available from Project Gutenberg](http://www.gutenberg.org/ebooks/search/?query=roget) and were generated using 1. automated regular expression text extraction on the [index](http://www.gutenberg.org/cache/epub/10681/pg10681.txt) and 2. semi-automated reconstruction of the hierarchy mirrored in the chapter headings of the [full 1911 edition](http://www.gutenberg.org/cache/epub/22/pg22.txt). 

This library opens up several methods of automated textual analysis. First, it enables Python-readable categorization of individual words at different levels of abstraction (i.e., specificity of semantic categorization). It also allows the user to return the full hierarchical path of all a given word's categories to the top of Roget's taxonomy, simultaneously measuring the path length. In addition to being applicable to individual words, both of these methods can be automatically applied to large samples of text, replacing words with their semantic categories. These tools can also return the distance (in network edges)^[See Jarmasz and Szpakowicz (2012) on the relevance of this measure.] between any two words in the *Thesaurus* or any two nodes in the hierarchy. Finally, given a text---be it a list of randomly selected words, a portion of a literary text, or part of the output from a topic modeling algorithm---the Roget tools can return the node or nodes that most accurately represent that text's semantic character; this representativeness is measured as the minimum average distance in edges from each word in the list to the selected node.

