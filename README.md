# WKG Realm Pack

A Minecraft Bedrock add-on built for Realms. It combines **Cannabis Craft**, a full cannabis growing, breeding and processing system, with **Farmer's Delight Bedrock** for cooking and farming. Everything runs on stable APIs, so no experimental toggles are needed.

- **Version:** 1.2.3
- **Minecraft:** Bedrock 1.26.50 or newer
- **Script API:** `@minecraft/server` 2.10.0 and `@minecraft/server-ui` 2.2.0
- **Experiments:** none required. Works on Realms and in worlds with experiments off.

---

## Features

### 🌱 Growing
- **18 strains**, each with its own THC %, yield, growth speed and potion effects.
  - **Common (9):** crafted from wheat seeds and a dye. OG Kush, Blue Dream, Sour Diesel, Purple Haze, Gorilla Glue, Green Crack, Tysgorilla, Tender Lad, Purple Nurple.
  - **Breed-only (3):** a 30% chance when crossing the right pair of pure parents. White Widow, Purple Punch, Skywalker OG.
  - **Trade-only (3):** sold by the Funguy. George Droid, Sleepy Joe OG, Black Mamba.
  - **Funguy exclusives (3):** effects no other strain has. Phantom Cookies (Invisibility), Poseidon OG (Conduit Power), Hero Haze (Hero of the Village).
- **Unique seeds.** Every new seed rolls its own stats (THC ±20%, yield ±1, growth ±15%). Only harvesting copies a plant's exact genetics, so seeds from one plant stack together.
- **Seed info.** Seeds show their THC, yield, growth, effects and rarity in the tooltip. Seed names are coloured by their effects.
- **Custom crops.**
  - 5 growth stages, with tall 1.5-block flowering plants.
  - Buds are tinted by strain: green, purple, frosty, dark, golden or red.
  - Hydrated farmland grows plants 40% faster.
  - Bone meal works on them.
- **Nutrients.** THC, Yield and Growth boosters, up to 3 of each per plant.
- **Seed sources.**
  - Breaking grass has a 5% chance to drop a common seed.
  - A fully grown plant always drops 1–3 seeds along with its buds.
- **Tobacco.** A separate crop that feeds blunts and cigarettes.

### 🧬 Breeding Station
- Cross any two seeds to make a hybrid. The hybrid mixes the parents' stats and keeps up to 3 effects.
- **Effect level-ups.** If both parents have the same effect at the same level, the child can gain a level:
  - 50% chance of II, 25% III, 12.5% IV, 6.25% V
- **Naming.** Name your hybrid and give it a colour. There are 16 colours, plus Random and **Rainbow**.
- A detailed machine model.

### 🔥 Processing
| Station | What it does |
|---|---|
| **Drying Rack** | Dries up to 16 buds (or tobacco leaves) in real time. Dried buds give better results later. |
| **Nug Press** | Presses 4–32 buds into rosin (65–75% THC), with an animated press. Install a copper, iron, diamond or netherite plate for a 20%, 33%, 50% or 70% yield. |
| **Distiller** | Refines rosin into concentrates, each fuelled by a different item. **Wax** uses coal, **Shatter** a blaze rod, **Live Resin** magma cream (every effect +1 level), and **Distillate** an ender pearl (up to 99.9% THC). |
| **Rolling Table** | Combines several strains into one product (details below). |

### 💨 Smoking
- **Joints** hold up to 4 strains and **blunts** up to 8.
- **Bongs** take buds, shatter or wax (up to 6 strains). A bowl packed only with concentrates is a "Dab".
- **Vape pens** take a cart of distillate or live resin and give 16 hits.
- **Cigarettes** and a **12-cigarette pack** give Swiftness I.
- Each hit applies the strain's effects. Higher THC makes the effects last longer, and strong strains get a level bonus.
- **Hold to smoke.** The item raises to your mouth with a sound and smoke particles, and it visibly burns down or empties with each hit.
- **Held models.**
  - Joints, blunts, cigarettes and vapes are 3D sticks, and the bong is 3D glass.
  - The cigarette pack is animated: a cigarette slides out to your mouth and stays lit there.
- **Offhand smoking.** Double-tap sneak and hold.
- **Views.** First person and third person each have their own poses. The rigs don't change the player skeleton, so they're safe with Persona skins.

### 🍄 The Funguy trader
- A mushroom-capped villager who sells rare seeds, plates, rolling papers, carts and machines. He also buys shatter.
- Some villages get a resident Funguy. A wandering one sometimes shows up near players.
- Every Funguy has his own random stock of up to 6 trades.
- Prices react to demand, and the Hero of the Village discount applies.

### 📖 Guide book
- New players get a signed **Cannabis Guide** book on their first join.
- It covers every mechanic and lists every strain, with in-text icons.
- Use a plain book on a Breeding Station to get another copy.

### 🍳 Also included
- **Farmer's Delight Bedrock**: cooking pots, skillets, cutting boards, new crops and meals. It's an unofficial MIT-licensed port.
- **Low Fire:** shorter fire textures (GPL-3.0).
- **Vibrant Visuals** material support for the machines, bong and vape.
- Translations in 7 languages: en_US, es_ES, it_IT, pt_BR, tr_TR, zh_CN, zh_TW.

---

## Installation

1. Download `WKG_Realm_Pack_v<version>.mcaddon` from Releases and double-click it. Minecraft imports both packs.
2. **In a world:** go to Settings → Behavior Packs and activate **WKG Realm Pack BP**. The resource pack is added automatically.
3. **On a Realm:** go to Realm settings. Activate the BP under Behavior Packs and the RP under Resource Packs. When updating, remove the old version first.

---

## For developers

```
development_behavior_packs/WKG_Realm_Pack_BP/   behavior pack (scripts/cc_main.js holds all Cannabis Craft logic)
development_resource_packs/WKG_Realm_Pack_RP/   resource pack (models, textures, attachables, animations)
cc_tools/     Python generators for textures/models/items, the audit and the release builder
cc_tests/     Node test runner with fake @minecraft/server modules
CLAUDE.md     detailed design notes and conventions
BEDROCK_ADDONS.md   Bedrock add-on development reference
```

```bash
node cc_tests/run_tests.mjs          # logic tests (15 suites)
node cc_tools/audit.js               # cross-reference, Bedrock limits and Realm checks
python cc_tools/build_release.py --bump 1.2.4   # build .mcpack + .mcaddon into releases/
```

The Python tools need `pip install numpy pillow scipy`.

---

## Credits

- **Cannabis Craft:** WKG.
- **Farmer's Delight Bedrock:** an unofficial port (MIT). See the pack's license files.
- **Low Fire V1.0.9:** GPL-3.0. See `LICENSE_LowFire.txt` and `CREDITS.txt` in the resource pack.

*This is a fan-made add-on. It is not affiliated with Mojang or Microsoft.*
