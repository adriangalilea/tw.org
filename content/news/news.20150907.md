---
title: "Taskwarrior 2.5.0 beta1 Released"
date: 2015-09-07
---

### Taskwarrior 2.5.0 beta1 Released 

After an intense four-month effort, which focused mainly on a more capable command-line parser, more extension-friendly behavior, and significant improvements to testing, Taskwarrior 2.5.0 beta1 is now released.

We are asking you to please [build](../../docs/build/) and test this release in your environment.

This is a major release, with about 1100 code changes and a hundred or so bug fixes, but still resulting in a smaller codebase.

There have been a lot of changes.
Here are the highlights:

- Improved command line parser: terminator `--` handling, UUID recognition, DOM recognition, red-herring pairs (`foo:bar`), escaped slashes in patterns (`/one\/two/`), substitutions (`/one\/two/one-two/`), Unicode `U+NNNN` and `\uNNNN`, escaped entities (`\n`, `\t`, etc.) for use in descriptions/annotations, abbreviated day and month names, ISO-8601 durations (`PT4H`, `P1Y` etc).
- New [virtual tags](../../docs/tags/) `UDA`, `ORPHAN`, `PROJECT`, `PRIORITY`, and `LATEST`.
- Improved support for DOM references in filters `task 'due.year = 2015 and due.week > 20' list`.
- New configuration settings `urgency.inherit`, `rule.color.merge`, `urgency.user.tag.next.coefficient`, `color.uda.<name>.none`, `sugar`, `report.<name>.sort:none`, `json.depends.array`.
- Improved urgency: the `urgency.inherit` setting propagates urgency along dependency chains.
- Improved searching: more powerful regular expressions.
- Improved attribute modifiers: `is`/`isnt` are now consistent exact match operator equivalents to `==`/`!==`.
- New command [`_unique`](../../docs/commands/_unique/), for generating unique lists of values, and will ultimately replace several helper commands.
- New command `commands`, which lists commands and details about how they affect [filters](../../docs/filter/), GC, context, and [syntax](../../docs/syntax/).
- New verbosity tokens `recur` (feedback when a recurring task instance is created), `unwait` (for when a waiting task becomes visible).
- Improved extensions: zsh completion, Fish shell completion, [add-on scripts](../../tools/) now online.
- Improved documentation: `help` command, man pages, more online docs, negation `!` operator, sample hook scripts.
- Improved sync: GnuTLS now mandatory, so everyone has the `sync` command.
- Improved JSON `import`/`export` support: free-format JSON, task arrays assumed (which makes import/export work with out-of-the-box parsers), dependencies optionally modeled as an array, UUIDs validated, tasks added/updated without duplication, import from STDIN using `-`.
- Improved performance: less data is read from disk depending on the filter.
- Improved diagnostics: duplicate dependency warnings, multi-task edit failures, changes to tasks without IDs, certificate file sizes.
- Improved testing: migrated all Perl tests to Python, parallelized test suite, colorized output, detection of newly passing tests, Python 2.7 and 3 support, better debug output, Bash test library, stress test tool, no more disabled tests - everything runs, test coverage is now 87.8%.
- Widespread code cleanup, removal of dead code, C++11 enhancements, improved portability, merged ISO-8601 and legacy durations, less code, happier developers.

For full details, see the ChangeLog file included in the release.
The release is immediately available as a source ~~tarball~~.

This is a beta release, and is not recommended for stable environments.
