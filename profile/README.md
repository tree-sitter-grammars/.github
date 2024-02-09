# Tree-Sitter-Grammars

Hey and welcome to the Tree-Sitter-Grammars organization! This org contains a
well-maintained bundle of grammar repositories for any downstream users to easily
find a grammar they're interested in.

## Contributing

If you have a grammar you're interested in contributing, please open an issue [here](https://github.com/tree-sitter-grammars/.github/issues).

### Grammar Requirements

1. No scanner written in C++, sorry.
2. Queries must use the last-wins precedence, a-la Neovim style.
3. You should be somewhat active in maintaining it; if there's no need for
   maintenance that's totally okay, but you shouldn't let issues pile up for months
   to years on end.
4. You must follow SemVer (Semantic Versioning) for your grammar, breaking changes
   must result in a version major bump, new features in a minor bump, and bug
   fixes in a patch bump.
5. (Optional) You should use conventional commits
