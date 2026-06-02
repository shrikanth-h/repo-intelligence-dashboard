# Contributing

Thanks for thinking about contributing. The atlas is opinion-driven, so not every suggestion will be merged — but every thoughtful one is read.

## The fastest path: file an issue

If you're proposing a new repository to add, the [**Suggest a repository**](https://github.com/shrikanth-h/repo-intelligence-dashboard/issues/new?template=repo-suggestion.md) issue template is the lowest-friction route. It asks for the URL, a one-line classification, the category it belongs to, and your reason for proposing it.

Maintainer time is the bottleneck. A clean issue takes a minute to triage; a vague one takes ten.

## The thorough path: open a PR

If you want to add the full entry yourself:

1. Open `index.html` and find the `repositories` array near the bottom of the file (search for `// === REPOSITORY DATA ===`).
2. Use the in-page form (the **Add or update** section) to generate a JSON entry. Paste a GitHub URL; the form auto-fills metadata, topics, language, license, and latest release. Fill in the interpretive fields (classification, category, features, use case, alternatives, diagram).
3. Append the generated object to the `repositories` array. Keep entries grouped roughly by category, but exact placement isn't strict.
4. Open a PR.

Or, equivalently, do the same by hand. The form is convenience, not requirement.

## The curation bar

A repository is a good fit if **all** of the following are true:

- **Open-source**, with a license file present in the repo. No source-available, no "open core" with the interesting parts behind a paywall.
- **Actively maintained**, or interesting enough to include as a historical anchor (rare). "Active" means real commits in the last 6 months for live entries.
- **Discoverable but useful** — popular enough to be findable, or obscure enough that surfacing it is the value. Either case is welcome; the middle (popular and well-documented elsewhere) adds the least.
- **Distinguishable**. If there are already three near-identical entries in the same category, a fourth needs to articulate what it does differently.
- **Adoptable**. It should be possible to install and try the thing in under an hour with the materials linked from the entry.

## Entry quality bar

Each repository entry should carry:

- **Original prose** in the description and use case. Don't paste the upstream README's tagline; write your own one-liner from the perspective of someone considering adoption.
- **A real-world use case** — one paragraph, narrative, concrete. "An engineering team uses X to do Y" is the shape. Avoid abstractions.
- **A Mermaid architecture diagram**. It doesn't need to be exhaustive — five to nine nodes is the right scale. Show the *shape* of the system, not every component.
- **Two to five alternatives** in the same problem space, by name. This is part of what makes the atlas useful.
- **Install commands** that actually run on a clean machine. If there are environment variables required, mention them.
- **Stack tags** that are accurate. "Python" if the user runs Python; "TypeScript" if they run TypeScript. Don't pad.

## What gets declined

- Marketing pages, course landing pages, paid products with a thin OSS veneer.
- Repositories that are mirrors, archives, or wrappers without substantive original content.
- Hot-take repos (someone's 200-star weekend project that's mostly README).
- Anything where the description has to obscure what the project actually does.

A decline isn't a judgement on the project — it's a curation decision about *this* atlas.

## Style notes

- **Prose voice**: editorial, plain, no hype. "Cutting-edge", "revolutionary", "game-changing" are immediate cuts.
- **Descriptions**: one to two sentences. The deep-dive card carries the detail; the index card is the headline.
- **Categories**: pick one. A repo can be tagged with multiple stack labels, but one primary category. If you genuinely can't decide between two, that's a signal the entry might need rethinking.

## Reporting problems

Found a stale entry, broken link, or factual error? Use the [bug report template](https://github.com/shrikanth-h/repo-intelligence-dashboard/issues/new?template=bug-report.md). Include the repo `id` if you know it.

## Code of conduct

By participating, you agree to abide by the [Code of Conduct](CODE_OF_CONDUCT.md).

## License

All contributions are licensed under [MIT](LICENSE), matching the project. By submitting a PR you affirm you have the right to license the contribution this way.
