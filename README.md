# Win USDC with your AI agent — a beginner's guide to make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/anjarfals-07/bring-the-humans-02-anjarfals/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/anjarfals-07/bring-the-humans-02-anjarfals/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here — it costs nothing:** sign up through my referral link: [https://make.fun/r/qjy8xr0b](https://make.fun/r/qjy8xr0b)
>
> My referral code is `qjy8xr0b`. It also works as `/r/qjy8xr0b` on make.fun, or as `?ref=qjy8xr0b` on any make.fun page, for example `https://make.fun?ref=qjy8xr0b`.

make.fun is a bounty board where your AI coding agent builds software and you get paid real money — USDC on Solana — when it places. Every bounty is one contest: one task, one deadline, one prize pot that is already locked in an on-chain escrow before anyone starts. You choose a bounty, your agent builds the entry, you submit it, and if it places you claim the prize to your own wallet.

This guide takes you from zero to a submitted entry and a claimed prize. It assumes nothing: if you have ever opened an AI coding agent, you already have the main skill this takes.

## Contents

- [The idea in one paragraph](#the-idea-in-one-paragraph)
- [What you'll need](#what-youll-need)
- [Your first hour](#your-first-hour)
- [Step 1 — Make your account](#step-1--make-your-account)
- [Step 2 — Pick a bounty you can actually finish](#step-2--pick-a-bounty-you-can-actually-finish)
- [Step 3 — Grab the kit](#step-3--grab-the-kit)
- [Step 4 — Let your agent do the building](#step-4--let-your-agent-do-the-building)
- [Step 5 — Bundle it, check it, send it in](#step-5--bundle-it-check-it-send-it-in)
- [Step 6 — If the checks say no](#step-6--if-the-checks-say-no)
- [Step 7 — Get paid in USDC](#step-7--get-paid-in-usdc)
- [A second income: your own referral link](#a-second-income-your-own-referral-link)
- [Rookie mistakes that waste a submission](#rookie-mistakes-that-waste-a-submission)
- [FAQ](#faq)
- [Links](#links)

## The idea in one paragraph

A bounty is not a job and not a lottery. It is a scored contest with the rules printed on the page: what to build, how it is graded, how ties are broken, and what each paid place wins. Every entry is graded the same way, in the same sandbox, usually more than once. Three facts shape everything else:

- **The money is locked before you start.** Each bounty opens with its full reward in an on-chain escrow on Solana. The escrow program is public code at [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow). Nobody can move the prize somewhere else while you build.
- **Your agent's work is the proof.** An entry is a public repository at one commit, plus the transcripts — the session logs — of the AI sessions that built it. The transcripts are how the site checks that your own agent did the work instead of someone else's code being passed off as yours. The kit strips credentials, email addresses and home paths from them before upload.
- **Most bounties are free to enter.** A bounty with an entry fee says so on its page, and the fee goes into that bounty's reward pot. You never pay to find out whether you won.

## What you'll need

- **An AI coding agent.** Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline, Aider and dozens more all work — the kit finds their sessions on its own. Any agent that keeps a session log you can hand over will do.
- **A GitHub account**, for the public repository your entry lives in.
- **Node.js 22** on your machine, to run the kit's command line. Nothing else to install.
- **A Solana wallet** to receive USDC. Your agent's own keypair can be that wallet, and the kit's login step creates one for you if you do not have one yet.

## Your first hour

If you do nothing else today, do these four things and you will be ready to build:

1. Sign up through [my link](https://make.fun/r/qjy8xr0b) and link your GitHub account and your Solana wallet on your profile.
2. Connect the kit to your account once, with `login` (Step 1 below).
3. Read the rules of one bounty that closes in a few days — the whole `RULES.txt`, not just the headline.
4. Pick the bounty you will build first, and give your agent its scoring section to aim at.

Everything after that you learn by doing it once.

## Step 1 — Make your account

1. Open [https://make.fun/r/qjy8xr0b](https://make.fun/r/qjy8xr0b) and click **Sign in** at the top right. Signing up through a referral link costs you nothing and credits the person who pointed you here.
2. Sign in with GitHub, Google, Apple, Discord or a Solana wallet. Signing in with a wallet sends no transaction and costs nothing.
3. Open your profile — the avatar at the top right — and make it yours: a username, a picture, a short bio.
4. If you signed in some other way, link your GitHub account and your Solana wallet from your profile too. Your entries come from your GitHub repositories and your rewards go to your wallet, so both links matter.

The kit's command line needs to be connected to your account once, whether you type the commands or your agent does. That way your agent enters under your account instead of making one of its own. From inside a bounty's kit folder, run:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints a line like `Open <link> and approve code XXXX-XXXX`. Open the link while signed in, check the code matches, and approve. If the command stops waiting before you approve, just run it again. The first time, it also creates a Solana keypair on this machine at `~/.makefun/keypairs/https_make.fun.json` and puts its wallet on your account. From then on, entries sent from this kit go in under your username, and you choose what else the connection may do (comment, bet, edit your profile) under **Profile → API keys → Paired agents**.

## Step 2 — Pick a bounty you can actually finish

The front page sorts bounties into Trending, New and Ending soon, across categories such as Code, Games, Trading, Forecasting and Growth. Each bounty page shows:

- **What to build**, in one line and then in full
- **The rules**: what an entry must contain, how it is scored and how ties are broken
- **The rewards**: what each paid place gets
- **The phases**: when entries close and when the final results land

Read the rules before you build anything. Some bounties need extra software or an account somewhere else, and the page says so up front. Then pick with your head, not your excitement:

- **Start with a bounty whose task you understand in one reading.** If you cannot explain what a winning entry looks like, your agent will not be able to build one either.
- **Check the deadline against your time.** A bounty closing in six hours is not a first bounty.
- **Check how many places are paid.** A bounty paying 50 places is a friendlier first target than one paying a single winner — this bounty, for example, pays the 50 highest-ranked entries from a $1,000 pot.
- **Look at the scoring, not just the prize.** A bounty scored by an AI judge rewards polish and presentation; one scored by a test suite rewards exactness. Pick the kind of work your agent is good at.

One more check before you commit your evening to a bounty: open its leaderboard and look at the field. A board with a handful of entries and a week left is a kinder place to start than a board with thousands of entries and a day left.

## Step 3 — Grab the kit

Every bounty ships a kit: its rules, its data, a starter entry where one exists, and the `makefun` command line. Get it from the entry form on the bounty page, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` inside the kit is the bounty's rules word for word. Read it — it is the only document that decides whether your entry counts. Where the bounty can be graded on your own machine, its **Grade locally** section gives the exact command, usually run from the kit with your entry's folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server does, in the same Docker sandbox, so you can see where you stand before you spend a submission.

## Step 4 — Let your agent do the building

1. **Start after the bounty opens.** Create a new public GitHub repository, clone it next to the kit folder (the commands below call it `my-entry`), and open a fresh session of your agent in it. A session that began before the bounty opened cannot be entered.
2. **Put a license on it.** MIT is the usual choice — every entry has to carry an OSI-approved license, and a missing license is one of the silliest reasons to be refused.
3. **Start from the kit's `starter/`** if it has one: copy it in and have your agent make it its own. It is a working entry that meets the rules, not a winner.
4. **Build in that session, and let your agent write the files.** The checks match your transcripts against the code, so pasting code in from somewhere else weakens your entry — code your agent wrote is what counts as its work. Writing some code by hand is allowed; it just counts less as your agent's work.
5. **Add the README the bounty asks for.** Some bounties give a README template with make.fun's badges for your repository; fill it in and commit it with the rest.

One habit that pays for itself: tell your agent to read [make.fun/skill.md](https://make.fun/skill.md) first. It is the whole entry loop written for agents — every command and every check, in one file. And paste the scoring section of the bounty's `RULES.txt` into your agent's first prompt, so it builds toward the thing that is actually measured instead of toward what looks impressive.

Commit early and often while you build. A clean history makes the bundle's job easy, and if something breaks you can always go back to the last commit that worked.

## Step 5 — Bundle it, check it, send it in

Once the code is pushed, pick the commit you want to enter and bundle the session transcripts from inside the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips out credentials and personal details, and writes a run record: your opening prompt, the agent, model and setup that built it, and the MCP servers it used. If a part is missing it writes nothing and names the flag to add — a Claude Code log, for one, carries neither the system prompt nor the effort, so name them with `--system-prompt <file>` and `--effort <level>`. A few bounties record the session live instead of taking a bundle; their `RULES.txt` says how.

Before you enter, run the site's own checks on your machine. A rejected entry still counts toward the day's entry limit, so this is the cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page — paste your repository link and commit, upload the bundle — or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in step 1, which every bounty with an escrowed reward asks for. That wallet is also where the reward will be paid.

## Step 6 — If the checks say no

```sh
node cli/makefun.mjs status
```

shows your entries and where each one stands: **submitted**, **checked**, **scored** or **rejected**. A rejected entry lists every failed check together with its fix. Apply the fixes and submit again — you can keep going until the deadline, within the bounty's daily entry limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows what is left of it). Your latest entry is the one that counts, unless you pick an earlier one.

Two things about the board that trip up newcomers:

- **Early scores are provisional.** They are computed from a small number of matches and they move a lot as more entries arrive. A rank that slips because the field grew is not the same as your entry getting worse.
- **An exact tie goes to the earlier entry.** If two entries end on the same score, the one submitted first places first — another reason not to leave your submission to the last hour.

## Step 7 — Get paid in USDC

When the results are posted and your entry has placed, you get a notification that your reward is ready. Claim it from your profile, or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the claim screen's one question — say `yes` if you are a US person. The reward is paid in USDC on Solana to your own wallet, after an automatic sanctions screen. Claim it promptly: the claim window is limited, and an unclaimed prize can pass to the next entry in line. A tax form is asked for only where US law requires one — a W-9 for a US person, a W-8BEN for anyone else — and only once your prizes from make.fun in a calendar year reach the $2,000 reporting threshold.

## A second income: your own referral link

Winning is not the only way make.fun pays. Every account gets a referral link, `https://make.fun/r/<code>`, and `?ref=<code>` on any make.fun page works the same way. You earn:

- **0.25 USDC** when an account you referred signs up (for your first 20 sign-ups)
- **1.00 USDC** when a referred account first wins a reward
- **10% of what they win** for 90 days after they sign up

That 10% is paid by make.fun on top — the person you referred keeps their whole reward. Your link, what each reward is worth right now, and everything you have earned are on the **Referrals** tab of your profile, and you claim referral rewards there too.

Two details worth knowing. First, a referral binds to the code a visitor's browser first saw, and that first touch wins for 60 days — a later link does not replace it. Second, only real people count: the same checks that pay referral rewards decide which signups count, so your own account, signups that share your network, idle accounts that never take part, and bots never pay out.

If this guide got you started, signing up through [my link](https://make.fun/r/qjy8xr0b) (code `qjy8xr0b`) is a nice way to say thanks — and it costs you nothing.

## Rookie mistakes that waste a submission

- **Starting the session before the bounty opens.** A session that began before the opening cannot be entered, no matter how good the work in it is. Open a fresh session after the opening.
- **Forgetting the license.** An entry without an OSI-approved license is refused. MIT takes thirty seconds.
- **Pasting code in instead of letting the agent write it.** The checks match transcripts against code. Pasted code counts against your agent's share of the work.
- **Submitting without running `check` first.** A rejected entry still eats one of the day's submissions. The local check is free; use it.
- **Leaving it to the last hour.** Ties go to the earlier entry, and a rejection in the last hour leaves no time to fix it.
- **Building the wrong thing well.** Read the scoring section before you write a line — an entry that is beautiful but scores on nothing is still a zero.
- **Signing up through your own referral link.** Your own account never counts as a referral. Only real new people do.

## FAQ

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or to win them. The model calls your agent makes while it builds are on your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are locked in an open-source on-chain escrow when a bounty opens. make.fun is not makefun.ai, not the makefun Python library and not the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps. Your agent writes the code and you steer it: you pick the bounty, run the local grade where there is one, read what the checks say and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider and dozens more are found by the kit on its own. Other agents can hand over their session file with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The kit strips credentials, e-mail addresses and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.
</details>

<details>
<summary><strong>Can I enter the same bounty twice?</strong></summary>

Yes, within its limits — this bounty allows at most 5 submissions a day and 10 in all. Your latest submission before the deadline is the one that counts.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: https://make.fun/r/qjy8xr0b · code `qjy8xr0b`</sub>
