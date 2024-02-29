# Contributing Guidelines

## Creating a Grammar

We recommend creating the grammar using our [template], either via the
"Use this template" button on the web interface, or via the `--template`
flag of the [gh cli]. Wait a moment for the initial setup to complete and
then check the workflow summary for the next steps. The repository includes
the MIT license by default, but you can change it to whatever you want.

Make sure to read the Tree-sitter [documentation] before you start
developing the grammar. The template handles most of the project setup
for you. Just run these two commands in the grammar directory to get started:

```bash
npm install --ignore-scripts
export PATH="$PWD/node_modules/.bin:$PATH"
```

Or, if you're developing on Windows using PowerShell:

```powershell
npm install --ignore-scripts
$env:PATH = "$PWD\node_modules\.bin;$env:PATH"
```

The template files include a few `NOTE:` comments that you should read,
act upon, and then remove. You can view them all by running this command:

```bash
grep -Irn NOTE: --exclude-dir=node_modules
```

## Requirements for Inclusion

If you'd like your grammar to be included in this organization, please adhere to the following:

1. Include corpus tests to ensure the parser works as expected.
    - You may also include some example files to be parsed in CI.
2. The queries must use the last-wins precedence (all queries are applied).
    - Include highlight queries and their tests. Other queries are generally not necessary.
    - The highlight captures should either use [Tree-sitter][STANDARD_CAPTURE_NAMES]'s
      "standard" names, or [Neovim][treesitter-highlight-groups]'s names.
3. The external scanner (if any) must be written in C and not C++.
4. The grammar must be written in JavaScript and not TypeScript or anything else.
5. You should be somewhat active in maintaining it. It's fine if there's no need for
   maintenance, but you shouldn't let issues pile up for months to years on end.
6. You must follow [SemVer] for your grammar: breaking changes must result in a major bump,
   new features in a minor bump, and bug fixes in a patch bump.
7. Commit messages should follow the [Conventional Commits] specification.
8. Make sure all the metadata (names, links, versions, etc.) are correct and consistent.
    - For example, the version in `package.json` must be the same as the one in `Cargo.toml`.
9. Make use of the official [workflows] and actions wherever possible.

[template]: https://github.com/tree-sitter-grammars/template
[gh cli]: https://cli.github.com/manual/gh_repo_create
[documentation]: https://tree-sitter.github.io/tree-sitter/creating-parsers
[STANDARD_CAPTURE_NAMES]: https://github.com/tree-sitter/tree-sitter/blob/master/highlight/src/lib.rs#L22-L73
[treesitter-highlight-groups]: https://neovim.io/doc/user/treesitter.html#treesitter-highlight-groups
[SemVer]: https://semver.org/
[Conventional Commits]: https://www.conventionalcommits.org/en/v1.0.0/
[workflows]: https://github.com/tree-sitter/workflows#readme
