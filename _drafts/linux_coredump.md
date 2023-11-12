---
# This is a template for Interrupt posts. Use previous, more recent posts from the _posts/
# directory for more inspiration and patterns.
#
# When submitting a post for publishing, submit a PR with the post in the _drafts/ directory
# and it will be moved to _posts/ on the date of publish.
#
# e.g.
# $ cp _drafts/_template.md _drafts/my_post.md
#
# It will now show up in the front page when running Jekyll locally.

title: A Shallow Dive into Linux Coredumps
description:
  Post Description (~140 words, used for discoverability and SEO)
author: blake
---

A little bit of background of why the reader should read this post.

<!-- excerpt start -->

Excerpt Content

<!-- excerpt end -->

Optional motivation to continue onwards

{% include newsletter.html %}

{% include toc.html %}

## What is a Linux Coredump

What it is, why it's useful, and how it's used.

## How are coredumps enabled/collected

Talke about core_pattern, ulimit, and other ways to enable coredumps.

## Layout of elf core file

Talk about the layout of the core file, and how it is a snapshot of the process.
Also shill Memfault a bit wrt limiting the memory captured in the core file.

## How to load a core file into gdb

Talk about how to load a core file into gdb, and how to use it to debug the
process.

## Conclusion



<!-- Interrupt Keep START -->
{% include newsletter.html %}

{% include submit-pr.html %}
<!-- Interrupt Keep END -->

{:.no_toc}

## References

<!-- prettier-ignore-start -->
[^reference_key]: [Post Title](https://example.com)
<!-- prettier-ignore-end -->
