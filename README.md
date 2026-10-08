# TrackMate

**A conversational music production assistant: part DAW, part theory coach.**

TrackMate walks beginners through making music step by step, and gives experienced producers a natural-language way to mix and compose. Its AI coach explains, suggests, and demonstrates, but **it never writes the music for you.**

> **Status: concept finalized, prototyping 2026–27.** Senior capstone for my self-designed major in Computational Media & Creative Technology at Whitman College.

---

## The problem

GarageBand is simple but doesn't teach you anything. Ableton is powerful, but its learning curve pushes most beginners away before they finish a song. Nothing in between sits with you, explains what sounds good and why, and coaches you through the creative process in real time.

## Core features

- **🎛 Conversational mixing.** Ask for an effect in plain language. The coach plays three variations, applies the one you pick, then fine-tunes based on your feedback.
- **🎵 Chord intelligence.** Play Em and C, and the coach suggests what comes next, explains the theory behind it, and offers a more adventurous option (like a diminished chord) to try.
- **🎙 Spacebar recording.** Tap space to record over a looped section, and double-tap to delete and restart. You stay in flow without touching the interface.
- **🔁 Loop & Write mode.** Hold a section on loop while you write lyrics. The track keeps playing, and you keep writing.
- **📚 Theory coach layer.** Explains why a chord works, what tension a note adds, and how different genres handle the same progression, without lecturing unless you ask.
- **🎚 Step sequencer.** A grid beat builder (drums, bass, pad, melody) where note input is limited to the current scale, so every note sounds intentional.

## How the interaction works

```
YOU  add a little reverb on this chorus
AI   Playing three options: Room, Plate, and Hall. Which feels right?
YOU  plate, but pull it back a bit
AI   Done. Plate reverb at 35% wet. Let me know if you want it drier.

YOU  I'm playing Em and C, what sounds good next?
AI   G and D are the natural resolution. For tension, try B° before
     resolving back to Em. Want to hear both?
```

## Architecture

| Layer | Tech | Role |
|---|---|---|
| Audio engine | Tone.js / Web Audio API | Synthesis, sequencing, effects, real-time playback in the browser |
| AI coach | Claude API | Music-theory reasoning and natural-language coaching |
| Context layer | Structured payloads | Every user action sends the current key, chords, BPM, genre, and skill level to the coach |
| Frontend | React | Sequencer grid, chat panel, instrument palette |
| Backend | Flask | Claude integration, project persistence, theory utilities |
| Recording | MediaRecorder API | Browser mic capture over looped playback |

## Roadmap

- [ ] **Phase 1: Foundation.** Architecture, Tone.js audio prototype, and step sequencer with basic instruments
- [ ] **Phase 2: Core UI.** Key/scale selector, instrument palette, and spacebar record flow
- [ ] **Phase 3: AI coach.** Claude integration, conversational mixing (A/B/C), chord intelligence, and theory coaching
- [ ] **Phase 4: User testing.** Sessions with beginner musicians, focused on coaching quality and points of friction in the interface
- [ ] **Phase 5: Polish.** Refine the coach's instructions based on the test findings, then the capstone write-up

## Research angle

Alongside the build, I'll document how repeatedly refining the coach's instructions (its system prompt) changes how good and how helpful its coaching is. The development process itself becomes a study in human–AI creative collaboration.

The core thesis: **AI as collaborator, not creator.**

## Author

**Lilla Tillo**: musician, producer, and student in Computational Media & Creative Technology at Whitman College (Class of 2028). [GitHub](https://github.com/lilltill7) · lillabryar@gmail.com
