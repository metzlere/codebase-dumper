# Codebase Dumper

**Codebase Dumper** is a command-line utility designed to scan a given codebase, generate a visual directory tree, and extract the contents of the source files into a Markdown file. This output is ideal for feeding into prompts to LLMs or for documentation purposes.

I use this regularly to provide the context of an entire codebase in a prompt to a powerful LLM. Large codebases will need to be pruned or the LLMs will struggle to provide satisfactory responses. Smaller models especially struggle. 

Almost all of the code was written by o3-mini-high and required minimal editing following a sophisticated prompt detailing my exact needs and desired functionality. 

## Features

- **Directory Tree Visualization:** Generates a structured view of your codebase’s directories.
- **File Content Extraction:** Scans and extracts contents from files with specific extensions.
- **Flexible Filtering:** Include or exclude specific files and directories.
- **Markdown Output:** Produces a well-formatted Markdown file that’s easy to read and share.

## Requirements

- No additional packages are required (only standard library modules are used).
- Virtual environment is optional given no additional packages are required

## Installation

1. **Clone the repository. codebase-dumper should be a sibling to the target directory:**
   ```bash
   git clone https://github.com/yourusername/codebase-dumper.git
   cd codebase-dumper
   ```

## Usage

Run the script from the command line, one level up from target directory:

```bash
python codebase-dumper/codebase_dumper.py --root-dir target_directory --output-file dump.md
```

### Command-Line Arguments

- `--root-dir`: Root directory of the codebase to scan (default: `./src`).
- `--output-file`: Path to the output Markdown file (default: `codebase_dump.md`).
- `--include-files`: Specific file names to include (overrides other filters).
- `--exclude-files`: Specific file names to exclude.
- `--excluded-dirs`: Directories to exclude (default: `.git`, `node_modules`, `venv`, `__pycache__`).
- `--extensions`: File extensions to include (default: `.py`, `.js`, `.html`, `.css`, `.json`).

Example:
```bash
python codebase_dumper.py --root-dir ./my_project --output-file my_dump.md 
```

## License

This project is licensed under the MIT License.
