# 🔮 [H A W T H O R N E](https://github.com/Coneja-Chibi/The-HawThorne-Directives) 🔮

## Paramnesia · V.4 → VI

> *Directors went missing, new forms to file, we don't pay these bitches overtime*

⊹ ── ✧ ── ⊹

### 📐 The shape of the change

VI is almost a completely different preset as I change around ideas.

A third fewer blocks carry nearly twice the text. The median block got *smaller*, 573 chars down to 176, while the largest grew sevenfold. V.4 was a long shelf of medium prompts you toggled by hand. VI is a handful of enormous engines surrounded by tiny switches that feed them.

⊹ ── ✧ ── ⊹

### ⚙️ The state machine 

V.4 had **no macro engine at all**. Every piece of memory was a prompt asking the model to remember something.

VI runs **20 hooks** over the model's own output, 34 sets, 5 appends, 2 pushes and 2 unsets, that read tags out of the prose and write them to variables before the next turn assembles. The records aren't asked to be remembered, they're caught.

**Stage and commit.** Catchers write only to `staging_*`. A reset clears all 21 staging slots at the head of every passage, and init commits them once. This is what makes a swipe safe: re-rolling a turn cannot corrupt tracked state, because nothing is live until it commits. The reset must fire *before* the writers.

### 🔧 Fixes

- **The model no longer plans {{user}}.** The old reasoning layer quietly forecast and scripted the protagonist's next move, which taught the model it was allowed to. {{user}} and the {{operator}} are now treated as separate entities with explicit wants. Your operator choice changes themes heavily.
- **The reasoning stopped tripping the guards.** Visible `<think>` planning read as a jailbreak and gets increasingly refused by advanced models as a distillation attempt. 
- **One prompt stopped fighting every backend.** Model families fail in different directions. Instead of a single file losing to all of them, VI ships tuned per-model editions.
- **Swipe safety.** Record catchers write to staging only and commit once, so re-rolling a turn no longer corrupts the tracked state.

### ✨ New Systems

- 📋 **Records.** The chain-of-thought is gone. Every Director files a department form now: its own bureau, its own paperwork, its own strike mechanic. The model reasons by filling out the record. All twenty Directors' sheets live in one 215 KB lens, gated per callsign, the largest block in the preset.
- 📊 **Director Instruments.** Each Director reasons in its own math machine. Odds, dose, cost, reserve, spread. Outcomes are priced, not chosen: every number is read off the scene and spent on the scene, and the guilt goes to the arithmetic rather than the model. Each director gets its own custom CoT.
- 🎭 **Three Record Formats.** One toggle, three ways to read it. **Letter** (the bespoke case-file card), **Panel** (bars, base-rate to P odds, a severity ladder), **Search** (the Director's own retrieval terminal). Every Director carries a bespoke version of all three, which is where most of that 215 KB went.
- 👤 **The Operator.** A seat above {{user}}. The real hand running the protagonist, with pick-one dossiers (Maria, Dez, Theo, Gordie) plus a floor, an override, and levers the scene reads without ever naming them. Six new blocks: Dossier, Floor, Snippet, Wants, Override, Vessel.
- 💋 **Director Demos.** Each Director ships a worked example as an assistant turn, so the model has a concrete target to match rather than instructions to obey.
- 🕯️ **The Boot.** A staged open across three machines: the Principle, the assignment and model sheet, a glossary of base terms, then the operator. Three turns, gaslit on purpose.
- 🎬 **Scene Shapes & the Scene Library.** A menu of scene shapes with a per-shape resolver, so the Director builds the right kind of scene instead of one default one.
- 🎞️ **The Booth (HawThorne Form).** An arc-planning turn that lays the next beats as Propp functions, then writes into them. Plans the story, does not script you.
- 🌍 **World Form.** A dedicated world-logic machine for the turns that are about the world moving rather than a character acting. Replaces the dissolved World Logic section with something that runs instead of instructs.
- 🔞 **The Clearance Handshake.** Content gating is a two-step ask-then-confirm now instead of a wall of standing toggles.
- 🗂️ **Shared State + Tags.** A running state ledger the records write to, so the world holds its facts between turns.
- 🎨 **Visual Artifacts, v2.** The scene-state HTML (weather, mood, the lights-out card) rebuilt as field-parameterized templates driven straight off the fiction instead of hand-authored one-offs.

### 🎛️ The dials, in full

VI exposes **19**:

| Dial | Options |
|---|---|
| 🧭 **Story Mode** | Driven · Balanced · Exploratory |
| ⏱️ **Pacing** | Sprint · Brisk · Standard · Literary · Glacial |
| 🃏 **Fortune** | Kind · Level · Crucible |
| 🎬 **Director Switching** | HawThorne casts · Roster pick · Auto-roll |
| 🎭 **Director** | pick many, from the twenty |
| 🎛 **Record Format** | Panel · Letter · Search |
| 👤 **Operator Dossier** | Maria · Dez · Theo · Gordie |
| 🎲 **World Events** | Off · Some · Lots, plus **Rolled** as its own toggle |
| 👁 **POV** | First · Second · Third |
| 🕰 **Tense** | Past · Present · Future |
| 📏 **Length** | Punchy · Standard · Sprawling |
| ✒️ **Style** | Roleplay · Literary · Standard |
| 🔞 **Content Clearance** | pick many, ten categories, behind the handshake |
| 🫙 **Vessel** · 🎨 **HTML Visuals** · 🐰 **BunnyMo** · 🧹 **Prose Floor** | toggles |
| 🌐 **Language Selector** | free input |

### 🔄 Reworked & Renamed

- ⚙️ **Affinities, recoined.** V.4's flat list of **26 pick-your-own** affinities (TELESCOPING, SWITCHBACK, GALLOWS GRACE, MESSY SHEETS...) became **19**, recoined as glossary cards with invented names and keyed per Director instead of chosen by hand. V.4's three affinity section blocks are gone, and one **Affinity Engine** stands where they were.
- 🃏 **Difficulty → Fortune.** The five-step Casual / Normal / Hard / Brutal / Suicide dial condensed into **Kind / Level / Crucible**.
- ⏱️ **Pacing, moved and widened.** Pulled out of World Logic into its own section, from three settings (Slow Burn / Unstable / Accelerant) to five (Sprint to Glacial).
- 🗣️ **Voice Engine → Voice & World Floor.** The old voice pass grew into an always-on floor: accents always, articulation over polish, cultural awareness that refuses to launder itself.
- 📏 **Length renamed.** Short / Long / Adaptive became Punchy / Standard / Sprawling.
- 🔞 **Content Warnings → Content.** Same coverage, renamed, run through the Clearance handshake instead of standing toggles.

### 🎭 The Directors

- 🔁 **Rebuilt.** Each Director keeps its genre lens but was rebuilt from the inside out: its own Instrument, its own Record in three formats, its own Presence dossier, its own Demo.
- 🗑️ **Roster cut, 23 → 20.** **SCORIA**, **TRIPWIRE**, **REQUIEM**, and **GRAVITAS** were struck from the wall. **MILQUETOAST** clocked in. (He's such a lil cutie!)
- 🎬 **Dispatch.** A Director Spec block and a switching machine replace V.4's hand-picked framing. Each Director now owns a `dir_<CALLSIGN>` state pair, twenty of them, which is where a third of the new variables went.
- ⚔️ **Director Framing, struck.** Adversarial and Hostile Takeover did not survive, and the README and its optional block came down with them.

### 🗑️ Removed & Retired

- 🌍 **World Logic, dissolved.** The whole section came down, seven blocks with it. Pacing and Difficulty were rehomed. **Epistemic Mode** (Behind / Alongside / Ahead / Dark) and **Director Framing** (Adversarial / Hostile Takeover) did not survive the move.
- 🧠 **The tiered chain-of-thought.** The old Baseline / Overclocked CoT and its System and Assistant prefills are gone, replaced wholesale by Records.
- 🎨 **Prose Color.** Beige, clear, blue, purple, red. The whole dial. (Will likely come back in a later version.)
- 🎲 **The QC toggle wall.** World Persistence, Information Rules, and the rest. The ones worth keeping were folded into the always-on floors.
- 📖 **Narrator options.** Hopping, Authored, Objective, Deep, and Character narrators. Gone. POV is First / Second / Third now.
- 🔄 **The prose rotations.** Purposeful Mistake, Contradictory Actions, Dialogue Rotation, and Prose Technique Rotation.
- 🎭 **Mood lenses.** Smitten, Heavy, Eager, Hungover, Pent-Up, Playful, Tense. All seven.
- 👁️ **Senses**, 👤 **Role**, 🎭 **User Reference**, ⚙️ **Causal Engine.** The pick-many walls, struck with the rest of the toggle shelf.
- 🔫 **Chekhov's Gun Rack** and 📖 **Prose Examples.** Cut from Gadgets, only BunnyMo remains. Gun struck cause name has been coined elsewhere, and the idea has evolved into an entire state machine instead of just one tracker.
- ✏️ **Pulp and Screenplay.** Prose styles trimmed from five to three (Roleplay, Literary, Standard).
- 🧹 **130 variables retired.** `chekhov_*`, `bsm5_*`, `acrostic_*`, `active_lens`, `causal_engine_*` and the rest of V.4's bookkeeping went out with the sections that wrote them.

### 📦 New Preset Versions

The single V.4 file is now eight editions: **RC/Standard**, **Deep Blue**, **Grandier**, **Hemlock (EX)**, **Brainrot(EX)**, **Yin(EX)**, **Yang(EX)**, and **Vessel**
(EX for Experimental)
⊹ ── ✧ ── ⊹

-# 🔮 ~~the Directors filed their own missing persons reports~~
