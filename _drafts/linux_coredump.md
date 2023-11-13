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

A linux coredump represents a snapshot of the crashing process' memory. It is written as an ELF[^elf_format] file. The entirety of the ELF format is outside the scope of this article, but we will touch on a few of the more important bits when looking at an ELF core file.

## How are coredumps enabled/collected

### core_pattern

The kernel provides an interface for controlling where and how coredumps are written. The `/proc/sys/kernel/core_pattern`[^man_core] file provides two methods for capturing coredumps from crashed processes. A coredump can be written directly to a file by providing a path directly to it. For example if we wanted to write the core file to our `/tmp` directory with both the process name and the pid we would write the following to `/proc/sys/kernel/core_pattern`.

```
/tmp/core.%e.%p
```

In this example `%e` expands to the name of the crashing process, and `%p` expands to the PID of the crashing process.

We can also write pipe a coredump directly to a program. This is useful when we want to modify the coredump in flight. The coredump is streamed to the provided program via `stdin`. The configuration is similar to saving directly to a file except the first character must be a `|`.

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
[^elf_format]: [ELF File Format](https://refspecs.linuxfoundation.org/elf/elf.pdf)
[^man_core]: [`man core`](https://man7.org/linux/man-pages/man5/core.5.html)
[^man_ulimit]: [`man ulimit`](https://man7.org/linux/man-pages/man3/ulimit.3.html)
<!-- prettier-ignore-end -->
