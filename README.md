# 🐝 beelieveInYourself

> *"According to all known laws of aviation, there is no way a bee should be able to fly."*
>
> *"...and yet here we are, filling your entire screen with the Bee Movie script."*

### 👉 [play it here — bitmousekatze.github.io/beelieveinyourself](https://bitmousekatze.github.io/beelieveinyourself/)

---

## what is this

it's the bee movie script. word by word. filling your screen. with idle game mechanics. and a casino.

you press start. the words come. they do not stop. yellow. black. yellow. black. just like the bee. and while you listen, you earn honey. and with honey you buy upgrades. and with upgrades you get more honey. and somewhere in there you can gamble it all on blackjack.

## features

- ✅ **9,157 words** of the Bee Movie script rendered all at once, revealed live as the voice speaks them
- ✅ **text-to-speech** — browser built-in, or plug in an ElevenLabs API key for an AI voice
- ✅ **pitch, voice, and speed controls** — "Normal" label at the default rate so you can always find it
- ✅ **4 display modes** — LIST (default), FALL (Matter.js physics), FLOAT (words drift upward), BOUNCE (ricochet physics)
- ✅ **4 color modes** — BEE (yellow/black), RAINBOW, MATRIX, CHAOS
- ✅ **pause / resume** — saves your word position so you can pick up exactly where you left off
- ✅ **auto-scroll** — follows the current word in LIST mode; pauses 4 seconds if you scroll up to read ahead
- ✅ **15 collectible milestones** mapped to exact moments in the script
- ✅ **🍯 honey economy** — catch bees by clicking them, earn honey, spend it in the shop
- ✅ **idle upgrades** — 7 tiers from Virtual Mouse to Bee Movie Studio, each generating honey per second
- ✅ **virtual mice** — animated cursors that hunt and click bees automatically
- ✅ **🎰 bee casino** — full blackjack (6-deck shoe, split, double, insurance, 3:1 BJ) and roulette (SVG wheel, full betting table, fireworks on wins)
- ✅ **gambling gated** — casino is locked while the script is paused; you have to listen to play
- ✅ **achievements** — bee catching, time listening, display/color mode discoveries, script completions
- ✅ **daily rewards** — 69 🍯 base, doubles each consecutive day; book-open animation, 3-second claim countdown
- ✅ **trivia for missed days** — answer a Bee Movie trivia question to retroactively claim a missed daily reward; reward doubles the further back in time; wrong answer means no honey
- ✅ **username persistence** — saved to localStorage, auto-filled on every visit
- ✅ **mobile support** — iOS Safari speech priming, boundary fallback timer, touch handlers, responsive layout
- ✅ **everything persists** — honey, shop upgrades, achievements, streak, and word position survive page refresh
- ✅ **built with AI** — iteratively developed through conversations with Claude (see [how was this made?](beelieve.html))

## milestones

15 milestones hidden along the progress bar, mapped to the exact word in the script where each moment occurs.

| # | milestone | word # | % |
|---|-----------|-------:|--:|
| 1 | 🐝 Yellow, black. Yellow, black. | 47 | 0.5% |
| 2 | 🎓 Graduation Day | 298 | 3.3% |
| 3 | 🌻 Pollen Jocks! | 692 | 7.6% |
| 4 | 🌸 She saved my life | 2,187 | 23.9% |
| 5 | 🎷 You like jazz? | 2,251 | 24.6% |
| 6 | 🧠 Thinking bee! | 3,118 | 34.1% |
| 7 | 🍯 Honey Farms discovered | 3,760 | 41.1% |
| 8 | ⚖️ The trial begins | 4,998 | 54.6% |
| 9 | 🎤 Mr. Sting takes the stand | 5,395 | 58.9% |
| 10 | ✊ FREE THE BEES! | 6,817 | 74.4% |
| 11 | 🏆 The bees win! | 6,833 | 74.6% |
| 12 | 🌺 Flowers are dying... | 7,284 | 79.5% |
| 13 | ✈️ Barry flies the plane | 8,142 | 88.9% |
| 14 | 🛬 Barry, we did it! | 8,759 | 95.7% |
| 15 | 🎬 No rehearsal for that. | 9,157 | 100% |

## shop upgrades

buy upgrades with honey to generate more honey per second automatically. costs scale at 1.15× per owned.

| upgrade | bps each |
|---------|----------|
| 🖱️ Virtual Mouse | auto-clicks bees on screen |
| 🚁 Bee Drone | passive honey generation |
| 🏠 Mini Hive | more passive honey |
| 🌸 Pollen Farm | even more |
| 🏭 Honey Distillery | substantial BPS |
| ⚖️ Barry's Lawyer | serious honey |
| 🎬 Bee Movie Studio | maximum output |

## casino

the 🎰 CASINO button appears in the gameplay header once you start. gambling is blocked while paused — you have to actually listen.

**Blackjack** — 6-deck shoe, Fisher-Yates shuffled, reshuffles below 20 cards. Place bets in up to 3 hand slots via chips (25 / 50 / 100 / 500 / 1000). Hit, Stand, Double Down (costs another bet), Split (up to 8 hands). Insurance when dealer shows Ace (auto-decline toggle). Natural blackjack pays **3:1**.

**Roulette** — SVG wheel with all 37 numbers, animated 4-second spin. Full betting table: straight numbers, splits, streets, corners, dozens, columns, and outside bets (red/black/even/odd/high/low). Canvas particle fireworks on wins.

## how to use

1. go to [the website](https://bitmousekatze.github.io/beelieveinyourself/)
2. enter a name (saved automatically for next time)
3. choose a voice and speed
4. optionally paste an ElevenLabs API key for a better voice
5. press **▶ START FRESH** or **⏩ RESUME** if you've been here before
6. watch the bee movie script fill your screen
7. click bees, buy upgrades, gamble your honey, unlock achievements
8. reflect on your choices

## how it works

all 9,157 words are pre-rendered as invisible grey spans the moment you press start. the TTS engine speaks full sentences; the `onboundary` event fires at each spoken word and lights the matching span yellow or black in real time. sentences are pre-queued in `onstart` of the current sentence to eliminate gaps between them. a fallback character-rate timer handles browsers (iOS Safari) that don't fire `onboundary`.

## tech stack

- HTML · CSS · JavaScript
- Web Speech API (built-in TTS)
- Web Audio API (ElevenLabs playback)
- Matter.js (FALL mode physics)
- localStorage (all progress)
- ElevenLabs TTS (optional, user-supplied key)
- GitHub Pages (hosting)
- the bee movie (2007, dir. Simon J. Smith & Steve Hickner)
- Claude (claude.ai/code) — built iteratively through AI conversation

## local storage

everything lives under `beelieve_progress` in localStorage:

| key | what it stores |
|-----|----------------|
| `beesTotal` | current spendable honey |
| `beesCaught` | all-time bees caught |
| `listeningSeconds` | total active listening time |
| `completions` | full script finish count |
| `savedLitCount` | word index to resume from |
| `claimedDates` | ISO dates of claimed daily rewards |
| `adDays` | ISO dates of trivia-claimed missed days |
| `shop` | upgrade owned counts by ID |
| `unlocked` | achievement unlock dates by ID |

username saved separately under `beelieve_username`.

## faq

**Q: why does this exist?**
A: beelieve in yourself

**Q: can I change the speed?**
A: yes. the slider goes to 38. "Normal" is labeled so you can find it again.

**Q: what's the best voice?**
A: the browser ones vary wildly by OS. for a good one, get a free ElevenLabs key — there's a help button on the start screen.

**Q: I muted the tab and the game paused?**
A: yes. that's intentional. you have to listen.

**Q: will you add other movie scripts?**
A: perhaps. do you have a suggestion. is it the bee movie again.

**Q: is this legal?**
A: it's a meme. dreamworks has bigger fish to fry. or bigger flowers to pollinate. we don't know how bees work.

---

*made with 🍯, questionable decision-making, and a lot of Claude*
