# Website Repository

A Jekyll-based blog built with Ruby.

## Prerequisites

- **Ruby 3.4.4** - Specified in `.ruby-version`
- **rbenv** - For managing Ruby versions (recommended)

## Setup

### 1. Install Ruby 3.4.4 with rbenv

```bash
rbenv install 3.4.4
rbenv local 3.4.4
```

### 2. Initialize rbenv in your shell

Add to your shell config (`~/.zshrc` or `~/.bashrc`):

```bash
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init - zsh)"  # or bash if using bash
```

Then reload your shell or run `source ~/.zshrc` (or `~/.bashrc`).

### 3. Install dependencies

```bash
cd docs
bundle install
```

## Development

Start the local development server:

```bash
cd docs
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000` and will automatically rebuild when you make changes.

## Project Structure

- `docs/` - Jekyll site content and configuration
- `docs/_posts/` - Blog posts
- `docs/_config.yml` - Site configuration
- `docs/Gemfile` - Ruby gem dependencies
