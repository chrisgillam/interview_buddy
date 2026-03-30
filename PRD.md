# Interview Buddy — Product Requirements Document

## Overview

**Interview Buddy** is a satirical digital assessment tool disguised as a legitimate character evaluation. It presents users with a sequence of 15 questions — ranging from absurd personality prompts to timed mini-games — and delivers deadpan, pseudo-professional feedback after each response. The tone should feel like a corporate HR tool that has gone slightly unhinged.

The tool is a single-page web application. Questions are presented one at a time. After the user answers, feedback is displayed before they advance to the next question. At the end, a summary "report" is shown.

---

## Preamble (Landing Screen)

Before Question 1, display a landing screen with the following copy:

> **Welcome to Interview Buddy™**
>
> Technical skills can be taught. Domain knowledge can be acquired. But **character** is immutable.
>
> This assessment does not measure what you know. It measures *who you are* — at a molecular level.
>
> Your results are final and will be kept on file permanently.
>
> Press **Begin Assessment** to proceed.

The "Begin Assessment" button advances to Question 1.

---

## Question Specifications

### Question 1 — "Who's Your Guy?"

- **Type:** Image + multiple choice (4 options)
- **Display:** A picture of the four Teenage Mutant Ninja Turtles, clearly labeled.
- **Prompt:** "Who's your guy?"
- **Options:** Leonardo, Donatello, Michelangelo, Raphael
- **Response logic:**
  - Leonardo → "Fine choice."
  - Donatello → "Fine choice."
  - Michelangelo → "Fine choice."
  - Raphael → "There was only one wrong answer here, and you picked it."

---

### Question 2 — "Hot Dog Capacity"

- **Type:** Integer input + special option
- **Prompt:** "In a single sitting, how many hot dogs can you eat?"
- **Input:** A number field (integers ≥ 1), plus a separate selectable option: `"0 — I don't eat hot dogs / am vegetarian"`
- **Response logic:**
  - `0 — I don't eat hot dogs / am vegetarian` → "Good. It's great to identify defective applicants early."
  - 1–3 → "Pathetic. I don't think you have what it takes."
  - 4–5 → "A respectable number."
  - 6+ → "Show some restraint."

---

### Question 3 — "The Rescue Drive"

- **Type:** Yes / No
- **Prompt:** "Your dog has been kidnapped and is being held at a location 30 minutes away. You're driving to rescue him. It's a warm night. Your windows are down. Do you listen to music on the drive there?"
- **Options:** Yes / No
- **Response logic:**
  - Yes → "Correct. Every rescue mission needs a soundtrack. You understand this instinctively."
  - No → "Your dog is out there, scared and alone, and you can't even give him the dignity of a heroic arrival? No music? Just the sound of your own breathing and the hum of the engine for 30 minutes? Sociopathic. −1 point."

---

### Question 4 — "Ghosts"

- **Type:** Yes / No
- **Prompt:** "Do you believe in ghosts?"
- **Options:** Yes / No
- **Response logic:**
  - Yes → "Defects in critical thinking detected. −1 point."
  - No → "Correct. But you should know the office *is* haunted."

---

### Question 5 — "Minesweeper Under Pressure"

- **Type:** Interactive mini-game
- **Prompt:** "Complete this game of Minesweeper."
- **Specifications:**
  - Render a simplified Minesweeper board (e.g., 6×6 grid with ~6 mines).
  - A visible **15-second countdown timer** starts immediately.
  - Standard Minesweeper rules: left-click to reveal, right-click to flag.
  - First click is always safe (no mine on first reveal).
- **Response logic:**
  - User clears the board in time → "Acceptable. Barely."
  - Timer expires or user hits a mine → "Does not perform well under pressure."

---

### Question 6 — "Cultural Literacy Check"

- **Type:** Multiple choice (4 options)
- **Prompt:** "Complete the lyric: *If there's a bustle in your hedgerow...*"
- **Options:**
  - A) "...you should probably call an exterminator"
  - B) "...don't be alarmed now"
  - C) "...it means spring has finally come"
  - D) "...check your property line"
- **Correct answer:** B
- **Response logic:**
  - B → "Correct. You may proceed."
  - Any other → "Shows unawareness of cultural touchstones. Concerning."

---

### Question 7 — "Thermostat Personality Index"

- **Type:** Number input (integer, °F)
- **Prompt:** "What temperature do you set your thermostat to at home?"
- **Input:** A number field for temperature in °F.
- **Response logic:**
  - Below 65 → "You live in a meat locker. This suggests deep psychological issues."
  - 65–67 → "Frugal to the point of cruelty. Your guests suffer in silence."
  - 68–72 → "Normal. Suspiciously normal."
  - 73–76 → "Comfortable. Soft. Unlikely to survive any kind of hardship."
  - 77+ → "You're the reason the planet is dying."

---

### Question 8 — "Toilet Paper Orientation"

- **Type:** Image + multiple choice (2 options)
- **Display:** A diagram showing a toilet paper roll in the "over" and "under" positions.
- **Prompt:** "Which way does the toilet paper go?"
- **Options:** Over / Under
- **Response logic:**
  - Over → "Correct."
  - Under → "Fundamentally untrustworthy. This answer has been flagged."

---

### Question 9 — "Reaction Time Test"

- **Type:** Interactive timed click
- **Prompt:** "Click the button the moment it turns green."
- **Specifications:**
  - Display a large circular button that is red/grey.
  - After a **random delay** (2–6 seconds), the button turns green.
  - Measure time between color change and click (in ms).
  - If the user clicks *before* it turns green, that's a false start.
- **Response logic:**
  - < 200ms → "Suspicious. Either you're a housefly or you clicked early. −1 point for dishonesty."
  - 200–350ms → "Excellent reflexes. You'd survive the first five minutes of a disaster movie."
  - 351–500ms → "Adequate."
  - 501ms+ → "Slow. In nature, you would have been eaten."
  - False start (click before green) → "Jumped the gun. Impulsive. Noted."

---

### Question 10 — "The CAPTCHA"

- **Type:** Fake image grid selection
- **Prompt:** "Select all images containing a stop sign."
- **Display:** A 3×3 grid of images, all of which are various red objects (fire hydrant, red balloon, apple, ketchup bottle, ladybug, red car, tomato, red door, strawberry). **None of them are stop signs.**
- **Response logic:**
  - User selects any images and submits → "There were no stop signs. You see what you're told to see. Susceptible to groupthink."
  - User submits with nothing selected → "Correct. There were no stop signs. You think for yourself. Rare."

---

### Question 11 — "Weakness Assessment"

- **Type:** Multiple choice (4 options)
- **Prompt:** "Please select your biggest weakness."
- **Options:**
  - A) "I'm too much of a perfectionist"
  - B) "I care too much about my work"
  - C) "I have trouble saying no to people"
  - D) "I procrastinate constantly and have no excuse for it"
- **Response logic:**
  - A → "We've heard that one before. Everyone has. It wasn't clever the first time."
  - B → "This is a job interview cliché from 2004. You Googled 'good weaknesses to say in an interview,' didn't you."
  - C → "That's not a weakness, that's a humblebrag. −0.5 points for trying to game the system."
  - D → "Refreshing candor. +1 point. You're still not getting the job, but we respect you."

---

### Question 12 — "Is a Hot Dog a Sandwich?"

- **Type:** Multiple choice (4 options)
- **Prompt:** "Is a hot dog a sandwich?"
- **Options:**
  - A) Yes
  - B) No
  - C) It depends on the structural integrity of the bun
  - D) I refuse to answer this
- **Response logic:**
  - A → "Bold. Wrong, but bold."
  - B → "Correct. But I want you to know there's no consensus on this, and you've chosen a side in a war."
  - C → "An engineer's answer. You must be fun at parties."
  - D → "Cowardice is not a strategy. −0.5 points."

---

### Question 13 — "Typing Under Duress"

- **Type:** Timed text input
- **Prompt:** "Type the following sentence exactly. You have 10 seconds."
- **Sentence to type:** `"The quick brown fox jumps over the lazy dog's existential dread."`
- **Specifications:**
  - Display the sentence in a slightly small, slightly hard-to-read serif font (but still legible).
  - 10-second countdown timer visible.
  - Exact character match required (case-sensitive, punctuation-sensitive).
- **Response logic:**
  - Perfect match in time → "Flawless execution under pressure. You may have a future here."
  - Close but not exact → "Close. But 'close' is what you say about horseshoes and hand grenades, not job applications."
  - Time expired → "Too slow. The moment has passed. As it does in life."

---

### Question 14 — "Ethical Flexibility Assessment"

- **Type:** Slider input
- **Prompt:** "You find a $20 bill on the ground in an empty parking lot. On a scale of 1–10, how hard do you try to find the owner?"
- **Input:** A slider from 1 (not at all) to 10 (extensive search)
- **Response logic:**
  - 1–2 → "Honest. Selfish, but honest. We can work with that."
  - 3–5 → "You'd look around for about four seconds and then pocket it. We know. Everyone knows."
  - 6–8 → "You're either lying or you have a crippling sense of guilt. Either way, notable."
  - 9–10 → "You would spend your afternoon tracking down the owner of a $20 bill in an empty parking lot? That's not integrity, that's a disorder."

---

### Question 15 — "Final Question"

- **Type:** Yes / No
- **Prompt:** "Last question. Are you a good person?"
- **Options:** Yes / No
- **Response logic:**
  - Yes → "The confidence is noted. Narcissism assessment: flagged for review."
  - No → "At least you're honest. That's more than most people who answered 'Yes' can say."

---

## End Screen — "Assessment Complete"

After Question 15, display a results summary screen:

> **Assessment Complete.**
>
> Your results have been compiled and are now part of your permanent record.
>
> **Overall Score:** [Display a random number between 41 and 67 out of 100, regardless of actual answers]
>
> **Personality Profile:** [Randomly select one from a set of absurd labels, e.g.:]
> - "Chaotic Adequate"
> - "Reluctantly Competent"
> - "Suspiciously Normal"
> - "Confidently Incorrect"
> - "Aggressively Fine"
> - "Dangerously Mid"
>
> **Recommendation:** "Further evaluation recommended. Please do not contact us."
>
> A "Download Your Results" button that, when clicked, just downloads a text file containing: *"There are no results. This was never real. But you knew that. Didn't you?"*

---

## Technical Requirements

### Stack
- **Frontend:** Single-page application (HTML/CSS/JS or React)
- **State management:** Track current question index, user answers, and point deductions/additions for the summary
- **No backend required** — all logic is client-side
- **No authentication** — the tool is publicly accessible

### UX / Design Guidelines
- **Tone:** The visual design should look *almost* legitimate. Clean, corporate, slightly sterile. Think "enterprise SaaS onboarding" meets "DMV website."
- **Typography:** A serious sans-serif font (e.g., Inter, IBM Plex Sans). No whimsical fonts until the punchlines land.
- **Progress bar:** Display a progress indicator (e.g., "Question 3 of 15") at the top of each question screen.
- **Transitions:** Smooth, professional fade transitions between questions. The comedy comes from the content, not from zany animations.
- **Feedback display:** After the user submits an answer, display the feedback message with a brief pause (~1 second) before showing a "Next" button. The feedback should feel like it's being *delivered* to them, not just appearing.
- **Mobile responsive:** Should work on desktop and mobile.
- **Color palette:** Muted corporate blues and grays. Accent color for buttons. The Minesweeper and reaction test can use appropriate game-specific colors.

### Assets Needed
- TMNT image (Question 1) — a clear group image with the four turtles labeled or identifiable by color/weapon.
- Toilet paper diagram (Question 8) — over vs. under positions.
- Nine red-object images (Question 10) — for the fake CAPTCHA grid. Must all be clearly red and clearly *not* stop signs.

---

## Scoring System (Internal)

The scoring system is purely for show. However, track the following internally so the summary screen can reference it:

| Event | Points |
|-------|--------|
| Chose Raphael (Q1) | −1 |
| Vegetarian (Q2) | −2 |
| No music on rescue drive (Q3) | −1 |
| Believes in ghosts (Q4) | −1 |
| Failed Minesweeper (Q5) | −1 |
| Wrong lyric (Q6) | −1 |
| Thermostat 77°F+ (Q7) | −1 |
| Clicked CAPTCHA images (Q10) | −1 |
| Fake weakness (Q11 A/B/C) | −0.5 |
| Refused hot dog question (Q12) | −0.5 |
| Dishonest reaction time (Q9) | −1 |
| Said "Yes" to good person (Q15) | −1 |

Starting score: random number between 41–67. Apply deductions. Floor at 0. The actual math doesn't need to be rigorous — the score is meaningless and the user should vaguely suspect this.

---

## Out of Scope (For Now)
- User accounts or saved results
- Shareable result links (future enhancement — would be good for virality)
- Leaderboards
- Actual personality assessment validity
- Any form of scientific rigor whatsoever
