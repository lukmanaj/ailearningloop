# ailearningloop

Personal technical notes, research summaries, and logs by [Lukman Aliyu Jibril](https://lukmanaj.github.io/ailearningloop/), built with [Quarto](https://quarto.org/).

The site is published live at: **[https://lukmanaj.github.io/ailearningloop/](https://lukmanaj.github.io/ailearningloop/)**

---

## Repository Structure

Each blog entry lives within its own subdirectory under `posts/`, following a chronological naming convention (`YYYY-MM-DD-slug/index.qmd`):

```text
ailearningloop/
├── _quarto.yml          # Site configuration and navigation
├── index.qmd            # Blog listing page with search, tag filters, and RSS
├── about.qmd            # Profile and research background
├── posts/                # Blog entries
│   ├── 2025-07-20-.../   # Post directory with associated figures/code
│   │   └── index.qmd
│   └── ...
├── .gitignore
└── README.md
```

---

## Local Development

### Prerequisites

- [Quarto CLI](https://quarto.org/docs/get-started/)
- Python 3.10+ (managed via [uv](https://github.com/astral-sh/uv))

### 1. Environment Setup

To support post execution without modifying system Python packages:

```bash
# Create local virtual environment
uv venv

# Install execution dependencies
uv pip install jupyter ipykernel
```

### 2. Live Preview

Run the Quarto preview server pointing to the virtual environment:

```bash
QUARTO_PYTHON=".venv/bin/python" quarto preview
```

Or activate the environment first:

```bash
source .venv/bin/activate
quarto preview
```

The preview server will monitor all `.qmd` and asset changes and reload automatically at [http://localhost:4200](http://localhost:4200).

### 3. Build

To render the complete static site for production:

```bash
quarto render
```

---

## Creating a New Post

1. Create a dated directory in `posts/`:

   ```bash
   mkdir posts/YYYY-MM-DD-post-title
   ```

2. Add an `index.qmd` file with standardized frontmatter:

   ```yaml
   ---
   title: "Post Title Here"
   description: "Brief summary for listings and metadata."
   author: "Lukman Aliyu Jibril"
   date: "YYYY-MM-DD"
   categories: [machine-learning, python, notes]
   execute:
     eval: false # Set to true if executable code cells are present
   ---
   ```

3. Save any supporting images or datasets directly in that directory and reference them with relative paths.

---

## License

Content and writing © Lukman Aliyu Jibril. 
