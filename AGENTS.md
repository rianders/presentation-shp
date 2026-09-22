# AGENTS.md

Guidance for coding agents working in this repository.

## Project

Two decks for the same day: the morning talk (`talk-outline.md`, `slides.html`) and the afternoon student panel (`panel-outline.md`, `panel-slides.html`).

A 45-minute lessons-learned talk for SHP and IT faculty at Rutgers. Title: **From Classroom to Campus Service: Lessons from faculty who teach and research AI**.

- **Speaker:** Rick Anderson, Director of Emerging Technology, Rutgers UOES
- **Program slot:** After Tom Vossler (AI IT Working Group), before Andy Paige and Eric Marshall (Cloud Services and OARC), who announce Portkey and the new AWS relationship.
- **Purpose:** Faculty who teach the tech and/or research with and about it don't have AI-familiar support. Different infrastructure fits teaching, research, or both, but integrating with Rutgers's central service tech is complicated and isn't documented for this kind of use. These projects aren't stalled; they do what's necessary. Can Rutgers identify these projects and support homegrown edtech?
- **Slide order:** Title → The fly on the wall → The pain point → The pathway (diagram) → Stages 1–4 → The questions for Rutgers → Closing thoughts → Up next. Eleven slides.
- **The pathway:** Stage 1 Teaching the tech → Stage 2 Research with and about the tech (overlapping; Chameleon Cloud fits both) → Stage 3 Student and departmental use → Stage 4 University services. Don't use "and back."
- **Skeleton rule:** Rick tells the stories live. Each slide gets a headline and at most one line. Story details stay out of the slides and the outline unless Rick asks. Background research goes in `research/`.

## Layout

```
talk-outline.md      Source of truth for content, timing, stories, touch points
AGENTS.md            This file
journey.svg          Four-stage pathway diagram (1600x900, slide-ready)
panel-outline.md     Source of truth for the afternoon panel with Jey and Rey
panel-prep.md        Journey questions to send the panelists before the panel
panel-slides.html    Panel deck, derived from panel-outline.md (same design and keys)
slides.html          HTML slide deck, derived from talk-outline.md. Keys: arrows/space move,
                     F fullscreen, N notes overlay, P presenter window, T resets the timer.
                     Two-window sync needs a served origin: python3 -m http.server 8000
research/            Background notes (chameleon.md, yaco-paper.md); not slide content
```

Derive slides and speaker notes from `talk-outline.md` and keep that file authoritative.

## Formats

- Markdown for all text. SVG for visuals. CSV or JSON for any data.
- No Microsoft formats (.docx, .pptx, .xlsx) unless Rick asks for one.
- Slides, if built, should be HTML or Markdown-based (for example, reveal.js or Marp), not PowerPoint.

## Accessibility (required)

- Every SVG has `role="img"`, a `<title>`, and a `<desc>` that states the full content in prose.
- Every image in Markdown has meaningful alt text.
- Text contrast of at least 4.5:1 against its background.
- Never use color alone to carry meaning. Pair color with an icon, shape, or text label (see the `!` gap markers in `journey.svg`).
- Keep text as real `<text>` in SVG, not outlined paths, so it stays readable by assistive tech and editable.

## Visual design tokens

| Token | Hex | Use |
|---|---|---|
| Ink | `#1C2B39` | Headings, primary text |
| Slate | `#4E5D6C` | Secondary text, labels |
| Scarlet | `#CC0033` | Responsibility band endpoint |
| Deep scarlet | `#A8002A` | Gap markers, return loop, warnings |
| Step 1 to 4 | `#EEF3F6`, `#E1EAF0`, `#D3E1E9`, `#C5D7E2` | Stage fills, darkening along the pathway |
| Background | `#FFFFFF` | Canvas |

- **Type:** Source Sans 3 with a system sans fallback stack. Sentence case throughout; no all-caps labels.
- **Layout idea:** The pathway diagram is the one memorable element. Keep everything around it quiet.
- **Canvas:** 1600x900 (16:9) for anything meant for slides.

## Content rules

- **Do not invent project details.** Bracketed placeholders like `[Fill in: ...]` stay as placeholders until Rick supplies the content. List them under Open Items in `talk-outline.md`.
- Use names exactly as spelled here: Jim Samuel, Carmela Scala, Sonia Yaco, Bala Desinghu, Claire Warwick, Dr. Siobhan Corbett, Rey Riordan, Rebecca Brody, Scott Parrot, Rahul Mittal, Jey Labadorf, Laura Ramírez, Barbara Tufuto, Tom Vossler, Andy Paige, Eric Marshall.
- Platform names: Ollama, Amarel (OARC's cluster), Chameleon Cloud, Google Colab, Hugging Face, OpenRouter, Portkey, Amazon Bedrock, AgentCore, Shibboleth.
- Portkey, Shibboleth, and RU Cloud (AWS) are grouped as centrally supported tools, hosted or managed by OIT and Andy, that take technical expertise to engage with. They belong in Stage 4.
- Do not describe features of Portkey or the AWS relationship in detail. Those belong to Andy and Eric's talk.
- Keep the tone conversational: plain verbs, short sentences, questions for the room.

## Story map

| Slide | Story |
|---|---|
| 3. The pain point | Laura Ramírez: security document for research that runs entirely on a Mac laptop with local-only AI (Ollama) and anonymized PHI data. The live example. |
| 5. Stage 1, Teaching the tech | Jim Samuel: his students get a client and use the latest AI tech. Emotional accuracy in LLM translation, then guardrails for a postpartum chatbot. |
| 6. Stage 2, Research | Sonia Yaco, "What can AI do with special collections?" (The American Archivist, 2025; with Desinghu, then at OARC, Warwick, and Rick) and Chameleon Cloud, automated with AI agents to ease IT management. Lexus began here too, which bridges to Stage 3. |
| 7. Stage 3, Student and departmental use | Lexus: it got the Dean's grant and student support. Rahul Mittal and Jey Labadorf, with Barbara Tufuto, Scott Parrot, and others. |
| 10. Closing thoughts | Students are building this. With no dedicated resource, involving students is a practical decision, and they should be learning from it. Can we create more support for them? Points ahead to the panel with Jey and Rey later that day. |
| 8. Stage 4, University services | VHS (Brody, via Parrot): a chatbot/GPT project becoming a standalone service project for students. |

| 4. The pathway | OSCE Simulation (Corbett and Riordan): research that became an educational tool, so movement isn't one way. |

Unplaced: Carmela Scala, who appears on slide 2 with Jim Samuel.

## Checks before finishing a change

- Render any SVG you touch and look at it (for example, a headless browser screenshot) to confirm nothing overlaps or clips.
- Confirm stage names, tools, and gaps in `journey.svg` still match `talk-outline.md`.
- Update the SVG `<desc>` whenever the visible content changes.
