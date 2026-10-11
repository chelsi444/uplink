# Uplink: demo script for three speakers

About **2¾ minutes**, plus optional extensions if you have time and a 2-minute cut if you don't. The key terms judges listen for are in **bold** in the lines and listed in the checklist at the end.

| Speaker | Owns | Drives the laptop during |
| --- | --- | --- |
| **Sara** | the problem, the agents arguing, the close | Chelsi's part |
| **Chelsi** | the business side (Say it, photo/video), ElevenLabs, the phone call | her own Say it, then Sara's part |
| **Haatim** | how it's built (AGNTCY), when agents can't agree, the evidence | his own part |

Swap names freely: what matters is that each person owns a part and someone else's hands are on the laptop while they talk.

**How to read the lines:**
- **bold** = lean on the word
- `/` = a half-second beat
- `[PAUSE]` = stop talking, let the screen work
- *(italics)* = an action on the laptop

Speak to the judges, not the screen. Point at the screen with your hand when a line says "here".

---

## Before you walk up (5 minutes earlier)

1. App running from `~/uplink`; the terminal shows **Claude key OK**, **Voice: ElevenLabs** and **16 agents … AGNTCY A2A over NATS**. Then hide the terminal.
2. Browser, full screen (Cmd+Ctrl+F), zoom 110% if the room is big. Only two tabs, in this order:
   - **Tab 1:** http://localhost:5050/#/schedule with **Donating as: Pizza My Heart (Pacific Ave)** selected and the **Say it** tab open. Test the mic once (allow microphone access), then refresh.
   - **Tab 2:** http://localhost:5050/ops in dark mode. Under Demo controls: **Empty world** (so it's clean), **Voices on** (the phone call is the only thing spoken), and **Majority with dissent** selected in the scenario list but not run yet. Click once anywhere on the page: browsers only play sound after a click.
3. Laptop volume at about 70%, Do Not Disturb on, notifications off, phone silenced.
4. Scroll Tab 2 to the top. The Negotiation panel should show the three agents and their goals, with no donation yet.

---

## The script

### 0:00 · Sara · The problem

**On screen:** Tab 2, `/ops`. Top left, **① Agent network** (empty); top right, **② Negotiation** with the three agent cards (Speed, Cost, Need) and their goals.

> Hi, we're Sara, Chelsi and Haatim, and this is **Uplink**.
>
> The **fast** courier costs money. / The **free** volunteer might not show up. / And the closest shelter might have already eaten today, while another one has waited **five days**.
>
> We built this for **Cisco Outshift's** challenge, ***When AI Agents Disagree***, at **Level 3**. / Food rescue is a problem where agents **should** disagree.

*(Sara hands off with a look; the driver switches to Tab 1.)*

---

### 0:25 · Chelsi · The business side: just say it

**On screen:** Tab 1, the customer site: "What's left over?", **Donating as: Pizza My Heart**, the **Say it** tab.

> This is what a restaurant sees. No forms. / I'm the manager at Pizza My Heart, it's closing time, and I just **say** what's left.

*(Chelsi taps the mic and says clearly, facing the laptop:)*

> "We've got **two** pepperoni pizzas, a **dozen** chocolate chip cookies, and **five** bananas."

*(Tap to stop.)* `[PAUSE: let the order fill in]`

**On screen:** the transcript appears, then the order: pizzas, cookies, bananas, with quantities and allergens.

> **ElevenLabs Scribe**, their **speech-to-text** model, turned my voice into text, / and **Claude** matched it to *our own menu*, so the allergens come from our recipes, not a guess.

*(The driver clicks **Schedule pickup**, then **Confirm pickup**.)*

**On screen:** the pickup tracking page.

*(Switch to Tab 2.)*

---

### 0:55 · Sara · The agents argue

**On screen:** Tab 2, `/ops`. If Chelsi's pizza donation is already being negotiated, point at it: "there's our pizza." Otherwise go straight on.

> This is the operations view, where the AI agents work. / Here are three agents with **competing goals**, and there is **no boss**: / **no central decision-maker**. The table only passes messages and counts votes.
>
> *(Point at each card.)* **Speed** cares about getting food there fast, with a reliable driver. / **Cost** cares about money. / **Need** cares about one thing: whoever has waited **longest**.
>
> Each one's arguments are written by **Claude**, from **Anthropic**, / but each agent only sees the facts **its own goal** cares about, so it stays in character. / And each one has a **red line** it will not cross: cross it, and that agent **vetoes**.

*(The driver: Demo controls → **Majority with dissent** → **Run scenario**.)*

**On screen:** the current donation appears at the top. **② Negotiation** (top right) says "Agents are deliberating…" and proposals stream in one by one, while **① Agent network** (top left) lights up.

**On screen:** objections appear in red.

> Now they **object** to each other. / Speed says the volunteer is only **50% reliable**: "a no-show would spoil this food." / Cost says why pay **fifteen dollars** when a volunteer route is free.

**On screen:** the result: **"Majority 2 of 3 (Cost disagrees, kept on record)"**.

> Round three: Speed and Cost both move toward Need's shelter, from **opposite** sides. / Two of three agree, / and Cost's objection stays **on the record**.
>
> We don't force a **consensus** that isn't there. / That's a **majority with dissent**.

*(Hand to Haatim.)*

---

### 1:40 · Haatim · How it's built: real agents, real messages

**On screen:** **① Agent network** (top left) lit up: business → shelter agents → driver agents → coordinators, with the **Message log** under it.

> Everything you just watched is **real message passing**. / *(Point at the graph, then the message log under it.)* Every shelter, every driver, and each of the three negotiators is its **own agent**, / running as its **own process**: **sixteen** of them.
>
> They talk over **AGNTCY**, **Cisco Outshift's** open agent framework: / **A2A**, agent-to-agent messages, over **NATS**. / *(Point at the badge "AGNTCY · A2A over NATS · 16 agent processes".)* / Agents find each other through an **agent directory**, / and each one publishes an **A2A AgentCard** and an **OASF** record, AGNTCY's standard agent description. / If one agent goes down, it drops out, and the rest **carry on**.
>
> And one thing is **never** up for debate: **food safety**. / Code removes any plan without a fridge, with the wrong allergens, or that arrives too late, **before** any agent even sees it.

*(Hand to Chelsi.)*

---

### 2:00 · Chelsi · The phone call (ElevenLabs)

**On screen:** scroll down to **③ Phone line** (bottom left): "Ringing…", then the dispatcher and the shelter talking, with the transcript filling in. The status pill at the top reads "Dispatcher calling · driver waits".

> Once they decide, / a **dispatcher agent** calls the shelter. / Listen.

`[PAUSE: let about 8 seconds of the call play, then go on]`

*(While the call plays, the driver quietly opens Demo controls and presses **Driver cancels**. A small note says the courier will cancel when the call ends. Don't mention it yet.)*

> Two agents, two voices from **ElevenLabs Eleven v3**, their most expressive **text-to-speech** model, with real pauses and emotion. / And the shelter's answer is its agent's **real** reply. / Shelter staff can also answer by **voice** from their phone.
>
> *Only* after the call does the driver set off.

*(The driver scrolls down to **④–⑤ Delivery**, beside the call. Hand to Sara.)*

---

### 2:15 · Haatim · When agents can't agree (the heart of Level 3)

> So instead of forcing a bad deal, / they **stop**, and **escalate to a human**. / They do the same when the only compromise crosses someone's **red line**, / or when the decision depends on a fact nobody has confirmed, like *are there peanuts in this?*

> The person gets the options, the agents' reasons, and a **decide-by** time, so the food never spoils waiting. / If nobody answers, the best-supported **safe** option goes.

---

### 2:30 · Haatim · Evidence

*(The driver clicks the **Evidence** tab.)*

**On screen:** Evidence: "93% less food lost", "67% less than the best single agent", "99 of 100".

> And here's the part we're proudest of: / compared to **any one agent deciding alone**, / the team lost **67% less**. / Speed alone overspends. / Cost alone trusts volunteers who don't show. / Need alone takes risky trips.
>
> **Together, they veto each other's blind spots.**

---

### 2:40 · Sara · Close

**On screen:** go back to the Live tab, showing the result and the agent cards.

> So that's **Uplink**. / Agents with **competing goals** and **no boss**, / that disagree **out loud** over **AGNTCY**, / never compromise on **safety**, / and ask a human when agreeing would be **wrong**.
>
> Thank you. `[PAUSE]` We'd love your questions.

---

## Optional extensions (add one or two if you have 6+ minutes)

**B · The world changes (Sara, 30 s).** During any running scenario: *(Demo controls → **Shelter says full**.)*
> A shelter just called: they're full. / The agents re-plan, / and each one tells us whether the news **changed its mind**. *(Point at "That changes my pick…".)*

**C · Pull an agent's plug (Haatim, 30 s).** *(Activity → **Agent services** → **Stop** on a shelter agent, run a scenario, then **Restart**.)*
> Each agent is its own service. / If one goes down, / it drops out of the directory and the others **carry on**.

**D · Photo or video (Chelsi, 25 s).** Tab 1 → **Photo / video** → upload a real photo of food.
> Claude names and counts it. / A video becomes four frames, so nothing is counted twice.

---

## The 2-minute cut

| Time | Who | Screen | Say |
| --- | --- | --- | --- |
| 0:00 | Sara | `/ops`, ② the three agent cards | The problem, in two sentences; "food rescue is where agents **should** disagree." |
| 0:20 | Chelsi | Tab 1 → **Say it** | Say the order; "**ElevenLabs** heard it, **Claude** matched our menu." Confirm. |
| 0:50 | Sara | `/ops` → Majority with dissent | Name the three goals and red lines; narrate the objections; "Majority 2 of 3, dissent **on record**." |
| 1:25 | Haatim | ① Agent network graph | "Sixteen agents, each its own process, on **AGNTCY** A2A over NATS. Safety is never negotiated." |
| 1:40 | Chelsi | ③ Phone line | Let 5 seconds of the call play: "the dispatcher **calls** the shelter." |
| 1:45 | Haatim | Decisions (Irreconcilable already run) | "When they **can't** agree, they **escalate to a human** with a decide-by deadline." |
| 1:52 | Haatim | Evidence | "**93%** less food lost than the simple approach; **67%** less than any one agent alone." |
| 2:00 | Sara | Live | The closing line. |

---

## If something goes wrong on stage

Keep talking. The judges remember calm more than a glitch.

| What happens | Who covers | What to say or do |
| --- | --- | --- |
| The mic doesn't pick up the voice | Chelsi | Switch to the **Menu** tab and tap the three items: "Same result by tapping; voice works the same way." |
| The debate takes longer than expected | Sara | Fill with the goals and red lines, or: "Each of those is a real model call; the clock waits for them so no food-safety time is lost." |
| A Claude call fails | nobody needs to | The agents fall back to their rules automatically after 20 s; keep narrating. |
| No sound | Chelsi | Read the call lines from the transcript; mention the voices are ElevenLabs. |
| The app freezes | the driver | Hard refresh (Cmd+Shift+R). If it's still frozen, switch to the backup video. |
| Ran out of time | Sara | Jump straight to the close. |
| *Irreconcilable goals* ends in a majority instead (Claude can surprise you) | Haatim | "This time they found a majority. When they can't, they escalate like this:" Click **Decisions** and explain the card, or run **Unacceptable compromise** instead. |

## Who answers which question

- **Agents, negotiation, "isn't this just a weighted score?"** → Sara
- **AGNTCY, A2A, architecture, "what's real vs simulated?"** → Haatim
- **ElevenLabs, voice, the customer experience, the business model** → Chelsi
- **Results, "does it cost more?"** → Haatim

Ready-made answers are in `docs/DEMO_DAY.md`, section 5.

---

## Key terms checklist

Make sure each of these is said out loud at least once. They're what the Cisco and ElevenLabs judges listen for.

| Term | Who says it | Where |
| --- | --- | --- |
| Cisco Outshift, *When AI Agents Disagree*, Level 3 | Sara | opening |
| competing goals, no boss / no central decision-maker | Sara | the agents argue |
| red line, veto | Sara | the agents argue |
| consensus vs **majority with dissent**, dissent on record | Sara | the result |
| reasons shown for every proposal, objection and veto (transparency) | Sara | round 2 |
| escalate to a human, decide-by deadline, safe fallback | Haatim | can't agree |
| irreconcilable goals, compromise that crosses a red line, unconfirmed fact | Haatim | can't agree |
| re-plan on new information, vote weight | Haatim | can't agree |
| AGNTCY, A2A, NATS, 16 agent processes | Haatim | how it's built |
| agent directory, A2A AgentCard, OASF record | Haatim | how it's built |
| safety is never negotiated (rules in code, before any agent sees a plan) | Haatim | how it's built |
| ElevenLabs Scribe (speech-to-text) | Chelsi | Say it |
| ElevenLabs Eleven v3 (text-to-speech), dispatcher agent calls the shelter agent | Chelsi | the phone call |
| Claude (Anthropic): menu matching, photo/video counting, each agent's arguments | Chelsi, Sara | Say it, the agents argue |
| 93% less food lost than the baseline; 67% less than the best agent alone; 100 unseen scenarios | Haatim | evidence |
