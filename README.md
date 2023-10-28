# Snipper ✂️

Snipper is a small CLI tool which can "snip out" specially marked up parts in a text file into other files.

This is very useful e.g. when writing codelab tutorial style documentation e.g. in Markdown syntax.

When you have e.g. source code of the full solution of an exercice, you add inline comments to mark
around the sections which a student should complete. Snipper can then remove such sections from
that source file, and extract it into separate small "snippets" files, which you can include
in documentation.

You could set up a workflow where only the original full source and documentation with placeholders
is hand written and maintained, and use Snipper to extract section to fill into documentation, as well as
generate the "template" of the exercice which the student would start with. This could be using 
version control with Git and built and tested with continous integration.

This tool is intentionally keep simple and independant of any other documentation tools, and can be used with many of them.

https://docs.enola.dev/use/execmd is an otherwise unrelated tool which may be a useful but orthogonal complement to this one.

## ToDo

1. Write `src/test/snipper` input/outputs (expected) test cases
   * Snipper is configured by RegExps in a file type per-extension map
   * In Java, the "markers" are comments like "// <<<<<<<<<<<<<<<<<<<<<<< id123" and "// >>>"
   * In MD, the "markers" could be <-- <<<<< id123 --> comments, or (better?) HTML-like Directives like `<SNIP id=xyz />`
1. Implement it, e.g. with https://deno.com as `src/deno/snipper.ts` 
1. Write `docs/codelab/snipper.md`, using https://github.com/googlecodelabs/tools and https://docs.enola.dev/use/execmd/
1. Publish https://codelabs.learn.study/snipper
1. Remove this _ToDo_ section 😸
