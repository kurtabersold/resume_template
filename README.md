# Markdown Resume

This repository stores a version-controlled resume, using pandoc/LaTeX to generate a PDF artifact.
The GitHub workflow will automatically generate a PDF using pandoc/LaTeX when changes are pushed
to branches/tags specified in [the workflow steps](./.github/workflows/pdf_generation.yml).

## Usage

To use this template repository for your own resume:

1. Fork this template repository to create your own copy.
2. Update [RESUME.md](./RESUME.md) with your own resume content.
3. Update [CHANGELOG.md](./CHANGELOG.md) to track and annotate changes in your resume.
4. Commit and push your changes to your forked repository, following the conventional commit 
   format. The format consists of a type, an optional scope, and a commit message:
   - **Type:** Indicates the nature of the commit (e.g., feat, fix, docs, etc.).
   - **Scope:** (Optional) Describes the section or component of the project being affected.
   - **Commit message:** A short description of the changes made.

   Example commit message:
   ```plaintext
   feat: Add new section to resume
   ```
   Following this format will help in automatically generating the changelog and managing releases
   using standard-version.

   We recommend using Commitizen to create conventional commits. Commitizen is a command-line tool 
   that provides a guided and standardized commit message format. It helps ensure consistent commit
   messages and simplifies the release process. To use Commitizen, run the following command in
   your repository:

   ```shell
   git cz
   ```

We encourage you to use the **[Common Changelog](https://common-changelog.org/)** format to track
and document changes in your resume. The Common Changelog provides a standardized approach to
recording and communicating project updates.

To simplify managing the changelog and git tags, we recommend using
**[standard-version](https://github.com/conventional-changelog/standard-version)**. Standard
Version helps automate versioning, generating changelogs, and managing git tags based on the
conventional commit format. You can use it to streamline your release process and ensure consistent
changelog generation.

To use standard-version, ensure you have the required dependencies installed. Run the following
command in your repository:

```shell
npm install
```

Once installed, you can run the following command in your repository to automatically update
the changelog and manage git tags based on your commit messages:

```shell
npm run release
```

This will update the package version, generate the changelog in CHANGELOG.md, create a Git tag, and
commit the changes. Finally, you can push the changes and tags to the remote repository.

## Generating PDF Locally

To generate the PDF version of the resume locally, you can use the following Docker command:

```shell
docker run --rm -v `pwd`:/data pandoc/extra --output resume.pdf --template=resume.tex RESUME.md
```

This command will run the pandoc/extra Docker image and use the provided LaTeX template to convert
the Markdown file (RESUME.md) into a PDF (resume.pdf). Make sure you have Docker installed on your
system and the current working directory contains the necessary files.

## Workflow Permissions

Please ensure that you have the necessary permissions set for the GitHub Actions workflow.

The workflow requires "read and write permissions" to create releases. To configure this:

1. Go to your repository's **Settings**.
2. Navigate to **Actions** -> **General**.
3. Scroll down to **Workflow permissions**.
4. Select "Read and write permissions".

## Contributing

Contributions are welcome! If you have improvements or additional features to suggest, please feel
free to make a pull request. We appreciate your contributions.

## Issues

If you encounter any issues with this template repository or have suggestions for improvement,
please create an issue on the [GitHub repository](https://github.com/kurtabersold/resume). We value
your feedback and will address the issues as soon as possible.

Feel free to customize this repository to fit your specific needs and preferences.
