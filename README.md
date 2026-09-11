# mdprint-pack-starter

A ready-to-fork **template pack** for [mdprint](https://github.com/filip-cokesh/mdprint) —
brand your Markdown → print-quality HTML documents with your own logo, colors,
fonts and footer (including social links with icons).

*Česká verze návodu: [README.cs.md](README.cs.md).*

**Live demo:** [filip-cokesh.github.io/mdprint-pack-starter](https://filip-cokesh.github.io/mdprint-pack-starter/) —
Markdown source next to the result rendered with this pack (CS/EN/DE).

A pack is just a folder loaded at run time — no rebuild of mdprint needed:

```
pack.toml          identity: [pack] name, [company] footer, [[links]], [[fonts]]
template.css       the look: accent color, fonts, header/footer, print rules
logo-light.png     logo for light mode and print (optional)
logo-dark.png      logo for dark mode (optional)
icons/github.svg   footer link icon, inlined into the HTML (optional)
```

Try it right away:

```
mdprint --template path/to/mdprint-pack-starter document.md
```

Footer links (`[[links]]`) require **mdprint ≥ 0.4.0**.

## Make it yours

1. **Use this template** (button above) or fork the repo, then clone it.
2. **Logos** — replace `logo-light.png` (light background + print) and
   `logo-dark.png` (dark background). Any size; `template.css` scales it.
   Delete both if you don't want a logo — the header still shows the name.
3. **Accent color** — in `template.css` set `--brand-accent` (and the link
   colors) in three places: light mode, and the two dark-mode blocks (use a
   *lighter* step of your hue there; aim for ≥ 4.5:1 contrast on both
   backgrounds).
4. **Footer** — fill in `[company]` in `pack.toml`; delete fields you don't
   need. Every field can still be overridden per project from `mdprint.toml`.
5. **Links** — edit the `[[links]]` blocks: label, URL, optional `icon`
   (SVG/PNG inside the pack; monochrome icons are auto-inverted to white in
   dark mode).
6. **Fonts** — either embed WOFF2 files via `[[fonts]]` (**only if the font
   license allows redistribution** — the files end up base64-inlined in every
   generated HTML), or just name the font in `--font-sans` in `template.css`
   and let readers without it fall back (the safe choice for licensed
   corporate fonts).
7. Rename the pack in `[pack] name` and run
   `mdprint --template . document.md` on a test file. Check light mode,
   dark mode (the ◐ toggle) and print preview (Ctrl+P).

## Trademarks

- The GitHub mark (`icons/github.svg`, from [Octicons](https://github.com/primer/octicons),
  MIT) is a trademark of GitHub, Inc., used per the
  [GitHub logo guidelines](https://github.com/logos) as a social button
  linking to GitHub. If your links point elsewhere, use that service's icon
  and follow its brand rules.
- The mdprint logo in `logo-light.png` / `logo-dark.png` belongs to the
  mdprint project — replace it with your own artwork in your pack.

## License

MIT — see [LICENSE](LICENSE). Trademark exceptions above.
