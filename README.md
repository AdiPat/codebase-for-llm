# Codebase-to-Markdown

**Codebase-to-Markdown** is a library that converts an entire codebase from a GitHub repository URL or local file path into a single markdown file. This file is structured for efficient processing by large language models (LLMs).

<p align="center">
  <img src="https://raw.githubusercontent.com/AdiPat/codebase-for-llm/refs/heads/main/assets/logo_art.png" />
</p>

---

## Problem Statement

As LLMs become increasingly capable of analyzing and understanding codebases, there is a growing need to provide them with input that is both comprehensive and well-structured. Typical codebases are complex, consisting of multiple directories, files, and formats. Feeding this directly to an LLM can lead to inefficiencies and processing errors. Additionally, LLMs often have context size limitations, making it essential to present the information in an organized and consumable manner.

---

## Use Cases

- **Code Review and Analysis**: Simplify the process of analyzing an entire codebase using LLMs by converting it into a format that highlights the directory structure and file contents clearly.
- **Documentation Generation**: Automatically generate a markdown-based overview of a project to help teams understand the structure and content of large codebases.
- **Codebase Summarization**: Summarize a repository’s key files and functionality to make it easier for new developers to onboard.
- **Bug Localization**: Provide LLMs with the entire codebase in a structured format for efficient debugging and error localization.
- **AI-Powered Refactoring**: Use LLMs to propose refactors or optimizations by providing them with the full context of the codebase in a manageable format.

---

## Features

- Accepts input as:
  - A GitHub repository URL (with optional branch or commit specification).
  - A local file path to the codebase.
- Transforms the directory structure, files, and content into a single markdown file.
- Annotates and organizes the markdown with clear file paths, metadata, and code snippets.
- Handles large codebases by breaking down files into sections or chunks.
- Configurable to include or exclude files, control file size limits, and customize output structure.

---

## Installation

Install the library using npm or yarn:

```bash
npm install codebase-to-markdown
```

or

```bash
yarn add codebase-to-markdown
```

---

## Usage

### Basic Example

```javascript
const { transformCodebase } = require("codebase-to-markdown");

// From GitHub Repository
transformCodebase({
  source: "https://github.com/user/repo",
  branch: "main", // Optional: Defaults to default branch
  output: "output.md",
});

// From Local File Path
transformCodebase({
  source: "/path/to/local/codebase",
  output: "output.md",
});
```

### Configuration Options

| Option        | Type     | Description                                      | Default          |
| ------------- | -------- | ------------------------------------------------ | ---------------- |
| `source`      | `string` | URL of the GitHub repository or local file path. | **Required**     |
| `branch`      | `string` | Branch or commit SHA to fetch from GitHub.       | Default branch   |
| `output`      | `string` | Path to save the generated markdown file.        | `codebase.md`    |
| `ignore`      | `array`  | List of file patterns or paths to exclude.       | `[]`             |
| `maxFileSize` | `number` | Maximum file size to process (in bytes).         | `1048576` (1 MB) |

---

## Output Format

The generated markdown file is structured as follows:

````markdown
# Codebase Summary

## File: /src/index.js

```javascript
// File content here
```

## File: /README.md

```markdown
# Project Title

Description here...
```

...
````

---

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch.
3. Submit a pull request with your changes.

---

## License

This library is licensed under the MIT License. See `LICENSE` file for details.

---

## Questions or Issues?

For any questions or issues, please open a GitHub issue in this repository.
