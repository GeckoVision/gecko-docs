# Diagram sources

The three architecture diagrams are generated with [archify](https://github.com/tt-a1i/archify)
from the typed specs in this folder — edit the spec, re-render, never hand-edit the HTML.

```bash
node bin/archify.mjs deliver architecture architecture.archify.json ../architecture.html --quality showcase
node bin/archify.mjs deliver architecture architecture-context.archify.json ../architecture-context.html --quality showcase
node bin/archify.mjs deliver sequence     architecture-onchain.archify.json ../architecture-onchain.html --quality showcase
```

The PNGs beside them are screenshots of the same output (1238×992, cropped to the content column).
