# Prompt Template Preflight

Paste a prompt template and get a local report: unfilled variables, an approximate token and length estimate, flagged prompt-injection patterns, and simple quality checks. No server, no tracking, no third-party scripts.

**Live demo:** https://0xelitesystem.github.io/prompt-template-preflight/

## Use

Open `index.html` in any modern browser, or visit the GitHub Pages link in the repo description.

Paste a template and the tool reports:

- Length estimate: characters, words, lines, and a rough token count (about 4 characters per token).
- Unfilled variables: every `{{variable}}` placeholder still present, with repeat counts.
- Potential prompt-injection patterns: heuristic matches for overrides ("ignore previous instructions"), role reassignment ("you are now"), fake role tags (`<system>`), jailbreak phrasing, and requests to reveal the system prompt.
- Quality checks: not empty, has an instruction cue, enough content, balanced placeholder braces, and whether it trails off on a colon.

Empty input is caught with a visible error.

## Why this exists

Prompt templates rot quietly: a placeholder gets renamed and never filled, an untrusted field opens an injection hole, or a template ships with no actual instruction. This runs a few cheap heuristics over the raw text so you catch those before shipping, in a single file with no dependencies.

## Privacy

Everything runs in your browser. The template you paste never leaves your machine. Verify by viewing the page source or by opening DevTools and watching the network tab, no requests are made.

## Run locally

```bash
git clone https://github.com/0xelitesystem/prompt-template-preflight
cd prompt-template-preflight
# Open index.html in your browser, or:
python -m http.server 8000
```

## Build

There is no build. It's a single HTML file.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT.

## Related

- [prompt-cost-across-models](https://github.com/0xelitesystem/prompt-cost-across-models)
- [context-window-gauges](https://github.com/0xelitesystem/context-window-gauges)
- [agent-instructions-file-builder](https://github.com/0xelitesystem/agent-instructions-file-builder)
