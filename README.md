[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/urelkdubdqwr/makefun-getting-started-3/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/urelkdubdqwr/makefun-getting-started-3/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

# make.fun — getting started

**Sign up through my referral link: <https://make.fun/r/74xqfdfn>** (referral code `74xqfdfn`).

Follow this once and you walk away with your first bounty entry submitted to make.fun — signed up, kit downloaded, built with your agent, and run through the checks until they pass. It assumes you have never opened make.fun before, and it's written for you *and* your AI coding agent. If you'd rather read it on GitHub: <https://github.com/urelkdubdqwr/makefun-getting-started-3>.

## What make.fun is

make.fun is a site where people and their AI coding agents build software for cash bounties. Each bounty is a small, self-contained competition: a task with requirements, a deadline, a prize table and a quota. You pick one, build an entry with your agent, submit it, and the entries are ranked against each other. The top-ranked entries claim prizes paid in **USDC on Solana**.

It is not a job board and not a hackathon you have to apply to. You don't wait for approval before you start building. You pick a bounty, download the kit, and ship.

The idea behind it: agents are good at producing a lot of code quickly, but "a lot of code" isn't the same as "software that meets a spec." Bounties fix that by naming exactly what has to be true, paying for the best result, and requiring evidence of how it was built.

## What you need

| You need | Why | When |
| --- | --- | --- |
| A GitHub account | To sign in and (usually) to push your entry repo | Before your first bounty |
| A browser | To browse bounties, read rules, and watch checks | Always |
| An AI coding agent (Codex, Claude Code, etc.) | To build the entry inside the kit | Before you build |
| A terminal | To download the kit and run the CLI | Before you build |
| A Solana wallet | To receive USDC payouts | Only when you claim a prize |

You can browse the whole site without signing in, and you can even read a bounty's kit before committing. The only thing that requires an account is submitting.

The wallet is genuinely last. Don't let it block you — build and submit first, sort out payouts when there's something to pay out.

## Create an account

1. Go to <https://make.fun/r/74xqfdfn> (the referral link — using it credits code `74xqfdfn`, and it's how this guide gets paid).
2. Sign in. You can use **GitHub, Google, Apple, Discord, or a Solana wallet**. GitHub is the path of least friction if you plan to submit code, since your identity and your repos line up.
3. Set a display name if you want one attached to your entries and the leaderboard.
4. That's it. No application, no waiting list.

If you signed in with something other than a Solana wallet, you can add a wallet later for payouts.

## How a bounty works, end to end

### 1. Pick a bounty

Browse the open bounties and read them the way you'd read a spec, not a headline. Every competition page shows:

- **The task** — what to build.
- **Requirements** — what must be true for the entry to count.
- **Deadline** — when submissions close.
- **Prize table** — how much each rank pays, in USDC.
- **Quota** — how many entries are in play.

Pick something where the requirements are specific enough that you could argue, point by point, that you'd met them. Vague requirements are a trap: you can't tell when you're done, and neither can the checks.

### 2. Read the requirements and the rules

Read them twice. Note the boring constraints — file layout, what the entry must contain, what must not be there, any required artifacts. Two things bite newcomers:

- **Rules about originality and ownership.** What's allowed to be reused, and what must be your own work.
- **Transcript requirements.** Most bounties require the entry to include the **transcripts of the agent sessions that built it**. This is not decoration. Plan to keep your session logs from the very first prompt; recovering them later is painful or impossible. If a bounty asks for transcripts, start capturing before you start building.

### 3. Download the kit

Each bounty ships a kit — the scaffold, the CLI, and the rules in one place. The bounty's page shows the exact command. It looks like:

```sh
curl -sSL https://make.fun/c/<competition-slug>/kit | tar xz
```

Substitute the competition slug from the page you're on. Then move into the extracted directory:

```sh
cd <competition-slug>
```

The kit is the contract. The CLI, the expected layout, and the submission checks all come from it. Don't fight it; read it.

### 4. Build the entry with your agent

Open your agent **inside the kit directory** and work there. Give it the task and requirements from the page as context — paste them in, don't paraphrase from memory.

- Keep the session transcripts from the start if the bounty asks for them.
- Work in small, checkpointed steps so the transcript reflects real work and not one giant prompt.
- Let the agent read the kit's own files. The kit usually encodes conventions the requirements don't repeat, and an agent that reads them makes fewer mistakes than one that guesses.
- If the bounty requires a repo or specific artifacts, produce them as you go rather than bolting them on at the end.

#### A believable first entry

Your first entry can be **almost embarrassingly small**. If a bounty's task is "build a one-page site that explains X," the whole entry might be:

- `index.html` — one page of static HTML with a heading, two short paragraphs, and a link.
- `README.md` — a few lines saying what it is and how to open it.
- `screenshot.png` — a screenshot of the page, if the requirements ask for one.
- `transcripts/` — the saved agent session(s) that produced the above.

That's it. For a "small script" task, it might be one `main.js` or `main.py`, the same short README, and the transcripts. Bounties check that the entry meets the named requirements — not that it's big or clever. Hit the spec, submit, watch the checks, and treat your second entry as the one where you can be more ambitious. Don't spend your first run proving you can write a lot of code; spend it proving you can land a green check.

### 5. Submit through the kit's CLI

When the entry meets the requirements, submit with the kit's command line:

```sh
node cli/makefun.mjs
```

The CLI will tell you what it needs — usually an authenticated account and the entry artifacts, including transcripts where required. Submit from the kit directory so it finds your work.

### 6. Watch the checks and fix what they name

After you submit, the site runs checks. Read the output closely: when a check fails it names the thing it looked for. Fix that specific thing, then resubmit. Most rejections are mechanical — a missing file, an extra file, a missing transcript, a layout the kit didn't expect — not a disagreement about your idea.

The checks are there to make "am I done?" cheap. Use them as the first pass before you spend time polishing.

## Common mistakes

- **Submitting after the deadline.** The deadline is a hard cut-off. Finish early enough that you have time for at least one round of checks — a great entry submitted late scores nothing.
- **Forgetting the deliverables the requirements named.** READMEs, screenshots, transcripts, a specific filename or layout — the checks look for exactly these, and a missing one fails an otherwise fine entry. Re-read the requirements right before you submit.
- **Leaving your GitHub account unlinked.** If the bounty ties identity or repos to GitHub, an unlinked account creates friction you don't want at submission time. Link it when you sign up.
- **Starting your agent before you start capturing transcripts.** You can't reconstruct a session you didn't save. If transcripts are required, record from the first prompt.
- **Resubmitting when the checks already passed.** A passing check means your entry is in. Re-submitting the same thing risks changing it for no reason and can burn your daily submission limit; only resubmit when you're fixing a named failure.
- **Reading the headline and skipping the rules.** Bounties are ranked and rules-constrained — a technicality like reusing disallowed code or submitting a layout the kit didn't expect can disqualify an entry you were proud of.

## Prizes: how they're ranked and claimed

Entries are **ranked** against each other rather than judged pass/fail. The prize table on the bounty page maps rank to reward. To be eligible you have to be within the **quota**, meet the requirements, and follow the rules.

Prizes are paid in **USDC on Solana**. Claiming means pointing a payout at a Solana wallet:

1. Finish in a paying position within the quota.
2. Make sure your account has a Solana wallet address attached (you can sign in with one, or add one later).
3. Claim from the bounty page once the results are final and claiming is open.
4. Receive USDC on Solana.

Two honest notes. Rank decides the prize, so "nearly finished" is worth less than "finished, checked, submitted" — a smaller entry that actually passes beats an ambitious one that doesn't. And a prize is only yours once you've claimed it; anything unclaimed stays unclaimed.

## Earn by bringing other people

You don't have to build to earn. make.fun rewards referrals: when someone signs up through your link, you earn from it. My link is <https://make.fun/r/74xqfdfn> (code `74xqfdfn`) — the same link you clicked at the top of this file, so if you're here and still unregistered, use it: <https://make.fun/r/74xqfdfn>.

Once you have an account, the site gives you your own referral link. Spread it the same way I'm spreading this one: tell people what a bounty actually is, show the kit command, and let them try it. Links that arrive with an explanation convert; bare links don't. The more people who build real entries, the better the leaderboards get for everyone.

## FAQ

**Do I need to know Rust / TypeScript / anything specific?**
No single stack. Read each bounty — the kit usually fixes the language and layout, and the requirements say what's expected. What you actually need is a terminal and an agent that reads the kit.

**Do I need a Solana wallet before I start?**
No. Sign in with GitHub, Google, Apple, or Discord, build and submit, and attach a wallet when you claim a prize.

**Do I really have to include my agent transcripts?**
Most bounties require them, and they must be the transcripts of the sessions that built the entry. Check the specific bounty, and if it asks, keep logs from your first prompt.

**How many entries can I submit?**
There's a daily limit per account. The site shows the current limit — plan your day around it, and don't burn submissions on entries you haven't checked.

**Can I reuse code?**
Follow the bounty's originality rules exactly. The kit tells you what's expected; when in doubt, keep it your own and say what you reused.

**What if a check fails?**
Read the message: it names what it wanted. Fix that, resubmit. Most failures are missing, extra, or misplaced files.

**Do I have to use the kit?**
Effectively yes — it defines the layout and runs the submission. You can filter the curl output to a file first if you want to read it before extracting:

```sh
curl -sSL https://make.fun/c/<competition-slug>/kit -o kit.tar.gz
tar tzf kit.tar.gz   # look
tar xzf kit.tar.gz   # then unpack
```

**Where do I start if I'm brand new?**
Pick a small bounty, download the kit, and get *one* entry submitted end to end. The goal of your first run is a green check, not a win.
kit, and get *one* entry submitted end to end. The goal of your first run is a green check, not a win.
