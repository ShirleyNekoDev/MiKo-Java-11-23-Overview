Features Outside of Projects
============================

## [JEP 467: Markdown Documentation Comments](https://openjdk.org/jeps/467) (Java 23)
new JavaDoc syntax using Markdown
- easier to write than HTML + doc-@-tags
- uses `///` instead of `/** ... */`
- syntax of [GitHub Flavored Markdown](https://github.github.com/gfm/)
- links: `[java.util.HashMap]` or `[equals][#equals(Object)]`
- retains inline tags such as {@inheritDoc} and block tags such as @param and @return
