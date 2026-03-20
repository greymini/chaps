# 📚 Master Prompt: Class 10 Science — Interactive Chapter Webpage Generator

> **How to use this file:**  
> Copy the entire prompt block under **"THE PROMPT"** and paste it to Claude.  
> Replace every `[BRACKETED PLACEHOLDER]` with the specific chapter details before sending.  
> The chapter-specific fill-in guide for all 13 chapters is at the bottom of this file.

---

## THE PROMPT

---

You are an expert science educator and senior frontend developer. Your task is to generate a **complete, single-file, self-contained HTML webpage** for **[CHAPTER NUMBER]: [CHAPTER NAME]** from the Class 10 NCERT Science syllabus.

This page will be used by **Class 10 students (age 14–16)** as an interactive study companion. It must be engaging, accurate, beautiful, and work perfectly when opened directly in any browser — no build tools, no server, no npm. One `.html` file, everything inside it.

---

## PART 1 — CONTENT ACCURACY (READ THIS FIRST, NON-NEGOTIABLE)

### 1.1 Primary Source
All factual content — definitions, laws, formulas, equations, values, reactions, diagrams — must be sourced from the **NCERT Class 10 Science textbook** for **[CHAPTER NUMBER]: [CHAPTER NAME]**. Do not invent, paraphrase carelessly, or extrapolate beyond what NCERT states for any formula, law, reaction, or definition.

### 1.2 What "enriched content" means
You may add:
- Real-world analogies and applications that make concepts tangible
- Memory tricks and mnemonics
- "Did You Know?" facts that connect the topic to everyday life
- Historical context (who discovered it, when, why it mattered)
- Exam tips and common mistake warnings

You must NOT add:
- Any formula, value, or law not present in NCERT Class 10 for this chapter
- University-level derivations or concepts beyond Class 10 scope
- Invented examples that could confuse or misinform

### 1.3 Verification rule
Before including any enriched fact (not from NCERT), mentally cross-verify it against at least **two reliable sources** (e.g., NCERT itself, verified educational references, established scientific knowledge). If there is any doubt, remove it or clearly label it as "Beyond Syllabus — For Curiosity Only."

### 1.4 Chapter-specific content to cover
Cover **all topics** listed here for **[CHAPTER NAME]**:

```
[PASTE THE COMPLETE TOPIC LIST FOR THIS CHAPTER HERE]
Example for Ch.9 Light:
- Reflection of light, laws of reflection
- Spherical mirrors: concave, convex
- Mirror formula, magnification, sign convention
- Refraction of light, Snell's law, refractive index
- Lenses: convex, concave, image formation tables
- Lens formula, magnification, power of a lens
```

---

## PART 2 — PAGE STRUCTURE

The page must be divided into **clearly labelled sections**, one per major topic of the chapter. Use the following structure:

### Section order:
1. **Hero / Title Section** — full-viewport animated intro
2. **Chapter Overview** — what this chapter is about, why it matters, what you'll learn
3. **[TOPIC SECTION 1]** — first major topic with explanation, animated diagram, formula cards
4. **[TOPIC SECTION 2]** — second major topic
5. *(repeat for every topic in the chapter)*
6. **Interactive Lab / Simulator** — at least one interactive calculator or animated diagram the student can manipulate
7. **Worked Examples** — 2–3 expandable step-by-step solved problems
8. **Flashcard Deck** — 8–12 flip-cards covering key Q&A
9. **Chapter Quiz** — 8–10 MCQ questions with instant feedback
10. **Chapter Summary / Key Takeaways** — all formulas and laws at a glance
11. **Footer** — chapter name, subject, class

---

## PART 3 — VISUAL & INTERACTION DESIGN

### 3.1 Colour Palette — LIGHT THEME (mandatory for this project)

Use a **light, warm, student-friendly** palette. Not dark. Not neon-heavy. Think: clean notebook paper meets a well-designed science textbook — warm whites, soft creams, with one or two vivid accent colours per chapter.

Each chapter has its **own unique accent colour pair** (see Chapter Colour Map below). Use CSS custom properties throughout:

```css
:root {
  /* Light base */
  --bg:           #fdfaf5;        /* warm off-white, like good paper */
  --bg-card:      #ffffff;
  --bg-surface:   #f4f0e8;        /* slightly warm surface */
  --border:       rgba(0,0,0,0.08);
  --border-bold:  rgba(0,0,0,0.16);

  /* Text */
  --text:         #1a1612;        /* near-black, warm */
  --text-muted:   #6b6355;        /* warm mid-grey */
  --text-light:   #9e9383;

  /* Chapter accent colours — REPLACE with chapter-specific values */
  --accent:       [CHAPTER PRIMARY ACCENT];
  --accent-light: [CHAPTER ACCENT LIGHT];
  --accent-dim:   [CHAPTER ACCENT DIM — rgba at 0.12 opacity];
  --accent-glow:  [CHAPTER ACCENT GLOW — rgba at 0.25 opacity];

  --accent2:      [CHAPTER SECONDARY ACCENT];
  --accent2-dim:  [CHAPTER SECONDARY DIM];

  /* Always-available semantic */
  --green:        #16a34a;
  --green-soft:   #dcfce7;
  --red:          #dc2626;
  --red-soft:     #fee2e2;
  --yellow:       #ca8a04;
  --yellow-soft:  #fef9c3;

  --radius:       12px;
  --radius-lg:    20px;
  --radius-xl:    28px;
}
```

### Chapter Colour Map (use these exact values per chapter):

| # | Chapter | --accent | --accent2 |
|---|---------|----------|-----------|
| 1 | Chemical Reactions & Equations | `#e85d04` (fire orange) | `#7209b7` (reaction purple) |
| 2 | Acids, Bases & Salts | `#0077b6` (litmus blue) | `#d62828` (acid red) |
| 3 | Metals & Non-metals | `#b5838d` (copper rose) | `#2d6a4f` (patina green) |
| 4 | Carbon & Its Compounds | `#264653` (graphite teal) | `#e9c46a` (organic amber) |
| 5 | Life Processes | `#2d6a4f` (chlorophyll green) | `#e76f51` (respiration coral) |
| 6 | Control & Coordination | `#7b2d8b` (neuron purple) | `#0096c7` (signal blue) |
| 7 | How Do Organisms Reproduce? | `#c77dff` (cell violet) | `#48cae4` (division cyan) |
| 8 | Heredity | `#457b9d` (DNA blue) | `#e63946` (gene red) |
| 9 | Light – Reflection & Refraction | `#f4a261` (ray amber) | `#219ebc` (refraction blue) |
| 10 | Human Eye & Colourful World | `#9b5de5` (iris violet) | `#00b4d8` (sky cyan) |
| 11 | Electricity | `#ffbe0b` (current yellow) | `#3a86ff` (circuit blue) |
| 12 | Magnetic Effects | `#ef233c` (magnet red) | `#4361ee` (field blue) |
| 13 | Our Environment | `#52b788` (ecosystem green) | `#f4a261` (sun amber) |

### 3.2 Typography

```html
<link href="https://fonts.googleapis.com/css2?family=Nunito:ital,wght@0,400;0,600;0,700;0,800;0,900;1,400&family=Lora:ital,wght@0,400;0,600;0,700;1,400;1,600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
```

- **Display / headings:** `'Lora'` serif — warm, academic, trustworthy
- **Body text:** `'Nunito'` sans-serif — friendly, rounded, highly readable for students
- **Formulas / equations / code:** `'JetBrains Mono'` — clean, unambiguous
- **Base font size:** 16px body, 15px in cards
- **Line height:** 1.75 body, 1.5 compact

### 3.3 Layout

- Max content width: `860px` centered
- Full-bleed coloured sections for topic dividers
- Sticky top navigation bar with chapter section links
- Reading progress bar at top (3px, accent colour)
- Scroll-triggered reveal animations on every section (IntersectionObserver, 0.15 threshold)
- `scroll-behavior: smooth` globally

---

## PART 4 — REQUIRED INTERACTIVE COMPONENTS

Every page must include all of the following. Build each one fully functional in vanilla JS — no external libraries except Google Fonts.

### 4.1 Animated SVG Diagrams (minimum 2 per page)
- At least **2 SVG diagrams** that are either animated (CSS keyframes or JS-driven) or interactive (user can click/hover to reveal labels or change state)
- Each diagram must be **directly relevant** to a topic in this chapter
- Diagrams must have labelled parts, smooth animations, and respond to hover or click
- Examples: animated ray diagram for light, pulsing cell division animation, electron flow in a circuit, digestive system with clickable organs
- Do NOT use placeholder shapes — draw actual simplified scientific diagrams using SVG paths, circles, lines, and text labels
- Chapter-specific diagram requirements:

```
[DIAGRAM REQUIREMENTS FOR THIS CHAPTER]
Example for Ch.9:
- Animated ray diagram: concave mirror showing incident ray, normal, reflected ray 
  with the angle labels appearing on hover. Object position slider changes image position.
- Animated refraction diagram: light ray bending at an interface, with n1/n2 labels,
  angles animating smoothly when the user drags a slider for angle of incidence.
```

### 4.2 Interactive Calculator / Simulator
- At least **1 fully working calculator** specific to this chapter
- Uses real formulas from NCERT (verify before coding)
- Input fields with proper labels, units shown inline
- Output: numerical result + plain-English interpretation of what it means
- Styled with accent colour, animated button, monospace result display
- Shows step-by-step working, not just the answer

```
[CALCULATOR REQUIREMENTS FOR THIS CHAPTER]
Example for Ch.11 Electricity:
- Ohm's Law calculator: input V and R → output I, with interpretation
- Also: series/parallel resistance calculator for up to 3 resistors
```

### 4.3 Flashcard Deck
- **8–12 cards** per chapter, covering key definitions, formulas, and distinctions
- Card front: question or term
- Card back: answer, formula, or explanation
- Flip animation: smooth 3D CSS `rotateY` transform, 0.6s ease
- Navigation: Previous / Next buttons + card counter "Card 3 of 10"
- Shuffle button that randomises card order
- Cards must cover content spread across ALL topics of the chapter
- Card content sourced strictly from NCERT definitions and NCERT-aligned explanations

```
[FLASHCARD CONTENT FOR THIS CHAPTER — provide 10 Q&A pairs]
Example:
Q: What is the SI unit of electric current?
A: Ampere (A). Defined as 1 coulomb of charge flowing per second.

Q: State Ohm's Law.
A: V = IR. At constant temperature, potential difference across a conductor is directly proportional to the current through it.
```

### 4.4 Chapter Quiz
- **8–10 MCQ questions**, all based on NCERT content for this chapter
- 4 options each, exactly 1 correct answer
- On click: immediate visual feedback (green = correct, red = wrong)
- Correct answer highlighted even if wrong option clicked
- Explanation shown below each question after answering
- Final score displayed as a large gradient number after all questions answered
- Questions must span all topics of the chapter, not just one section
- Difficulty mix: 3 easy, 4 medium, 2–3 hard

```
[QUIZ QUESTIONS FOR THIS CHAPTER — provide 9 questions with answers and explanations]
Example:
Q: Which of the following has the highest electrical resistivity?
A) Silver  B) Copper  C) Nichrome  D) Aluminium
Answer: C
Explanation: Nichrome has resistivity ~100 × 10⁻⁶ Ω·m, far higher than silver (1.6 × 10⁻⁸) or copper (1.62 × 10⁻⁸). This is why it's used in heaters.
```

### 4.5 Section Mini-Quiz (in-line, 1 per major topic section)
- After each topic explanation, embed a **1–3 question mini-check**
- Not a full quiz — just a quick "Did you get it?" moment
- Style: simple pill-button options, instant colour feedback, no scoring
- Keeps students engaged section by section rather than only at the end

### 4.6 Fun Fact / Did You Know Cards
- **1 per topic section** minimum
- Glowing accent-coloured left border
- Pulsing icon (CSS animation)
- Content: real-world connection, historical context, or surprising application
- Must be factually correct and cross-verified

---

## PART 5 — ANIMATION SPECIFICATIONS

All animations must be CSS-only or vanilla JS. No GSAP, no anime.js, no heavy libraries.

### 5.1 Page Load
- Staggered hero text fade-up: eyebrow → title → subtitle → CTAs, each 0.2s delay apart
- Animated light rays or chapter-specific particle effect in hero background
- Hero uses a radial gradient mesh with chapter accent colours, subtle and not distracting

### 5.2 Scroll Animations
```css
.reveal {
  opacity: 0;
  transform: translateY(28px);
  transition: opacity 0.65s ease, transform 0.65s ease;
}
.reveal.visible {
  opacity: 1;
  transform: none;
}
```
Apply `.reveal` to every section, card, and diagram. Use IntersectionObserver with threshold 0.12.

### 5.3 SVG / Diagram Animations
- Use `@keyframes` for continuous animations (flowing electrons, pulsing cells, rotating molecules)
- Use JS event listeners for interactive state changes (click to label, drag to recalculate)
- Arrows on diagrams: animated `stroke-dashoffset` to draw themselves in on scroll-reveal
- Keep animation durations between 1–4 seconds, `ease-in-out` timing
- `animation-play-state: paused` by default; start playing when `.visible` class added

### 5.4 Hover States
- Formula cards: lift 4px, box-shadow increases, border becomes accent-coloured
- Buttons: scale(1.02) + glow shadow matching accent
- Nav links: underline slides in from left (::after pseudo-element, scaleX 0→1)
- Quiz options: border-left 3px accent colour appears on hover
- Flashcards: subtle scale(1.01) on hover before flip

### 5.5 Chapter-Specific Hero Animation
Each chapter hero should have a unique atmospheric background animation:

```
[HERO ANIMATION FOR THIS CHAPTER]
Examples by chapter:
- Ch.1 Chemical Reactions: Animated bubbles rising + colour-changing liquid in a beaker SVG
- Ch.2 Acids/Bases: Litmus paper slowly changing colour from red↔blue
- Ch.3 Metals: Metallic sheen sweep across a surface, crystalline lattice dots
- Ch.4 Carbon: Hexagonal benzene ring slowly rotating/assembling
- Ch.5 Life Processes: Slow leaf-vein pulse animation, green photosynthesis glow
- Ch.6 Control: Animated neuron firing — signal pulse travelling down axon
- Ch.7 Reproduction: Cell gently dividing in two, mitosis loop
- Ch.8 Heredity: DNA double helix slowly rotating (CSS 3D transform)
- Ch.9 Light: Light ray splitting through prism into VIBGYOR spectrum
- Ch.10 Human Eye: Pupil dilating and contracting slowly
- Ch.11 Electricity: Electrons (dots) flowing through a circuit loop
- Ch.12 Magnetism: Magnetic field lines animating around a bar magnet
- Ch.13 Environment: Animated food web arrows pulsing between organisms
```

---

## PART 6 — NAVIGATION

### 6.1 Sticky Nav Bar
```html
<nav> with position: sticky; top: 0; z-index: 100;
```
- Logo/title left: "[Chapter Number] · [Short Chapter Name]"
- Right: anchor links to each section of the page (auto-generated from section IDs)
- Active section highlighted as user scrolls (IntersectionObserver on sections)
- Collapses to hamburger on mobile (< 768px), slides down as a full-width dropdown

### 6.2 Reading Progress Bar
- 3–4px bar at very top of viewport, above nav
- Fills left-to-right with accent colour as user scrolls
- Smooth `width` transition with linear timing

### 6.3 Section Anchors
Every major section `<section>` tag must have a unique `id` matching a nav link:
```html
<section id="reflection"> ... </section>
<section id="refraction"> ... </section>
```

---

## PART 7 — ACCESSIBILITY & PERFORMANCE

- All images and SVGs must have `aria-label` or `<title>` elements
- Colour contrast: all text must pass WCAG AA (4.5:1 for body text)
- Interactive elements must be keyboard-navigable (tabindex, Enter key support for buttons)
- Font sizes: minimum 14px for any visible text
- No layout shift on load (reserve space for all dynamic elements)
- Lazy-load nothing — this is a single study session page, preload everything
- Total file size target: under 150KB (the whole .html file)
- No external dependencies except Google Fonts CDN

---

## PART 8 — FORMULA & EQUATION DISPLAY

- All formulas displayed in `JetBrains Mono` inside styled `.formula` blocks
- Formula blocks: accent-coloured text, semi-transparent accent background, rounded corners
- Variables explained in a grid below each formula
- For chemistry chapters: use proper notation (subscripts with `<sub>`, superscripts with `<sup>`, arrows with `→` or `⇌`)
- For physics chapters: use proper SI units inline after each quantity
- Never use LaTeX — use plain Unicode + HTML sub/sup tags only
- Formula cards must be hoverable (reveal description on hover or show worked example)

---

## PART 9 — SPECIFIC COMPONENT STYLING RULES

### Callout Boxes (3 variants)
```
.callout-concept   — accent left border, light accent background — for definitions
.callout-warning   — yellow left border, yellow-soft bg — for common mistakes  
.callout-remember  — green left border, green-soft bg — for exam tips
```

### Topic Section Headers
Each topic section must open with:
1. A small chapter-accent coloured eyebrow label (e.g. "Section 3 · Refraction")
2. A large Lora serif heading
3. A 1–2 sentence hook that connects the topic to the student's real life

### Cards
All cards must have:
- White background (#ffffff) with soft box-shadow (0 2px 12px rgba(0,0,0,0.08))
- 1px solid border (var(--border))
- Border-radius: var(--radius-lg)
- Hover: shadow increases to (0 8px 32px rgba(0,0,0,0.12)), translateY(-3px)
- Transition: all 0.25s ease

### Tables
- Header row: accent-dim background, accent-coloured text, bold
- Alternating row shading: every even row gets `--bg-surface` background
- Hover row: accent-dim highlight
- Responsive: horizontal scroll wrapper on mobile

---

## PART 10 — COMPLETE HTML STRUCTURE TEMPLATE

Generate the file in this exact order:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <!-- meta, title, Google Fonts link -->
  <!-- All CSS in one <style> block -->
</head>
<body>
  <!-- 1. Reading progress bar div -->
  <!-- 2. Sticky nav with section links + hamburger -->
  <!-- 3. Mobile menu dropdown -->
  <!-- 4. Hero section with animated background + title -->
  <!-- 5. Chapter overview section -->
  <!-- 6. Topic section 1 (with mini-quiz, fun fact, diagram) -->
  <!-- 7. Topic section 2 (with mini-quiz, fun fact, diagram or calculator) -->
  <!-- ... repeat for all topics ... -->
  <!-- N-3. Flashcard deck section -->
  <!-- N-2. Full chapter quiz section -->
  <!-- N-1. Chapter summary / formula sheet section -->
  <!-- N. Footer -->
  <!-- All JS in one <script> block at end of body -->
</body>
</html>
```

---

## PART 11 — OUTPUT REQUIREMENTS

1. **Output the complete file in full** — do not truncate, do not say "rest of the code follows the same pattern." Every section, every component, fully written.
2. **One single `.html` file** — all CSS in `<style>`, all JS in `<script>`, no external files except Google Fonts
3. **File must open and work perfectly offline** (minus fonts) — no fetch calls to external APIs
4. **Test mentally before outputting:** verify that all JS functions are defined before they're called, all IDs referenced in JS exist in HTML, all CSS variables are defined before use
5. The output file should be named: `ch[NUMBER]-[slug].html` (e.g. `ch09-light.html`, `ch01-chemical-reactions.html`)

---

## PART 12 — FINAL QUALITY CHECK (run through this before finishing)

Before outputting, verify:
- [ ] All NCERT content for this chapter is covered across sections
- [ ] Every formula has been double-checked (value, sign, variable names)
- [ ] All SVG diagrams are labelled and animated
- [ ] Calculator uses the correct NCERT formula for this chapter
- [ ] Flashcards cover all major topics, not just one
- [ ] Quiz questions span all topics with 3-easy / 4-medium / 2-hard mix
- [ ] All JS event listeners are attached after DOM content loads
- [ ] Mobile hamburger menu works
- [ ] Reading progress bar updates on scroll
- [ ] IntersectionObserver triggers `.reveal.visible` on all elements
- [ ] No console errors (all referenced IDs exist, no undefined functions)
- [ ] Colour contrast is readable on the light background
- [ ] Flashcard flip animation works with keyboard (Enter key)
- [ ] File size is under 150KB

---

# CHAPTER-SPECIFIC FILL-IN GUIDE

Use this section to fill in the `[BRACKETED PLACEHOLDERS]` for each chapter before sending the prompt.

---

## Chapter 1: Chemical Reactions and Equations

**[CHAPTER NUMBER]:** 1  
**[CHAPTER NAME]:** Chemical Reactions and Equations  
**[TOPIC LIST]:**
- Chemical reactions: signs of a chemical reaction (colour change, gas evolution, precipitate, temp change)
- Chemical equations: writing, balancing (by hit-and-trial)
- Types of chemical reactions: combination, decomposition, displacement, double displacement, oxidation-reduction
- Corrosion and rancidity

**[HERO ANIMATION]:** Animated beaker where two liquids slowly merge and change colour, with rising bubble particles (SVG + CSS keyframes)

**[DIAGRAM REQUIREMENTS]:**
1. Animated reaction type cards — clicking each card shows a simplified before/after particle diagram with arrows
2. Animated balancing equation builder — shows atoms on both sides with a visual counter showing balance achieved

**[CALCULATOR REQUIREMENTS]:** None (qualitative chapter) — replace with an interactive "Identify the Reaction Type" drag-and-drop activity where students match equations to reaction types, with instant feedback

**[FLASHCARD Q&A — 10 cards]:**
1. Q: What is a chemical reaction? A: A process in which new substances with new properties are formed from the original substances.
2. Q: What are the signs that a chemical reaction has occurred? A: Change in colour, evolution of gas, change in temperature, formation of precipitate, change in state.
3. Q: What is a balanced chemical equation? A: An equation where the number of atoms of each element is equal on both sides of the equation.
4. Q: Define combination reaction with example. A: Two or more substances combine to form a single product. e.g. 2Mg + O₂ → 2MgO
5. Q: Define decomposition reaction with example. A: A single reactant breaks into two or more products. e.g. 2H₂O₂ → 2H₂O + O₂
6. Q: What is a displacement reaction? A: A more reactive element displaces a less reactive element from its compound. e.g. Fe + CuSO₄ → FeSO₄ + Cu
7. Q: What is a double displacement reaction? A: Exchange of ions between two compounds to form two new compounds. e.g. Na₂SO₄ + BaCl₂ → BaSO₄↓ + 2NaCl
8. Q: Define oxidation. A: Gain of oxygen or loss of hydrogen in a reaction.
9. Q: What is corrosion? A: Slow eating up of metals due to attack by moisture, acid, oxygen etc. e.g. rusting of iron.
10. Q: What is rancidity? A: Oxidation of fats and oils in food causing unpleasant smell/taste.

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) Which symbol is used to show a gas evolved in a reaction? A) ↓ B) ↑ C) ⇌ D) △ | Answer: B
2. (Easy) Burning of magnesium ribbon is an example of: A) Decomposition B) Displacement C) Combination D) Double displacement | Answer: C
3. (Easy) The balanced form of H₂ + O₂ → H₂O is: A) H₂+O₂→H₂O B) 2H₂+O₂→2H₂O C) H₂+2O₂→2H₂O D) 2H₂+2O₂→H₂O | Answer: B
4. (Medium) Fe + CuSO₄ → FeSO₄ + Cu is an example of: A) Combination B) Decomposition C) Displacement D) Double displacement | Answer: C
5. (Medium) In the reaction 2FeSO₄ → Fe₂O₃ + SO₂ + SO₃, iron is: A) Oxidised B) Reduced C) Both D) Neither | Answer: A
6. (Medium) Which type of reaction requires heat or light to proceed? A) Combination B) Decomposition C) Displacement D) Redox | Answer: B
7. (Medium) AgNO₃ + NaCl → AgCl↓ + NaNO₃ is: A) Displacement B) Combination C) Double displacement D) Decomposition | Answer: C
8. (Hard) In a redox reaction, the reducing agent is: A) Oxidised and gains electrons B) Oxidised and loses electrons C) Reduced and loses electrons D) Reduced and gains electrons | Answer: B
9. (Hard) Which is NOT a sign of a chemical reaction? A) Change in colour B) Evolution of heat C) Change in shape of container D) Formation of precipitate | Answer: C

---

## Chapter 2: Acids, Bases and Salts

**[CHAPTER NUMBER]:** 2  
**[CHAPTER NAME]:** Acids, Bases and Salts  
**[TOPIC LIST]:**
- Properties of acids and bases (reaction with metals, metal carbonates, metal hydrogen carbonates, bases, indicators)
- Indicators: natural and artificial (litmus, turmeric, china rose)
- Strong vs weak acids and bases
- pH scale (0–14), pH of common substances
- Importance of pH in everyday life
- Salts: family of salts, pH of salts, preparation and uses
- Common chemicals: washing soda, baking soda, bleaching powder, plaster of paris

**[HERO ANIMATION]:** Litmus paper strip slowly changing from red → purple → blue as pH gradient sweeps across it

**[DIAGRAM REQUIREMENTS]:**
1. Interactive pH scale — a horizontal gradient bar (0=red → 7=green → 14=blue), students click on it to reveal example substances and their pH values with labels appearing
2. Animated acid-base reaction — H⁺ and OH⁻ ions shown as coloured circles approaching each other and combining into H₂O with a neutralisation glow effect

**[CALCULATOR REQUIREMENTS]:** Simple pH classifier — student enters a substance name from a predefined list (dropdown), output shows: pH value, acidic/basic/neutral, colour on pH scale, and real-world significance

**[FLASHCARD Q&A — 10 cards]:**
1. Q: What is an acid according to its reaction with water? A: Acids are substances that dissociate in water to produce H⁺ (hydrogen) ions.
2. Q: What gas is produced when a metal reacts with an acid? A: Hydrogen gas (H₂) is produced.
3. Q: What is neutralisation? A: Reaction between an acid and a base to form salt and water. Acid + Base → Salt + Water
4. Q: What does pH stand for, and what does it measure? A: "Potential of Hydrogen." It measures the concentration of H⁺ ions; scale 0–14.
5. Q: What is the pH of a neutral solution? A: 7. Above 7 is basic; below 7 is acidic.
6. Q: What is washing soda? A: Na₂CO₃·10H₂O (sodium carbonate decahydrate). Used in glass, soap, paper industries and as a water softener.
7. Q: What is baking soda? A: NaHCO₃ (sodium hydrogen carbonate). Used in cooking as a raising agent.
8. Q: How is bleaching powder formed? A: Ca(OH)₂ + Cl₂ → CaOCl₂ + H₂O. Chlorine is passed over slaked lime.
9. Q: What is Plaster of Paris? A: CaSO₄·½H₂O (calcium sulphate hemihydrate). Prepared by heating gypsum at 100°C.
10. Q: What is a salt? A: An ionic compound formed by the neutralisation of an acid with a base.

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) Litmus solution is: A) Natural indicator B) Artificial indicator C) Universal indicator D) None | Answer: A
2. (Easy) HCl is an example of: A) Weak acid B) Strong base C) Strong acid D) Weak base | Answer: C
3. (Easy) pH of gastric juice is approximately: A) 7 B) 1.2 C) 8 D) 5 | Answer: B
4. (Medium) Which of these produces OH⁻ ions in water? A) HNO₃ B) NaOH C) NaCl D) CO₂ | Answer: B
5. (Medium) Baking soda is used in fire extinguishers because: A) It is non-toxic B) It reacts with acid to produce CO₂ C) It absorbs heat D) It dissolves in water | Answer: B
6. (Medium) What happens when excess CO₂ is passed through lime water? A) Remains milky B) White precipitate persists C) Milky solution turns clear D) Blue colour appears | Answer: C
7. (Medium) The chemical name of gypsum is: A) CaSO₄·2H₂O B) CaSO₄·½H₂O C) CaCO₃ D) Ca(OH)₂ | Answer: A
8. (Hard) A student finds the pH of a solution to be 9. Which is the CORRECT statement? A) Acidic, H⁺>OH⁻ B) Neutral C) Basic, OH⁻>H⁺ D) Basic, H⁺>OH⁻ | Answer: C
9. (Hard) Which acid is present in ant sting? A) Acetic acid B) Citric acid C) Formic acid D) Oxalic acid | Answer: C

---

## Chapter 3: Metals and Non-metals

**[CHAPTER NUMBER]:** 3  
**[CHAPTER NAME]:** Metals and Non-metals  
**[TOPIC LIST]:**
- Physical properties of metals vs non-metals
- Chemical properties: reactions with oxygen, water, acids, other metal salts
- Reactivity series
- Ionic bond formation (electron transfer)
- Metallurgy: occurrence, extraction (concentration, reduction, refining)
- Corrosion and prevention

**[HERO ANIMATION]:** Metallic grid of atoms showing electron "sea" with slow-drifting electron particles

**[DIAGRAM REQUIREMENTS]:**
1. Interactive reactivity series — vertical ladder diagram; click any metal to see how it reacts with water, acid, and oxygen with animated reaction description
2. Animated ionic bond formation — Na and Cl atoms shown with electron shells; electron transfers with a glowing arc animation to form Na⁺ and Cl⁻, then lattice forms

**[CALCULATOR REQUIREMENTS]:** Reactivity comparator — select two metals from dropdowns, output states which is more reactive and what displacement reaction would occur between them

**[FLASHCARD Q&A — 10 cards]:**
1. Q: What is malleability? A: The property of metals to be beaten into thin sheets. e.g. gold, silver.
2. Q: Which non-metal conducts electricity? A: Graphite (a form of carbon).
3. Q: What is the most reactive metal? A: Potassium (K) — at the top of the reactivity series.
4. Q: What is the thermite reaction? A: 2Al + Fe₂O₃ → Al₂O₃ + 2Fe. Aluminium displaces iron due to higher reactivity.
5. Q: What is gangue? A: The impurities present along with the ore in the earth are called gangue.
6. Q: Define amalgam. A: An alloy of mercury with another metal.
7. Q: What is galvanisation? A: Coating iron/steel with a thin layer of zinc to prevent rusting.
8. Q: What gas is produced when metals react with water? A: Hydrogen gas (H₂).
9. Q: Why are ionic compounds solid at room temperature? A: They have strong electrostatic forces between oppositely charged ions arranged in a crystal lattice.
10. Q: What is an ore? A: A mineral from which a metal can be profitably extracted.

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) Which property allows metals to be drawn into wires? A) Malleability B) Ductility C) Conductivity D) Sonority | Answer: B
2. (Easy) Iron reacts with moist air to form: A) Iron oxide B) Iron carbonate C) Hydrated iron oxide (rust) D) Iron hydroxide | Answer: C
3. (Easy) Which metal is found in its free state in nature? A) Sodium B) Gold C) Aluminium D) Calcium | Answer: B
4. (Medium) Which of the following is NOT a property of metals? A) High melting point B) Electropositive C) Good conductor D) Non-lustrous | Answer: D
5. (Medium) In the reactivity series, which is MORE reactive? A) Cu > Fe B) Zn > Cu C) Au > Ag D) Pb > Zn | Answer: B
6. (Medium) Calcination is: A) Heating ore in presence of excess air B) Heating ore in absence or limited air C) Dissolving ore in acid D) Adding flux to ore | Answer: B
7. (Medium) Ionic compounds have high melting points because: A) They are covalent B) Strong ionic lattice forces C) They are metals D) They contain carbon | Answer: B
8. (Hard) Which process removes volatile impurities from metals? A) Liquation B) Distillation C) Electrolytic refining D) Zone refining | Answer: B
9. (Hard) Why is aluminium more reactive than iron, yet aluminium objects last longer? A) Aluminium is less reactive B) Aluminium oxide layer protects it C) Aluminium doesn't react with water D) Aluminium is non-metal | Answer: B

---

## Chapter 4: Carbon and Its Compounds

**[CHAPTER NUMBER]:** 4  
**[CHAPTER NAME]:** Carbon and Its Compounds  
**[TOPIC LIST]:**
- Bonding in carbon: covalent bond, tetravalency, catenation
- Allotropes of carbon
- Saturated and unsaturated hydrocarbons (alkanes, alkenes, alkynes)
- Functional groups
- Nomenclature of carbon compounds
- Chemical properties: combustion, oxidation, addition, substitution
- Important compounds: ethanol, ethanoic acid
- Soaps and detergents: cleansing action

**[HERO ANIMATION]:** Slowly rotating benzene ring (hexagon with alternating double bonds), built from animated SVG paths drawing themselves in

**[DIAGRAM REQUIREMENTS]:**
1. Interactive homologous series explorer — CnH(2n+2) for alkanes; student uses +/- buttons to change n from 1 to 6, diagram updates showing structural formula and name
2. Animated soap micelle — soap molecule with hydrophilic head and hydrophobic tail; clicking "Add grease" shows tails clustering around grease droplet, heads facing water

**[CALCULATOR REQUIREMENTS]:** Molecular formula calculator — input number of carbon atoms and compound type (alkane/alkene/alkyne/alcohol/acid), output: molecular formula, general formula applied, example name

**[FLASHCARD Q&A — 10 cards]:**
1. Q: What is catenation? A: The ability of carbon to bond with other carbon atoms to form long chains, branches or rings.
2. Q: What is the valency of carbon? A: 4 (tetravalent — forms 4 covalent bonds).
3. Q: General formula for alkanes? A: CₙH₂ₙ₊₂ (e.g. methane CH₄, ethane C₂H₆)
4. Q: What is a functional group? A: An atom or group of atoms that gives an organic compound its characteristic properties.
5. Q: What is ethanol used for? A: As a solvent, in alcoholic beverages, as fuel (biofuel), antiseptic.
6. Q: What is ethanoic acid commonly known as? A: Acetic acid — the acid in vinegar (~5-8% solution).
7. Q: What is saponification? A: Hydrolysis of fat/oil with NaOH (or KOH) to produce soap and glycerol.
8. Q: What is the cleansing action of soap? A: Soap molecules have hydrophilic head (attracted to water) and hydrophobic tail (attracted to grease); they form micelles around dirt.
9. Q: Why is soap ineffective in hard water? A: Hard water contains Ca²⁺ and Mg²⁺ ions which react with soap to form insoluble scum.
10. Q: What is the difference between soap and detergent? A: Soaps are sodium/potassium salts of fatty acids (natural). Detergents are synthetic, work in hard water.

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) How many bonds does carbon typically form? A) 2 B) 3 C) 4 D) 6 | Answer: C
2. (Easy) Ethene (C₂H₄) is: A) Alkane B) Alkyne C) Alkene D) Alcohol | Answer: C
3. (Easy) The functional group -OH is called: A) Aldehyde B) Hydroxyl C) Carboxyl D) Amino | Answer: B
4. (Medium) Denatured alcohol is: A) Pure ethanol B) Ethanol + methanol/pyridine to make it undrinkable C) Propanol D) Industrial CO₂ | Answer: B
5. (Medium) Hydrogenation is an example of: A) Substitution reaction B) Combustion C) Addition reaction D) Oxidation | Answer: C
6. (Medium) Which is the IUPAC name for CH₃COOH? A) Methanoic acid B) Ethanoic acid C) Propanoic acid D) Butanoic acid | Answer: B
7. (Medium) Diamond and graphite are: A) Isotopes of carbon B) Allotropes of carbon C) Isomers D) Compounds of carbon | Answer: B
8. (Hard) In substitution reaction of CH₄ with Cl₂ in sunlight, the first product is: A) C₂H₅Cl B) CHCl₃ C) CH₃Cl D) CCl₄ | Answer: C
9. (Hard) Why do detergents work in hard water but soaps don't? A) Detergents have no ionic groups B) Detergent anions don't form insoluble calcium/magnesium salts C) Detergents are non-polar D) Detergents contain benzene | Answer: B

---

## Chapter 5: Life Processes

**[CHAPTER NUMBER]:** 5  
**[CHAPTER NAME]:** Life Processes  
**[TOPIC LIST]:**
- What are life processes?
- Nutrition: autotrophic (photosynthesis — equation, conditions, leaf adaptations) and heterotrophic (types: holozoic, saprophytic, parasitic)
- Human digestive system (step-by-step: mouth to large intestine), enzymes
- Respiration: aerobic and anaerobic, equation for each; ATP
- Human respiratory system
- Transportation in humans: blood, heart (double circulation), blood vessels, lymph
- Transportation in plants: xylem, phloem, transpiration, osmosis
- Excretion in humans: kidneys, nephron (structure and function), dialysis
- Excretion in plants

**[HERO ANIMATION]:** Animated leaf with pulsing green veins slowly brightening, sunlight rays filtering in, CO₂ arrows entering and O₂ arrows exiting

**[DIAGRAM REQUIREMENTS]:**
1. Interactive human digestive system — clickable SVG body diagram; clicking each organ (mouth, oesophagus, stomach, small intestine, large intestine, liver) shows a callout with enzyme/role info
2. Animated nephron — tubular structure with animated fluid flow; labels appear showing filtration, reabsorption, secretion zones

**[CALCULATOR REQUIREMENTS]:** Photosynthesis / Respiration equation balancer — shows the balanced equations and lets student verify by checking atom counts on each side with a visual tick/cross

**[FLASHCARD Q&A — 10 cards]:**
1. Q: What is the equation for photosynthesis? A: 6CO₂ + 6H₂O → C₆H₁₂O₆ + 6O₂ (in presence of sunlight and chlorophyll)
2. Q: What is the role of HCl in the stomach? A: Creates acidic medium for pepsin to work; kills bacteria in food.
3. Q: What is the equation for aerobic respiration? A: C₆H₁₂O₆ + 6O₂ → 6CO₂ + 6H₂O + Energy (ATP)
4. Q: What is anaerobic respiration in yeast? A: C₆H₁₂O₆ → 2C₂H₅OH + 2CO₂ + Energy (fermentation)
5. Q: What is the role of platelets? A: They help in blood clotting (coagulation) to prevent excess blood loss.
6. Q: What is double circulation? A: Blood passes through the heart twice in one complete cycle — once for pulmonary, once for systemic circulation.
7. Q: What is the functional unit of kidney? A: Nephron — where filtration, reabsorption, and secretion of urine occurs.
8. Q: What is transpiration? A: Loss of water vapour through stomata of leaves; creates transpiration pull for water uptake.
9. Q: What is the role of phloem? A: Transports food (sucrose/amino acids) from leaves to all parts of the plant — bidirectional.
10. Q: What is osmoregulation? A: Regulation of water and ion balance in the body (performed by kidneys in humans).

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) Chlorophyll is found in: A) Mitochondria B) Chloroplasts C) Nucleus D) Vacuole | Answer: B
2. (Easy) The enzyme that digests starch in the mouth is: A) Pepsin B) Lipase C) Salivary amylase D) Trypsin | Answer: C
3. (Easy) Aerobic respiration produces: A) Alcohol B) Lactic acid C) CO₂ and H₂O D) Only CO₂ | Answer: C
4. (Medium) Bile is produced by the liver and stored in: A) Pancreas B) Small intestine C) Gall bladder D) Stomach | Answer: C
5. (Medium) What is the function of valves in the heart? A) Pump blood B) Prevent backflow of blood C) Produce RBCs D) Filter blood | Answer: B
6. (Medium) Glomerulus is part of: A) Lungs B) Heart C) Kidney/nephron D) Liver | Answer: C
7. (Medium) Xylem transports: A) Food from leaves B) Water and minerals from roots C) Oxygen D) Hormones | Answer: B
8. (Hard) In yeast, glucose → ethanol + CO₂ is: A) Aerobic respiration B) Photosynthesis C) Anaerobic fermentation D) Decomposition | Answer: C
9. (Hard) Which of the following is NOT reabsorbed by the tubules in nephron? A) Glucose B) Water C) Urea D) Ions | Answer: C

---

## Chapter 6: Control and Coordination

**[CHAPTER NUMBER]:** 6  
**[CHAPTER NAME]:** Control and Coordination  
**[TOPIC LIST]:**
- Nervous system in animals: neuron structure, nerve impulse
- Human nervous system: CNS (brain regions + functions, spinal cord) and PNS
- Reflex action and reflex arc
- Tropic movements in plants (phototropism, geotropism, hydrotropism, thigmotropism)
- Chemical coordination: hormones
- Human endocrine system: glands and their hormones
- Plant hormones: auxin, gibberellin, cytokinin, abscisic acid

**[HERO ANIMATION]:** Animated neuron with signal pulse (glowing dot) travelling along axon from dendrite to axon terminal, synapse glow effect

**[DIAGRAM REQUIREMENTS]:**
1. Interactive neuron diagram — labelled SVG with dendrite, cell body, axon, myelin sheath, axon terminal; clicking each part shows function tooltip; animated electrical signal travels along it on button click
2. Reflex arc animation — stimulus → receptor → sensory neuron → spinal cord → motor neuron → effector → response; each step lights up in sequence with a "Fire!" button

**[CALCULATOR REQUIREMENTS]:** None (qualitative chapter) — replace with interactive Hormone-Gland matching activity: drag glands to correct hormone descriptions with instant feedback

**[FLASHCARD Q&A — 10 cards]:**
1. Q: What is a neuron? A: The structural and functional unit of the nervous system; specialised for transmitting nerve impulses.
2. Q: What is a reflex action? A: A spontaneous, involuntary, rapid response to a stimulus that does not involve the brain directly.
3. Q: What does the cerebellum do? A: Controls balance, posture, and coordination of voluntary movements.
4. Q: What is the function of auxin? A: Promotes cell elongation; responsible for phototropism — causes bending of plants towards light.
5. Q: What hormone controls blood sugar? A: Insulin (lowers blood sugar) produced by pancreas; glucagon raises it.
6. Q: What is adrenaline and what does it do? A: "Fight or flight" hormone from adrenal glands; increases heart rate, breathing, blood flow to muscles.
7. Q: What is positive phototropism? A: Growth of a plant part towards light (e.g. shoots).
8. Q: What is the role of the medulla oblongata? A: Controls involuntary actions — breathing, heart rate, swallowing, blood pressure.
9. Q: What is abscisic acid (ABA)? A: Plant hormone that inhibits growth; promotes wilting (closes stomata during water stress) — also called "stress hormone."
10. Q: What is the difference between endocrine and exocrine glands? A: Endocrine glands are ductless, secrete hormones directly into blood. Exocrine glands have ducts and secrete externally (e.g. sweat glands).

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) The gap between two neurons is called: A) Axon B) Synapse C) Dendrite D) Myelin | Answer: B
2. (Easy) Which part of the brain controls thinking? A) Cerebellum B) Medulla C) Cerebrum D) Pons | Answer: C
3. (Easy) Geotropism means growth in response to: A) Light B) Water C) Touch D) Gravity | Answer: D
4. (Medium) Iodine deficiency causes: A) Diabetes B) Dwarfism C) Goitre D) Acromegaly | Answer: C
5. (Medium) The hormone responsible for secondary sexual characteristics in males: A) Oestrogen B) Progesterone C) Testosterone D) FSH | Answer: C
6. (Medium) A reflex arc involves: A) Only brain B) Brain and spinal cord C) Receptors, neurons, effectors (spinal cord-mediated) D) Only voluntary response | Answer: C
7. (Medium) Which plant hormone promotes fruit ripening? A) Auxin B) Gibberellin C) Ethylene D) Cytokinin | Answer: C
8. (Hard) During phototropism, why does a shoot bend toward light? A) More auxin on light side B) Less auxin on dark side C) Auxin moves to darker side causing more elongation there D) Light destroys cells on lit side | Answer: C
9. (Hard) Insulin and glucagon work antagonistically. If blood glucose rises: A) Insulin decreases, glucagon increases B) Both increase C) Insulin increases, glucagon decreases D) Neither changes | Answer: C

---

## Chapter 7: How Do Organisms Reproduce?

**[CHAPTER NUMBER]:** 7  
**[CHAPTER NAME]:** How Do Organisms Reproduce?  
**[TOPIC LIST]:**
- Why do organisms reproduce?
- Types of reproduction: asexual (fission, budding, fragmentation, regeneration, vegetative propagation, spore formation)
- Sexual reproduction in flowering plants: stamen, pistil, pollination, fertilisation, seed and fruit formation
- Reproduction in humans: male and female reproductive systems, menstrual cycle, fertilisation, pregnancy
- Contraception methods
- Reproductive health: STDs

**[HERO ANIMATION]:** Gentle cell-division loop — one circle slowly pinching and splitting into two identical circles, repeating

**[DIAGRAM REQUIREMENTS]:**
1. Interactive flower cross-section — labelled SVG showing petal, sepal, stamen (anther + filament), pistil (stigma, style, ovary, ovule); clicking each part shows label + function
2. Animated human fertilisation — egg and sperm cells; sperm cell moves across the screen and merges with egg to form zygote, then zygote divides into 2, 4, 8 cells showing early development

**[CALCULATOR REQUIREMENTS]:** None — replace with visual matching activity: match asexual reproduction type (fission, budding, etc.) to the organism (amoeba, hydra, planaria...) with drag-and-drop

**[FLASHCARD Q&A — 10 cards]:**
1. Q: What is binary fission? Give an example. A: Division of a single-celled organism into two equal halves. e.g. Amoeba, bacteria.
2. Q: What is budding? A: A small outgrowth (bud) forms on the parent organism and eventually detaches. e.g. Hydra, yeast.
3. Q: What is regeneration? A: Ability to regrow lost body parts. e.g. Planaria (flatworm) can regenerate a complete organism from any cut piece.
4. Q: Define pollination. A: Transfer of pollen grains from anther to stigma of a flower.
5. Q: What is double fertilisation? A: In flowering plants: one sperm fertilises the egg → zygote; another sperm fuses with polar nuclei → endosperm. Unique to angiosperms.
6. Q: What is the function of the placenta? A: Connects mother and foetus; supplies oxygen and nutrients to foetus and removes waste.
7. Q: What is the menstrual cycle? A: ~28-day cycle of uterine lining building up (in preparation for fertilisation) and shedding if fertilisation doesn't occur.
8. Q: What is vegetative propagation? Give examples. A: Asexual reproduction in plants using roots, stems, or leaves. e.g. potato (tubers), rose (cuttings), Bryophyllum (leaves).
9. Q: What is contraception? A: Methods to prevent unwanted pregnancy; includes barrier (condoms), chemical (pills), surgical (vasectomy/tubectomy).
10. Q: What are STDs? A: Sexually transmitted diseases passed through sexual contact. e.g. HIV/AIDS, gonorrhoea, syphilis.

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) Spore formation occurs in: A) Amoeba B) Rhizopus (bread mould) C) Hydra D) Planaria | Answer: B
2. (Easy) The male gametophyte in plants produces: A) Eggs B) Pollen grains (sperm) C) Seeds D) Fruit | Answer: B
3. (Easy) Fertilisation in humans occurs in: A) Uterus B) Ovary C) Fallopian tube D) Cervix | Answer: C
4. (Medium) In double fertilisation, endosperm nucleus is: A) Diploid B) Triploid C) Haploid D) Polyploid | Answer: B
5. (Medium) Which hormone triggers ovulation? A) Progesterone B) Oestrogen C) LH (Luteinising hormone) D) FSH | Answer: C
6. (Medium) Budding in Hydra is a form of: A) Sexual reproduction B) Asexual reproduction C) Regeneration D) Fragmentation | Answer: B
7. (Medium) The function of the testis is: A) Produce eggs B) Produce sperm and testosterone C) Produce progesterone D) Store eggs | Answer: B
8. (Hard) If a cut piece of Planaria can regenerate a whole organism, this is possible because: A) All its cells are stem cells B) It uses sexual reproduction C) Specialised cells called neoblasts (undifferentiated cells) can redifferentiate D) Planaria has no specialised cells | Answer: C
9. (Hard) Vegetative propagation is preferred in horticulture because: A) It produces genetically diverse offspring B) It produces genetically identical (cloned) offspring with desired traits C) It is cheaper D) It only works in soil | Answer: B

---

## Chapter 8: Heredity

**[CHAPTER NUMBER]:** 8  
**[CHAPTER NAME]:** Heredity  
**[TOPIC LIST]:**
- Heredity and variation
- Mendel's experiments: monohybrid and dihybrid cross
- Laws: Law of segregation, Law of independent assortment
- Dominant and recessive traits
- Sex determination in humans (XX/XY)
- Evolution: accumulation of variation, speciation
- Acquired vs inherited traits
- Tracing evolutionary relationships (homologous organs, analogous organs, fossils)
- Human evolution

**[HERO ANIMATION]:** Animated DNA double helix slowly unzipping and re-zipping (CSS 3D rotateY on connected SVG nodes)

**[DIAGRAM REQUIREMENTS]:**
1. Interactive Punnett square — student selects parent genotypes from dropdown (e.g. Tt × Tt), the 2×2 Punnett square fills in with allele combinations, and the phenotype ratio is shown with a pie chart
2. Animated monohybrid cross (tall × short plants) — parent plants shown, gametes fall into Punnett square, F1 and F2 results shown with ratio labels

**[CALCULATOR REQUIREMENTS]:** Punnett Square calculator — input parent genotypes (e.g. "Tt" × "tt"), outputs: all offspring genotypes, genotype ratio, phenotype ratio, probability of each type

**[FLASHCARD Q&A — 10 cards]:**
1. Q: What is heredity? A: Transmission of traits from parents to offspring through genes.
2. Q: What is a dominant trait? A: A trait that expresses itself even when present in a single copy (one allele). Represented by capital letter.
3. Q: State the Law of Segregation. A: Each individual has two alleles for each trait; they segregate during gamete formation so each gamete carries only one allele.
4. Q: What is the F2 phenotype ratio in a monohybrid cross (Tt × Tt)? A: 3:1 (Tall : Short).
5. Q: How is sex determined in humans? A: Males are XY; females are XX. The father determines the child's sex — X from father → girl, Y from father → boy.
6. Q: What is variation? A: Differences in characteristics among individuals of the same species.
7. Q: What are homologous organs? A: Organs with similar structure (common origin/ancestry) but different functions. e.g. human arm, bat wing, whale flipper.
8. Q: What are analogous organs? A: Organs with different structures but similar functions. e.g. wings of bird and insect.
9. Q: What is speciation? A: Formation of new species from existing ones due to isolation and accumulation of variation over generations.
10. Q: What is the difference between acquired and inherited traits? A: Acquired traits develop during an organism's lifetime due to environment; they are NOT passed to offspring. Inherited traits come from genes and are passed on.

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) Who is the father of genetics? A) Darwin B) Mendel C) Watson D) Lamarck | Answer: B
2. (Easy) In Tt, T is: A) Recessive allele B) Dominant allele C) Gene D) Chromosome | Answer: B
3. (Easy) In humans, sex is determined by: A) Mother only B) Father only C) Both parents equally D) Environment | Answer: B
4. (Medium) A cross between Tt × tt gives offspring ratio: A) 3:1 B) 1:1 C) All Tt D) All tt | Answer: B
5. (Medium) Fossils are evidence for evolution because: A) They show living organisms B) They show extinct organisms and transitional forms C) They tell us the future D) They are living organisms | Answer: B
6. (Medium) Homologous organs suggest: A) Convergent evolution B) Common ancestry (divergent evolution) C) Similar environment D) Similar function | Answer: B
7. (Medium) If a father has blood group AB and mother is OO, children can have: A) Only O B) A or B only C) AB only D) A, B, or AB | Answer: B
8. (Hard) In dihybrid cross (RRYY × rryy), the F2 phenotype ratio is: A) 9:3:3:1 B) 1:1:1:1 C) 3:1 D) 1:2:1 | Answer: A
9. (Hard) Genetic drift is: A) Mutation by chemicals B) Random change in allele frequency in small isolated populations C) Gene flow between populations D) Directed natural selection | Answer: B

---

## Chapter 9: Light – Reflection and Refraction
*(Already built — use the existing page as reference for quality standard)*

**[CHAPTER NUMBER]:** 9  
**[CHAPTER NAME]:** Light – Reflection and Refraction  
**Refer to the existing `index.html` for full implementation.**  
All topics, formulas, diagrams, quiz, and flashcards are already present.  
If regenerating from scratch with this prompt, follow the same structure and use the same NCERT formulas.

---

## Chapter 10: The Human Eye and the Colourful World
*(Already built — use the existing page as reference for quality standard)*

**[CHAPTER NUMBER]:** 10  
**[CHAPTER NAME]:** The Human Eye and the Colourful World  
**Refer to the existing `index.html` for full implementation.**

---

## Chapter 11: Electricity

**[CHAPTER NUMBER]:** 11  
**[CHAPTER NAME]:** Electricity  
**[TOPIC LIST]:**
- Electric current and circuit; charge (Q = It)
- Potential difference (V = W/Q)
- Ohm's Law (V = IR); resistance, ohmic and non-ohmic conductors
- Factors affecting resistance: R = ρL/A
- Resistors in series and parallel
- Heating effect: Joule's Law (H = I²Rt)
- Electric power (P = VI = I²R = V²/R)
- Commercial unit of energy (kWh); cost calculations

**[HERO ANIMATION]:** Animated circuit loop — electrons (small glowing dots) flowing around a simple circuit with battery, bulb (glowing) and resistor; bulb brightness changes when "resistance" slider is adjusted

**[DIAGRAM REQUIREMENTS]:**
1. Interactive series vs parallel circuit — toggle switch to switch between series/parallel; shows current path, calculates equivalent resistance, shows relative brightness of bulbs
2. Animated Ohm's Law graph — V-I graph that draws itself; user adjusts resistance slider and the slope changes accordingly, showing steeper slope = more resistance

**[CALCULATOR REQUIREMENTS]:**
- Primary: Ohm's Law calculator (input any two of V, I, R → output third)
- Secondary: Series/Parallel resistance calculator (input up to 3 resistor values, select series or parallel → output equivalent resistance)
- Bonus: Power and electricity bill calculator (input watts, hours/day, days, rate per kWh → total cost)

**[FLASHCARD Q&A — 10 cards]:**
1. Q: State Ohm's Law. A: V = IR. At constant temperature, potential difference across a conductor is directly proportional to current through it.
2. Q: What is the SI unit of resistance? A: Ohm (Ω). 1 Ω = resistance when 1V produces 1A current.
3. Q: Formula for resistors in series? A: Rs = R₁ + R₂ + R₃ (total resistance is sum of individual resistances).
4. Q: Formula for resistors in parallel? A: 1/Rp = 1/R₁ + 1/R₂ + 1/R₃.
5. Q: What is electric power? A: Rate of energy consumption. P = VI = I²R = V²/R. Unit: Watt (W).
6. Q: What is 1 kWh? A: 1 kilowatt-hour = energy consumed by 1kW device in 1 hour = 3.6 × 10⁶ J. Commercial unit of electricity.
7. Q: What is resistivity (ρ)? A: Intrinsic property of a material: R = ρL/A. Unit: Ω·m.
8. Q: State Joule's Law of heating. A: H = I²Rt. Heat produced is proportional to square of current, resistance, and time.
9. Q: Why is household wiring done in parallel? A: Each appliance gets full voltage (220V); can be switched independently; total resistance lower.
10. Q: What is an electric fuse? A: Safety device in series; wire with low melting point melts when current exceeds safe limit, breaking the circuit.

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) Ohm's Law gives the relationship between: A) Power and energy B) Voltage, current and resistance C) Charge and time D) Work and force | Answer: B
2. (Easy) SI unit of electric charge is: A) Ampere B) Volt C) Coulomb D) Ohm | Answer: C
3. (Easy) 1 kWh = ? A) 3.6 × 10³ J B) 3.6 × 10⁶ J C) 360 J D) 3600 kJ | Answer: B
4. (Medium) Three 6Ω resistors in parallel give equivalent resistance: A) 18Ω B) 6Ω C) 2Ω D) 3Ω | Answer: C
5. (Medium) Resistivity of a material depends on: A) Length B) Area C) Temperature and material nature D) Shape | Answer: C
6. (Medium) An iron of 1000W runs for 2 hours. Energy consumed: A) 1 kWh B) 2 kWh C) 0.5 kWh D) 4 kWh | Answer: B
7. (Medium) A wire is stretched to double its length. Resistance becomes: A) Half B) Same C) Double D) 4 times | Answer: D
8. (Hard) Two bulbs (100W, 220V) and (60W, 220V) in series across 220V. Which is brighter? A) 100W bulb B) 60W bulb C) Both equally D) Neither lights up | Answer: B (60W bulb has higher resistance, more voltage drop in series)
9. (Hard) Nichrome is used in heating elements because: A) Low resistance B) High melting point and high resistivity C) Good conductor D) Low resistivity | Answer: B

---

## Chapter 12: Magnetic Effects of Electric Current

**[CHAPTER NUMBER]:** 12  
**[CHAPTER NAME]:** Magnetic Effects of Electric Current  
**[TOPIC LIST]:**
- Magnetic field and field lines (properties)
- Magnetic field due to current in: straight conductor, circular loop, solenoid
- Right-hand thumb rule
- Force on current-carrying conductor in magnetic field
- Fleming's left-hand rule
- Electric motor: principle, construction, working
- Electromagnetic induction; Faraday's experiment
- Fleming's right-hand rule
- Electric generator
- Domestic electric circuits: live, neutral, earth wires; earthing; fuse; overloading; short circuit

**[HERO ANIMATION]:** Animated magnetic field lines flowing around a bar magnet — curved lines emerging from north pole and curving back to south pole, animated with `stroke-dashoffset`

**[DIAGRAM REQUIREMENTS]:**
1. Interactive magnetic field visualiser — user can select "straight wire", "circular loop", or "solenoid"; the correct field line pattern animates and labels appear; arrow direction reverses if "reverse current" button clicked
2. Animated electric motor — rotating coil between magnets; commutator and brushes labelled; play/pause button; rotation speed changes with "current" slider

**[CALCULATOR REQUIREMENTS]:** None (conceptual chapter) — replace with interactive "Apply the Rule" activity: scenario is shown (e.g. current direction + field direction), student uses click to indicate force direction (left/right/up/down/in/out), with instant right-hand/left-hand rule explanation

**[FLASHCARD Q&A — 10 cards]:**
1. Q: State the Right-Hand Thumb Rule. A: If a current-carrying conductor is held in the right hand with thumb pointing in current direction, the curled fingers show the direction of the magnetic field.
2. Q: State Fleming's Left-Hand Rule. A: Stretch thumb, forefinger, middle finger mutually perpendicular: forefinger = field direction, middle = current direction, thumb = force direction.
3. Q: What is an electromagnet? A: A temporary magnet made by passing current through a coil wound around a soft iron core.
4. Q: What is electromagnetic induction? A: Generation of an induced EMF/current in a conductor when it is placed in a changing magnetic field.
5. Q: State Fleming's Right-Hand Rule. A: Forefinger = field, thumb = motion of conductor, middle finger = direction of induced current.
6. Q: What is the purpose of a split-ring commutator in a DC motor? A: It reverses the current direction in the coil every half rotation, maintaining continuous rotation in one direction.
7. Q: What is the function of the earth wire? A: Safety wire connected to earth; carries leakage current to ground, preventing electric shock.
8. Q: What causes short circuit? A: Direct contact between live and neutral wire (due to damaged insulation), causing very high current flow.
9. Q: What is overloading? A: Connecting too many high-power appliances to a single circuit, exceeding safe current limit.
10. Q: AC vs DC — what is the main difference? A: AC (Alternating Current) periodically reverses direction; DC (Direct Current) flows in one direction only. India's domestic supply: AC, 220V, 50Hz.

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) Magnetic field lines emerge from: A) South pole B) North pole C) Both poles equally D) Middle of magnet | Answer: B
2. (Easy) Oersted discovered that: A) Moving charges create magnetic field B) Magnets deflect compass C) Current in a wire deflects a nearby compass D) All of these | Answer: C
3. (Easy) Colour of live wire in India: A) Green B) Black C) Red D) Blue | Answer: C
4. (Medium) In Fleming's Left-Hand Rule, the thumb represents: A) Field direction B) Current direction C) Force on conductor D) Induced EMF | Answer: C
5. (Medium) What happens to magnetic field strength inside a solenoid if number of turns is doubled? A) Halved B) Unchanged C) Doubled D) Quadrupled | Answer: C
6. (Medium) A generator works on the principle of: A) Magnetic force on current B) Electromagnetic induction C) Heating effect D) Electrolysis | Answer: B
7. (Medium) The fuse wire must have: A) High melting point, high resistance B) Low melting point, high resistance C) High melting point, low resistance D) Low melting point, low resistance | Answer: B
8. (Hard) An AC generator produces alternating current because: A) The coil rotates continuously, changing the direction of induced EMF B) The magnets alternate polarity C) The commutator reverses current D) Brushes reverse the current | Answer: A
9. (Hard) Why is a DC motor's commutator split into two halves? A) Reduce resistance B) Increase magnetic field C) Reverse current in coil every half turn to maintain rotation direction D) Cool the coil | Answer: C

---

## Chapter 13: Our Environment

**[CHAPTER NUMBER]:** 13  
**[CHAPTER NAME]:** Our Environment  
**[TOPIC LIST]:**
- Ecosystem: components (biotic, abiotic)
- Food chains and food webs
- Trophic levels; energy flow (10% law); producers, consumers, decomposers
- Ozone layer: formation, importance, depletion (CFCs)
- Waste management: biodegradable vs non-biodegradable
- Environmental problems: pollution, global warming, greenhouse effect

**[HERO ANIMATION]:** Animated food web — nodes (sun, grass, rabbit, fox) connected by arrows; energy pulses flow along arrows continuously; clicking a node highlights its connections

**[DIAGRAM REQUIREMENTS]:**
1. Interactive food chain / web builder — pre-built animated food web with 6–8 organisms; clicking an organism shows its trophic level, what it eats, and what eats it; an "Remove organism" button shows cascade effect
2. Energy pyramid animation — 4-tier pyramid (producers → herbivores → carnivores → top carnivores); energy bar fills each level; student sees the 10% law visually (100% → 10% → 1% → 0.1%)

**[CALCULATOR REQUIREMENTS]:** Energy transfer calculator — input energy at producer level (e.g. 10,000 J), select number of trophic levels (2–5), output: energy available at each level using 10% law, shown as a bar chart

**[FLASHCARD Q&A — 10 cards]:**
1. Q: What is an ecosystem? A: A self-sustaining unit of biotic (living) and abiotic (non-living) components interacting with each other.
2. Q: What is the 10% law of energy transfer? A: Only 10% of energy from one trophic level is passed to the next; 90% is lost as heat, respiration etc.
3. Q: What are decomposers? Give examples. A: Organisms that break down dead organic matter. e.g. bacteria, fungi. They recycle nutrients.
4. Q: What is a food web? A: A network of interconnected food chains in an ecosystem.
5. Q: Why are food chains usually limited to 3–4 levels? A: Because of the 10% law — so little energy remains at higher levels that it cannot support more consumers.
6. Q: What causes ozone layer depletion? A: CFCs (chlorofluorocarbons) — released from ACs, refrigerators, aerosols — react with and break down ozone (O₃).
7. Q: What is the greenhouse effect? A: Trapping of solar heat by atmospheric gases (CO₂, CH₄, water vapour) — essential in moderate amounts but increased by pollution → global warming.
8. Q: What is a biodegradable substance? Give example. A: Can be broken down by microorganisms. e.g. food waste, paper, cotton.
9. Q: What is a non-biodegradable substance? A: Cannot be broken down naturally. e.g. plastics, DDT, pesticides — accumulate and cause pollution.
10. Q: What is biomagnification? A: Progressive increase in concentration of non-biodegradable substances as they pass up the food chain. e.g. DDT concentration highest in top predators.

**[QUIZ QUESTIONS — 9 questions]:**
1. (Easy) Producers in an ecosystem are: A) Animals B) Decomposers C) Green plants D) Parasites | Answer: C
2. (Easy) Which gas is responsible for ozone depletion? A) CO₂ B) SO₂ C) CFCs D) NO₂ | Answer: C
3. (Easy) Plastic is: A) Biodegradable B) Non-biodegradable C) Easily decomposed D) Organic | Answer: B
4. (Medium) In a food chain: Grass → Grasshopper → Frog → Snake. If 10,000 J reaches grasshopper, snake gets: A) 100 J B) 10 J C) 1000 J D) 1 J | Answer: B (10% × 10% = 1% of 10,000 = 100J to frog; 10% of that = 10J to snake)
5. (Medium) Ozone hole is mainly observed over: A) Equator B) Arctic C) Antarctica D) Himalayas | Answer: C
6. (Medium) The chemical formula for ozone is: A) O₂ B) O₃ C) O₄ D) CO₂ | Answer: B
7. (Medium) Biomagnification is highest in: A) Producers B) Primary consumers C) Secondary consumers D) Top carnivores | Answer: D
8. (Hard) Why does removing an organism from the middle of a food web cause more disruption than removing one from the end? A) Middle organisms eat more B) They connect multiple food chains, affecting both below and above C) They are larger D) They are producers | Answer: B
9. (Hard) An increase in CO₂ contributes to global warming. Which human activity contributes MOST? A) Agriculture B) Burning fossil fuels C) Deforestation alone D) Transportation alone | Answer: B

---

## HOW TO USE THIS PROMPT FILE

### Quick Start
1. Open this `.md` file
2. Scroll to the chapter you want to generate
3. Copy the entire **"THE PROMPT"** section (Part 1 through Part 12)
4. Fill in all `[BRACKETED PLACEHOLDERS]` with the chapter-specific content from the bottom of this file
5. Paste into Claude and send
6. Claude will generate the complete single-file HTML
7. Save as `ch[N]-[name].html` and open in browser

### Tips for Best Results
- **Send one chapter at a time** — each page is large; don't ask for multiple chapters at once
- **For Chapters 1–8 and 11–13**, copy the topic list, hero animation, diagram requirements, calculator requirements, flashcard Q&A, and quiz questions from Part 12 into the prompt before sending
- **For Chapters 9–10**, the reference implementation already exists — use those pages as your quality benchmark
- If Claude truncates the output, reply "Continue from where you left off" and it will complete the file
- After generation, open the HTML file in Chrome or Firefox and test: flip cards, run calculators, take the quiz, check all animations play

### GitHub Pages Deployment (same as before)
1. Create a public GitHub repo named `class10-science`
2. Upload each chapter's HTML file
3. Settings → Pages → Deploy from main branch
4. Each chapter will be live at `https://USERNAME.github.io/class10-science/ch09-light.html`

---

*Prompt version: 1.0 | For NCERT Class 10 Science, 13 chapters | All content aligned to NCERT syllabus*
