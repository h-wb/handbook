# handbook: instructions for agents

What spans repos, and how things run. Read [README.md](README.md), then [Systems/Handbook.md](Systems/Handbook.md), which is the standard for every page here.

## Reading

- Do not read the whole handbook. Read `README.md`, then the one system page for what you will touch.
- Every page in one screen: `grep -r --include='*.md' --exclude-dir=Templates '^summary: .' .` gives one line per page. Open a page only if its summary says you need it.
- Everything about one system: `grep -rl '\[\[Board\]\]' .`, here and in the code repos.
- A page is short on purpose. If you need more than one screen from it, the detail belongs in the code repo it links to.

## Writing

- Nothing private goes here: no personal details, no domain names, no addresses, no secrets. The repo is public.
- Properties are the vault's: lowercase keys, alphabetical, `created` last, links as `"[[Name]]"`, no empty properties, no tags. Start a page from `Templates/`.
- A system page is named for its role, with today's product in `aliases`. Other pages name the role and link to it. A repo is described only on its own page in `Repos/`.
- A page goes here if it is about more than one repo or about how things run. If a change to one repo's code could make it wrong, it goes in that repo.
- `reviewed` changes only when you checked the page against reality.
- Style: plain and dense, no commentary about the page itself, few em-dashes, little bold. Shorten before appending.
- A replaced or dropped page moves to `Archives/`. Nothing is deleted.
- After editing a `.base`, check it has no duplicate YAML key.
- Branch and pull request; never push to `main`.
