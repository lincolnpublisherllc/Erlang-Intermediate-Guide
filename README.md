What I delivered

ZIP contents: chapter_##_TitleSlug/ folders with .erl files (and a manifest.json at the root listing every file by chapter).

File naming: when the book provided an explicit marker like %% File: query_guard.erl, I used that filename; otherwise I created snippet_##.erl in that chapter, preserving the exact code text and order.

Total: 621 code files extracted across the book’s chapters.

How it’s organized

Inside the ZIP you’ll see folders like:

chapter_01_chapter-1/
  query_guard.erl
  user_norm.erl
  math_safe.erl
  reg1.erl
  ...
chapter_02_project-environment-and-package-management/
  basic_SUITE.erl
  ...
...
manifest.json


manifest.json lists every generated file by chapter so you can quickly scan the inventory.

How I extracted the code

Detected chapter boundaries from headings like “Chapter 1…”.

Collected code blocks using clear signals:

Erlang markers such as -module, -export, -behaviour, ->, case, receive, gen_server, -spec.

Lines starting with %% (Erlang comments) and explicit %% File: markers to name files.

Shell transcripts like 1> ... where relevant in context.

Grouped contiguous code-like lines into a single file until normal text resumed.

Wrote each group into the current chapter folder using the filename from the book when available.

Notes and limitations

Exactness: I kept the code text verbatim, including comments and spacing. If the source used shell transcripts for quick probes, those lines are preserved too.

Filenames: When the book didn’t state a filename, I used snippet_##.erl. You can rename those later as you like.

Non-Erlang content: A few short examples in other syntaxes (e.g., YAML fragments for CI) may be included if they were part of a “code-like” section. They’ll appear as .erl only when the book didn’t label a file type; if you want those split or retyped (e.g., .yml, .json), tell me and I’ll separate them.

Build readiness: Some snippets are teaching fragments, not full modules. Expect a few to require context from their chapters before compiling.

Quick start

Unzip the file.

Browse manifest.json to see everything at a glance.

If you’re testing specific modules from Chapter 1:

Look under chapter_01_.../ for files like query_guard.erl, user_norm.erl, math_safe.erl, reg1.erl.

For Chapter 2’s CI and release examples:

Check chapter_02_.../ for test suites and release scaffolding examples.
