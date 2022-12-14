# write-template

A project template to help write prose in Visual Studio Code (yes, really) and provides some export/compilation functionality. Compilation steps are kicked off through GitHub Actions (see the `.github` directory for details).

## Project Structure

Chapters are stored as individual Markdown files in the `chapters` directory and included in the final compilation.

Research is in the `research` directory and not included during compilation.

## Project Settings

The settings for the workspace are stored in `write-template.code-workspace` and provide some editor changes while working with Markdown files, specifically while in Zen mode.

## Snippets

There are a few VSCode snippets defined in the `.vscode/markdown.code-snippets` file to help fill out blank Markdown files. These are:

- `chapter` - A super simple snippet that inserts a page title
- `character` - A character bio template with name, age, occupation, etc.

## Compilation

Project compilation is handled by GitHub actions, so check the files inside the `.github/workflows` directory for details.

The compiled files are part of the action's artifacts and named "output."

### EPUB Compilation

During compilation, files are read from the file system in order, so maintain a sort-friendly filename system. I recommend prefixing a chapter number to the filename for fiction or an ISO-8601 type date format for journaling, e.g.:

- `001-chapter-name.md`
- `2020-09-20-journal.md`
- `2020-journal.md`

### EPUB Metadata

The file `chapters/metadata.yaml` is a YAML file containing the metadata for the EPUB file generated by the compilation script. The provided file is a minimum viable sample file. However, for real projects, I suggest reading [the Pandoc documentation](https://pandoc.org/MANUAL.html#epub-metadata) for this specific file since you will want to customize this.
