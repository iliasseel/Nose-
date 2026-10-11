# NOSE Luxury Perfume — Signature Fragrance Showcase & Corridor Integration

A minimalist, high-end fragrance landing page for the luxury perfume house **NOSE**, featuring an infinite 3D perspective stream of men's iconic fragrances (`parfum homme` category) converging toward the signature **NOSE Extrait de Parfum** showcase bottle with luxury gold illumination, custom brand logo, and bilingual Arabic/English interface.

---

### User Review & Critical Decisions

> [!IMPORTANT]
> The architectural direction and experience have been aligned with your preferences:
> - **Focus**: Minimalist luxury landing page centered on the signature NOSE fragrance.
> - **Hero Center**: Prominent central showcase bottle with dark marble backdrop, atmospheric gold smoky aura, and refined brand typography.
> - **Corridor Stream**: Left and right 3D perspective rails populated with the 16 masculine fragrance bottles from your catalogue (Sauvage Dior, Bleu de Chanel, Invictus, Ultra Male, 1 Million, Stronger With You, etc.).
> - **Language**: Seamless bilingual Arabic / English toggle with instant typography and RTL/LTR adjustments.

- **Confirmed Decision 1**: Store layout strictly follows a minimalist luxury format avoiding e-commerce clutter, giving full atmospheric weight to the signature scent.
- **Confirmed Decision 2**: Center focal bottle renders the signature NOSE Extrait de Parfum bottle with realistic glass reflections, gold collar detail, and scent note exploration modal/accordion.
- **Confirmed Decision 3**: The site header displays the vector-perfect gold NOSE crown-and-scent emblem as the primary brand mark.

---

### 1. Overview & Core Concept

- **What It Does**: Integrates the 3D perspective `ImageStreamHero` component into a luxury digital showcase for NOSE Parfums. Two rails of high-fashion fragrance flacons sweep forward from deep z-space, framing the hero centerpiece: the signature NOSE Extrait de Parfum bottle. Visitors can toggle between Arabic and English, explore olfactory pyramid notes (Top, Heart, Base), listen to ambient fragrance notes, and place an exclusive order inquiry.
- **Target Audience / Persona**: High-end fragrance connoisseurs, gift seekers, and perfume collectors in the Middle East and internationally looking for bespoke extrait de parfum creations.
- **Key Value**: Replaces conventional flat product grids with an immersive, resolution-independent 3D visual corridor that conveys prestige, depth, and French-Oriental artisanal luxury.

---

### 2. User Experience & Visual Design

- **Key User Flows**:
  1. **Arrival & Reveal**: Seamless loading into a deep obsidian/marble canvas (`#09090b` with warm gold accents). The top navigation renders the official NOSE gold royal emblem, navigation anchors (Signature, Olfactory Notes, Collection, Private Order), and the AR/EN language switch.
  2. **3D Corridor Stream**: The `ImageStreamHero` animates twin rails of catalog perfume bottles (Sauvage, Bleu de Chanel, Invictus, Ultra Male, The One, Scandal, etc.) projecting outward from the vanishing point.
  3. **Signature Centerpiece**: At the focal axis sits the illuminated NOSE Extrait de Parfum flacon with gold foil branding, smoky amber atmospheric backlighting, and a "Discover Notes" interaction.
  4. **Fragrance Notes Drawer / Modal**: Clicking the signature bottle opens the olfactory profile (Bergamot & Saffron, Black Amber & Smoky Oud, Royal Vanilla & Cedarwood) with tactile bottle dimensions (50ml / 100ml Extrait concentration).
  5. **Direct VIP Acquisition Flow**: Simple bespoke order reservation trigger modal allowing customers to secure their bottle via WhatsApp / Direct Inquiry with prefilled details.

- **Visual Identity & Theme**:
  - *Aesthetic Direction*: Haute Parfumerie, Parisian-Arabian luxury, dark marble, warm golden reflections, atmospheric mist.
  - *Color Palette & Tokens*:
    - Canvas (60%): Deep obsidian velvet `#09090b` / Rich charcoal `#121215`
    - Structural Surfaces (30%): Deep smoked glass with hairline metallic borders `rgba(212, 175, 55, 0.15)`
    - Accent (10%): Imperial burnished gold `#D4AF37` / `#F3E5AB`
  - *Typography & Hierarchy*:
    - Display / Headings: `Cinzel` / `Playfair Display` serif for timeless royal prestige.
    - Arabic Typeface: High-legibility modern Amiri / Cairo luxury serif font hierarchy.
    - Body / Details: `Plus Jakarta Sans` with `tabular-nums` for dimensions and concentrations.

- **Interactive Feedback & Motion**:
  - CSS 3D matrix keyframes with `cqw` container queries ensuring zero distortion across resolutions.
  - Reduced-motion accessibility fallback (`prefers-reduced-motion: reduce`) freezing frames at balanced flight positions.
  - Micro-glow expansion and smooth 200ms settling curves on interactive controls.

---

### 3. Key Product Decisions & Trade-Offs

- **Decision 1: Supporting shadcn/ui Project Structure**:
  - *Chosen Approach*: Configure the project to standard shadcn conventions (`@/components/ui/`, `@/lib/utils.ts` with `clsx` and `tailwind-merge`, and `@/` path aliasing in both `tsconfig.json` and `vite.config.ts`).
  - *Why*: Ensures drop-in compatibility with the requested `image-stream-hero.tsx`, `demo.tsx`, and standard UI primitives.
  - *Instructions Provided*: Detailed explanation on shadcn CLI setup (`npx shadcn@latest init --defaults`), path mapping, and utility helpers.

- **Decision 2: Perfume Stream Asset Strategy**:
  - *Chosen Approach*: Curate high-fidelity studio renders representing the 16 masculine fragrance classics from the uploaded catalog (Sauvage, Bleu, Invictus, Hugo Boss, Ultra Male, 1 Million, The One, Gucci Guilty, Scandal, Stronger With You, Acqua Di Gio Profondo, Light Blue, YSL Y, Wanted, Nebras, Ana Abiyedh) along with the central signature NOSE Extrait de Parfum flacon.
  - *Why*: Eliminates broken third-party links, matches the user's uploaded catalog sheet, and guarantees crisp 3D rendering.

- **Decision 3: Bilingual Arabic & English Support**:
  - *Chosen Approach*: Lightweight client-side reactive locale context with RTL/LTR document direction synchronization.
  - *Why*: Matches the bilingual nature of Middle Eastern luxury fragrance retail without requiring complex heavy internationalization dependencies.

---

### 4. Technical Architecture & Data Strategy

```
┌────────────────────────────────────────────────────────────────────────┐
│                              NOSE App                                  │
├────────────────────────────────────────────────────────────────────────┤
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │ Navigation Bar (NOSE Gold Logo • Nav Anchors • AR/EN Toggle)     │  │
│  └──────────────────────────────────────────────────────────────────┘  │
│                                                                        │
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │ Hero Section: <ImageStreamHero>                                  │  │
│  │  ├─ Left & Right Rails: 16 Catalog Masculine Fragrance Cards     │  │
│  │  │  (Sauvage, Bleu Chanel, Invictus, Ultra Male, One Million...) │  │
│  │  └─ Central Focal Stage:                                         │  │
│  │      ├─ Signature NOSE Extrait de Parfum Bottle (Gold Halo)      │  │
│  │      ├─ Royal NOSE Crest & Arabic/English Typography             │  │
│  │      └─ Quick Actions: "Experience Fragrance" & "Reserve Now"    │  │
│  └──────────────────────────────────────────────────────────────────┘  │
│                                                                        │
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │ Olfactory Notes & Artisanal Craftsmanship Section                │  │
│  │  (Top: Saffron & Bergamot • Heart: Oud & Rose • Base: Amber)     │  │
│  └──────────────────────────────────────────────────────────────────┘  │
│                                                                        │
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │ VIP Direct Order / Inquiry Modal (WhatsApp / Instant Checkout)   │  │
│  └──────────────────────────────────────────────────────────────────┘  │
│                                                                        │
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │ Minimalist Luxury Footer with Brand Copyright & Contact          │  │
│  └──────────────────────────────────────────────────────────────────┘  │
└────────────────────────────────────────────────────────────────────────┘
```

#### Directory & Component Organization:
- `components/ui/image-stream-hero.tsx`: Exact copy of the provided 3D perspective hero corridor component.
- `components/ui/demo.tsx`: Interactive demo showing the component as requested.
- `lib/utils.ts`: Standard shadcn `cn` utility combining `clsx` and `tailwind-merge`.
- `src/components/Navbar.tsx`: Top bar adhering to the one-row 3-zone contract with the gold NOSE crest.
- `src/components/SignatureShowcase.tsx`: The focal bottle presentation with gold halo, smoke effect, and olfactory pyramid.
- `src/components/OrderModal.tsx`: Seamless VIP reservation dialog.
- `src/data/fragrances.ts`: Structured dataset containing the 16 masculine fragrance references from the uploaded photo.
