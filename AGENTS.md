# handbook: instructions for agents

This repo holds what spans repos and how we work. Read [README.md](README.md) first.

- **Scope.** Nothing private goes here: no personal details, no domain names,
  no addresses, no secrets. The repo is public.
- **Pages** follow [how-we-work/write-pages.md](how-we-work/write-pages.md):
  the header, one of five types, the shape of that type.
- **Where a page goes.** Here if it is about more than one repo or about how we
  work. In the code repo if a change to that code could make it wrong.
- **Repos and systems** are named only in `registry.yaml` and in a system's own
  overview under `systems/`.
- **`INDEX.md` is generated**: run `uv run tools/build_index.py` and commit the
  result. Do not edit it by hand.
- **`reviewed`** changes only when you checked the page against reality.
- Branch and pull request; never push to `main`.
