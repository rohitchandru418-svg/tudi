# Minsky: The Workshop

*Interactive website concept featuring Marvin | Version 2 | Concept document for the Minsky team*

## 1. The idea in one page

A traditional agency website asks the visitor to scroll, read, and decide. This one asks them to **walk into a workshop**, sit at a desk, and talk to Marvin.

The visitor never reads about Minsky. They experience it: a retro loading ritual, a room full of real work, a monitor that wakes up, and a character who listens to their problem and hands back a printed solution brief.

**One-line pitch:** *Walk in. Tell Marvin your problem. Walk out with a plan.*

**What the visitor feels, in order**

1. Curiosity: the loader shows the evolution of the web in ASCII.
2. Wonder: a real room, with real work on the wall.
3. Intimacy: the camera zooms into the monitor and Marvin appears.
4. Being understood: Marvin answers their problem.
5. Confidence: a printed brief arrives, and sending it is one click.

**The principle behind every decision:** the visitor should get trust and hope that Minsky is the right team to build their idea, without scrolling and without reading paragraphs.

## 2. Full journey at a glance

```
[1 LOADER] -> [2 WORKSHOP ROOM] -> [3 ZOOM INTO MONITOR] -> [4 MARVIN TERMINAL]
                                                                   |
                              +------------------------------------+
                              |
         [Philosophy] [Capabilities] [Start project] [FAQ] [Contact]
                              |
                      [5 PROBLEM INPUT]
                              |
                      [6 SOLUTION BRIEF]
                              |
                      [7 PRINTER DRAWER] -> send to Minsky / download
```

| Stage | Screen | Job to be done | Time |
| --- | --- | --- | --- |
| 1 | Loader | Build anticipation, show Minsky's range across web eras | 5-8 s |
| 2 | Workshop room | Show proof, craft and personality | 5-15 s |
| 3 | Zoom transition | Move from "looking" to "using" | 2 s |
| 4 | Marvin terminal | Let the visitor choose their own path | open |
| 5-6 | Problem to brief | The conversion moment | 1-2 min |
| 7 | Printer drawer | Make the next step feel natural | 30 s |

## 3. Stage 1: The loader

### What you described

A retro ASCII progress bar with the percentage at the bottom left or right, a retro border, and above it an animation showing how application UI has evolved: a year-2000 monitor, the search-box era, modern apps, 3D and three.js websites, and AI.

### How I would design it

```
+------------------------------------------------------------+
|                                                            |
|        +----------------------------+                      |
|        | My Computer       [_][X]   |      <- era frame      |
|        |----------------------------|         changes as   |
|        | [Home] [Links] [Mail]      |         progress grows |
|        | Welcome to my page!        |                      |
|        +----------------------------+                      |
|                                                            |
|   2000 ---- 2005 ---- 2012 ---- 2020 ---- NOW              |
|                                                            |
|   [##################------------]                   58%   |
|   booting the workshop...                                  |
+------------------------------------------------------------+
```

### The five era frames (each one plays while the bar passes its range)

| Progress | Era label | What the ASCII frame shows |
| --- | --- | --- |
| 0-20% | 2000 | A boxy desktop window with a title bar, a page counter and blue-link style menu |
| 20-40% | Search era | A centered empty page with a single search box and two buttons (generic, no brand logos) |
| 40-60% | App era | Cards, a hamburger menu, rounded buttons, a mobile frame |
| 60-80% | 3D era | A wireframe cube that rotates, drawn in ASCII, standing for three.js sites |
| 80-100% | AI era | Marvin's face and a blinking prompt: "how can I help you?" |

```
 2000            Search era        App era           3D era            AI era
+----------+    +----------+    +----------+          /\          +----------+
|[_][X]    |    |          |    | = Menu   |         /  \___      | (o_o)    |
|Welcome!  |    | [search] |    | [card]   |        /   /   /|     | how can  |
|Visitors: |    | [Go]     |    | [card]   |       +---+---+ |     | I help?  |
|000123    |    |          |    | [Start]  |       |   |   |/      | > _      |
+----------+    +----------+    +----------+       +---+---+       +----------+
```

Each frame "redraws" in ASCII with a typewriter effect, then dissolves into the next. The last frame (AI era) should be Marvin's face, which becomes the bridge to the next stage.

### Improvements I recommend

- **Make the bar honest.** Tie the percentage to real loading of the 3D scene, audio and fonts, so the loader is not fake. If assets are fast, the loader still plays at least the five eras so the story is seen.
- **Skip for returning visitors.** First visit: full loader. Next visits: a 1-2 second version, with a small `SKIP >>` always visible.
- **Keep the loader tiny.** It must start instantly, so build it in plain HTML, CSS and a little JavaScript, separate from the heavy 3D bundle.
- **Text under the bar** rotates short status lines in Marvin's voice, for example: `warming up the monitor...`, `dusting the shelves...`, `waking Marvin...`.
- **Optional sound:** a soft keyboard or floppy click, off by default.
- **Do not copy brand marks.** Evoke the Google-era search page generically, with no logos.

## 4. Stage 2: The workshop room

### What you described

An environment with a desk, monitor and chair. On the wall: your works, blogs and articles as books, case studies as files, services as sticky notes. The monitor shows the logo, glitches into different things like eyes (so it reads as AI), then a heading with a START button.

### Room layout

```
+------------------------------- WALL -------------------------------+
|                                                                    |
|  [FILE] [FILE] [FILE]        [NOTE][NOTE]       [BOOK][BOOK][BOOK] |
|  case studies (pinned)       services           blog / articles    |
|                                                                    |
|                      +-----------------+                          |
|                      |    MONITOR      |                          |
|                      |  logo -> eye    |                          |
|                      |  [ START ]      |                          |
|                      +--------+--------+                          |
|   (desk lamp)  ======= D E S K ======    (plant)                  |
|                    [chair]                                         |
+--------------------------------------------------------------------+
```

### What each object does

| Object | Represents | On hover | On click |
| --- | --- | --- | --- |
| Files pinned to the wall | Case studies (COORD, TNGSS, TVK, ICDIC and others) | File lifts slightly, project name appears | Opens a short case study card over the room |
| Books on a shelf | Blog / articles | Book slides out a little, title appears | Opens the article in a reading panel |
| Sticky notes | Services: AI-Native Apps, Web Design, Full-Stack Product Development (plus websites, web apps, mobile apps) | Note wiggles, one-line promise shows | Opens a short service card with a "start with this" button |
| Monitor | The main entrance | Screen brightens | Starts the zoom (same as START) |
| Chair | Personality | Slight spin | Easter egg |
| Desk lamp | Mood | Light flickers | Toggles day/night lighting |

The room should work as a **second way in**. A visitor who wants proof can explore the wall. A visitor who wants action presses START. Both lead to Marvin.

### The monitor sequence (idle loop)

```
frame 1:  MINSKY logo
frame 2:  glitch (horizontal tear, colour split)
frame 3:  an ASCII eye opens  ( O )
frame 4:  glitch
frame 5:  heading text types out: "Tell us your problem. We'll plan the solution."
frame 6:  [ START ] blinks
```

The eye is the AI cue. Glitching between logo, eye and heading tells the visitor, without words, that this is a studio that builds intelligent things.

### Improvements I recommend

- **Slow camera drift and mouse parallax** so the room feels alive without needing interaction.
- **Marvin peeks in** from behind the monitor or on a small desk toy after about 10 seconds of idle, nudging the visitor toward START.
- **Hotspot hints:** a faint pulsing outline on first visit so people know the wall is clickable.
- **Keep the wall real.** Every file, book and note must link to something real. No placeholder items on launch.
- **Retro but premium lighting:** warm lamp, soft CRT glow, light dust particles. Avoid clutter.
- **Mobile version:** a simplified room (monitor centered, wall objects reachable through a swipe carousel) rather than a full 3D scene.

## 5. Stage 3: Zoom into the monitor

### What you described

When the visitor clicks START, the camera zooms into the monitor and the monitor's bevels stay as the screen border. Inside, Marvin appears in ASCII.

### How it works

1. The camera dollies toward the monitor over about 1.5 seconds.
2. The room fades out as the screen fills the viewport.
3. The monitor's plastic bevel remains as a **permanent frame** around the experience, so the visitor feels they are "inside the computer".
4. A quick scanline sweep, then Marvin's boot text appears.

This frame stays for everything that follows: Marvin's terminal, the brief, and the printer. It also gives a clean, consistent retro look and hides any seams between 3D and 2D.

**A small but important detail:** the START click also unlocks audio, because browsers only allow sound after a user action. That is what makes Marvin's voice possible in the next stage.

## 6. Stage 4: Marvin's terminal

### What you described

Marvin introduces himself in ASCII and asks what the visitor wants, with action buttons. Clicking Philosophy makes Marvin explain it by voice, with typography on the left. The same for Capabilities, Start Project, FAQ and Contact. There is also an input box to describe the problem.

### Screen layout

```
+=====================[ MONITOR BEVEL / FRAME ]=====================+
|                                                                 |
|  LEFT PANEL (typography)         |   MARVIN STAGE               |
|                                  |                              |
|  "We build software as an        |       .-----------.          |
|   act of care."                  |       | o     o   |          |
|                                  |       |    __     |          |
|  words highlight as Marvin       |       '-----------'          |
|  speaks them                     |      (Marvin, ASCII)         |
|                                  |                              |
+-----------------------------------------------------------------+
|  [ PHILOSOPHY ] [ CAPABILITIES ] [ START PROJECT ] [ FAQ ] [CONTACT] |
|  > tell Marvin your problem_                              [ SEND ] |
+=================================================================+
```

*Marvin's real look comes from your own character artwork. The ASCII above is only a placeholder for position and size.*

### The five menu buttons

| Button | What Marvin says (voice) | What the left panel shows | Ends with |
| --- | --- | --- | --- |
| **Philosophy** | Building software is an act of care: for end users and for the developers who maintain it later. Sustainable, human-centric software; open source for cost and values; software that fades into the background and can be maintained without heroics and scaled without breaking the bank. | Big kinetic words from the philosophy, each lighting up in sync with the voice | "Want to tell me your problem?" |
| **Capabilities** | AI-native apps, web design, and full-stack product development, plus the process behind them. | Three large service blocks; the process words (Ideation, Research, Strategy, Design, Development, Architecture, Data Modelling, Deployment, Analytics) appear as a progress line | "Which of these sounds closest to yours?" |
| **Start project** | Marvin begins the guided path and asks for the problem. | The problem input and the first questions | The brief |
| **FAQ** | Marvin answers the top questions in short spoken lines. | A small list the visitor can tap; answers type out | "Anything else?" |
| **Contact** | Marvin gives the ways to reach the team. | Email, phone, social links | A short message form, plus "or send me your brief" |

### Voice: how I would handle it

- **Recommended:** pre-recorded voice lines in one consistent voice for Philosophy, Capabilities, FAQ and Contact. This gives brand consistency and works offline.
- **Always show captions** (the left typography doubles as captions), because many people browse with sound off.
- **Mute and pause controls** are always visible, and a `Voice: ON/OFF` toggle remembers the choice.
- **Languages:** decide early whether you want English only, or English plus Tamil voice and text.
- **Speak in short chunks** (under about 20 seconds each) so visitors can jump between topics without waiting.

### Marvin's behavior rules

- Never talks for long. Two short lines on screen, a few short sentences by voice.
- Asks before he tells. Says when he is not sure.
- Never hypes. No buzzwords.
- Always returns to the same question: "what are you trying to build?"

### Marvin's states (variations of your design)

| State | When |
| --- | --- |
| Idle | waiting, small blink |
| Speaking | during voice, mouth/eye animation synced to audio |
| Listening | while the visitor types |
| Thinking | generating the brief |
| Hmm | the problem is unclear or risky |
| Ready | brief completed |

## 7. Stage 5: The problem input and the solution brief

### What you described

The visitor writes a problem in the input box. We give a solution brief. If there is related past work, we use it. If there is not, AI creates the brief. It is not 100% accurate and may vary based on decisions needed, so there is a disclaimer.

### Decision flow

```
visitor writes problem
        |
        v
[ understand ]  too vague? ---> Marvin asks 1-2 follow-up questions
        |
        v
[ match against Minsky work library ]
        |
   +----+----------------+
   |                     |
 match found         no strong match
   |                     |
 brief built from    brief generated by AI from Minsky's
 real past project   services, process and tech principles
 + similar case      (clearly labeled AI-generated)
   |                     |
   +----------+----------+
              |
        [ disclaimer ]
              |
        [ printer drawer ]
```

### What the brief contains

| Section | Content |
| --- | --- |
| Your problem | The visitor's own words, tidied |
| What we understood | 2-3 lines in plain language, so they feel heard |
| Suggested solution | The type of product (website, web app, mobile app, AI-native) and the core features |
| Approach | The process steps that apply (Research, Strategy, Design, Development, Deployment, and so on) |
| Similar work | A real Minsky project if one matches, with a link. If none, it says so honestly |
| Open decisions | The questions that would change the plan (users, scale, integrations, budget, deadline) |
| Rough range (optional) | A time or budget range only if Minsky decides to show one, clearly marked as an estimate |
| Next step | Send to the team |

### The disclaimer (suggested wording)

> *This brief is a starting point, generated to help you and our team talk faster. It is not a quote or a commitment. The right solution depends on decisions we make together, and details may change.*

Show it **on the brief itself and on the printout**, not hidden in a footer.

### Guardrails (important for trust)

- **Never invent past work.** If no real project matches, say so: "we haven't built exactly this, but here is the closest."
- **No fake precision.** No exact prices or dates unless your team has approved a rule for ranges.
- **Label AI-generated parts** clearly, so the visitor knows what came from past work and what came from AI.
- **Ask before assuming.** If the problem is vague, Marvin asks one or two questions instead of guessing.
- **Protect the system:** rate limiting, input length limits, and protection against prompt injection (people typing instructions to break the bot).
- **Privacy:** tell the visitor what is stored. Do not collect personal data until they choose to send the brief.
- **Fallback:** if the AI service fails, Marvin says so and offers the contact form, so the visitor is never stuck.
- **Human review:** the team reads every brief before replying.

## 8. Stage 6: The printer drawer

### What you described

Once the brief is generated, a left-side drawer slides in, a printer appears and prints the brief, and the visitor can send it by mail to reach the team.

### How it feels

```
  +------------------+
  |   PRINTER        |
  |  [==========]    |
  |  | MINSKY    |   <- paper feeds out line by line
  |  | BRIEF #0042   |
  |  | -------------- |
  |  | Problem: ...  |
  |  | Solution: ... |
  +------------------+
   [ SEND TO MINSKY ]  [ DOWNLOAD PDF ]  [ EDIT ]
```

1. A drawer slides in from the left over the terminal.
2. An ASCII printer appears and prints the brief line by line with a soft printing sound (sound is optional and off by default).
3. The paper "tears off", and the brief stays readable on a printed slip.
4. Three actions sit below: **Send to Minsky**, **Download PDF**, **Edit my answer** (goes back to the input).

### Send flow

- Visitor enters name and email (phone optional).
- The full brief is attached automatically, so they never repeat themselves.
- On send: Marvin confirms and sets expectations (for example: "the team will read it properly and reply"). Use a real reply-time promise only.
- The team receives the brief in email and, ideally, in a CRM or inbox tool.

### Improvements I recommend

- Give each brief a short reference number, so the team and the visitor can both refer to it.
- Let the visitor **copy**, **download as PDF**, or **email themselves a copy**.
- Keep the printer drawer closable, and keep the brief available if they want to explore another menu item.
- Print a small line at the bottom: "Reviewed by a human at Minsky before we reply."

## 9. What I added to your concept

These are the improvements beyond what you described. Keep, change or remove any of them.

| Area | Addition | Why |
| --- | --- | --- |
| Loader | Real progress, a skip for returning visitors | Prevents frustration and wasted time |
| Room | Hotspot hints, Marvin peeking in, day/night lamp | Guides first-time visitors, adds life |
| Wall | Every object links to real content | Proof must be real to build trust |
| Zoom | Bevel stays as permanent frame | Hides transitions, keeps the retro feel |
| Voice | Captions, mute, pre-recorded lines | Works with sound off, consistent brand voice |
| Problem input | Follow-up questions when vague | Better briefs, feels like being listened to |
| Brief | Clear "from past work" versus "AI-generated" labels | Honesty is the main trust signal |
| Printer | Reference number, PDF, copy, edit | Makes the next step easy and flexible |
| Whole site | Skip-the-story path and a plain content version | Accessibility, SEO and impatient visitors |
| Mobile | Simplified room, tap-based menu | Most visitors may be on phones |

## 10. Accessibility, SEO and fallback

A concept this immersive must still be usable by everyone and findable by search.

- **Reduced motion:** respect the visitor's system setting. Replace the zoom and glitch with simple fades.
- **Keyboard:** every button and hotspot reachable with the keyboard, visible focus states.
- **Screen readers:** all spoken text also exists as real HTML text. Menu buttons have proper labels.
- **Plain version:** a normal, fast page set (`/work`, `/services`, `/blog`, `/contact`) that search engines and impatient visitors can use. The immersive experience is the front door, not the only door.
- **Low-end devices and slow networks:** detect weak GPU or slow connection and offer a lighter 2D version of the room.
- **Language:** if Tamil is included, test fonts, voice and line lengths early.

## 11. Suggested technology

These are suggestions to discuss with your developers, not fixed decisions.

| Layer | Suggestion | Notes |
| --- | --- | --- |
| Framework | Next.js | Good for SEO and routing |
| 3D room | three.js through React Three Fiber | Compressed models, lazy-loaded after the loader |
| Animation | GSAP or Framer Motion | Transitions, zoom, glitch, drawer |
| ASCII rendering | Monospace text grid, with canvas for the animated frames | Marvin and the era frames |
| Audio | Web Audio API or a small audio library | Pre-recorded voice, mute, captions in sync |
| AI brief | A server route calling an AI model | Strict prompt, structured output, rate limits, logging |
| Work library | A small CMS or structured JSON of past projects | Used for matching and for the wall |
| Email and PDF | Transactional email service, server-side PDF | Sends the brief to the team and the visitor |
| Hosting | A platform with edge delivery | Fast first load worldwide |

**Performance rule:** the loader appears almost instantly. The 3D room loads while the loader plays. Aim for the room to be ready as the bar reaches 100%.

## 12. Risks and how to handle them

| Risk | Mitigation |
| --- | --- |
| Visitors leave during a long load | Tiny loader, honest progress, skip option, lighter 3D assets |
| Too clever, visitor confused | Hotspot hints, always-visible menu, "skip to contact" |
| AI brief is wrong or too generic | Follow-up questions, disclaimer, human review, honest labels |
| AI is abused or fails | Rate limits, input limits, injection protection, fallback form |
| Voice annoys or is blocked | Off-by-default controls, captions, tied to a user action |
| Weak SEO | Plain content pages, real HTML text, proper metadata |
| Heavy site on mobile or old devices | Simplified mobile room, 2D fallback, asset compression |
| Overpromising in briefs | No exact prices or dates unless approved rules exist |

## 13. Build phases

| Phase | Scope | Outcome |
| --- | --- | --- |
| 1. Foundations | Marvin artwork finalized, voice script written, work library prepared | Everything the experience needs exists |
| 2. Loader and terminal | ASCII loader with era frames, Marvin terminal, the five menu buttons with voice and captions | A working core without 3D |
| 3. Brief engine | Problem input, matching, AI brief, disclaimer, guardrails | The conversion engine works |
| 4. Printer and send | Drawer, printing animation, PDF, email to team | The full funnel works end to end |
| 5. The room | 3D workshop, wall objects, monitor glitch, zoom transition | The wow moment is added |
| 6. Polish | Mobile version, accessibility, SEO pages, performance, testing | Ready to launch |

Building the terminal and brief engine **before** the 3D room is deliberate. It proves the conversion idea early, and the room then becomes the layer of delight on top.

## 14. How to measure success

- Visitors who pass the loader and reach the room
- Visitors who click START
- Visitors who press a menu button, and which ones
- Visitors who write a problem
- Briefs generated, briefs printed, briefs sent
- Send rate per 100 visitors
- Quality of briefs, judged by the team (do they shorten the first call?)
- Skip rate and drop-off at each stage
- Voice on versus off, and mobile versus desktop behavior

## 15. What is needed from the Minsky team

- [ ] Marvin artwork (image or ASCII) with the expressions needed for each state
- [ ] Final voice scripts for Philosophy, Capabilities, FAQ and Contact (and a language decision)
- [ ] The list of work for the wall: case studies, articles, services
- [ ] A short, verified write-up for each case study (problem, what was built, where it lives now)
- [ ] An AI-native case study, if one exists
- [ ] The FAQ questions and answers
- [ ] A decision on whether the brief shows a time or budget range
- [ ] The real reply-time promise
- [ ] Where briefs should go (email address, CRM or inbox tool)
- [ ] A decision on voice: recorded by a person, or generated

## 16. One-line summary

**Minsky is not a website you read. It is a workshop you walk into, where Marvin listens, plans, and prints your next step.**
