# Agent Instructions

## Git Workflow

- Do not push directly to `master`. The branch is protected and GitHub rejects direct updates.
- Make changes on a topic branch.
- Push the topic branch to `origin`.
- Open a pull request targeting `master`.
- Wait for required checks to pass.
- Merge the pull request after checks pass.
- Delete the topic branch after merging when appropriate.

## Local Development

- Use the Homebrew Ruby if the system Ruby is too old for the locked Bundler version: `/opt/homebrew/opt/ruby/bin/bundle`.
- Install dependencies with `/opt/homebrew/opt/ruby/bin/bundle install`.
- Build the site with `/opt/homebrew/opt/ruby/bin/bundle exec jekyll build`.
- Start the local server with `/opt/homebrew/opt/ruby/bin/bundle exec jekyll serve --host 127.0.0.1 --port 4000`.
- Open `http://127.0.0.1:4000/` to preview the site.
