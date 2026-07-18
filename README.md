# designedbykoda

**[designedbykoda.com](https://designedbykoda.com)** — a portfolio of custom PCB hardware, ESP32 projects, RF tools, and the occasional game, designed and built by Koda.

<!-- Swap this for a real screenshot once the site has one — public/images/ has placeholder folders ready. -->
<!-- ![Site preview](./public/images/preview.jpg) -->

## About

I'm 16 and I design and build custom electronics — mostly custom PCBs, ESP32-based hardware, and RF/wireless tools, funded month to month through a couple of JLCPCB sponsorships. Everything on the site is fully custom: schematic, PCB layout, enclosure, and firmware, all written and designed from scratch.

The site covers projects like:

- **[RF Tool](https://designedbykoda.com/projects/rf-tool/)** — flagship multi-radio RF analysis platform with a touchscreen UI
- **[Phantomware](https://designedbykoda.com/projects/phantomware/)** — a fully custom Flipper Zero–style multi-tool
- **[Dual VFD Display Board](https://designedbykoda.com/projects/vfd-display-board/)** — a retro VFD desk display with a fully custom driver
- **[LoRa Portable Messenger](https://designedbykoda.com/projects/lora-portable-messenger/)** — a rugged, GPS-aware handheld messenger
- ...and a growing list of smart home devices, RF tools, and a narrative pixel-art RPG

See the full list at [designedbykoda.com/projects](https://designedbykoda.com/projects).

## Tech stack

- [Astro](https://astro.build) — static site generation
- Markdown content collections for project data (`src/content/projects/`)
- Hosted on [Cloudflare Workers](https://developers.cloudflare.com/workers/)
- No frameworks, no JS bloat — plain HTML/CSS with a bit of vanilla JS where it matters

## Running locally

```bash
npm install
npm run dev
```

Then visit `http://localhost:4321`.

```bash
npm run build     # production build to ./dist
npm run deploy    # deploy to Cloudflare Workers
```

## Project structure

```
src/
├── components/       reusable bits (cards, header/footer, image placeholders)
├── layouts/           page shells, including the per-project detail layout
├── content/
│   ├── projects/      one markdown file per project — this is what powers the site
│   └── blog/          unused starter demo content
├── pages/              routes: home, /projects, /projects/[slug], /about
└── styles/             global dark theme
```

Adding a new project is just a new markdown file in `src/content/projects/` — see the comments in an existing entry for the frontmatter format. Photos are placeholdered automatically: drop an image into the matching `public/images/projects/<slug>/` folder and it swaps in with no code changes.

## License

Code is available under the MIT License. The project write-ups, photos, and any original designs described within are not — please don't reuse those without asking.

## Contact

- GitHub: [@agekoda](https://github.com/agekoda)
- Site: [designedbykoda.com](https://designedbykoda.com)
