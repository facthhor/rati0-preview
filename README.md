<p align="center"><img src="art/banner.svg" alt="rati0 — the harness made for local AI" width="100%"></p>

**rati0** is the harness made for local AI, in the making. Every big
harness is built around a cloud API, and many of them are better than rati0
in plenty of ways. rati0 is built around the computer on your desk
instead. It was built and tested on one laptop, by local models, for local
models, and most of what it does exists so that a small model does real
work in tight memory. API access exists, but it isn't the focus.

It's a desktop app wrapped around
[pi](https://www.npmjs.com/package/@earendil-works/pi-coding-agent), a
local model, and an agent you give a name. This repository holds only the
idea and some pictures. The code and the app become public with the beta.

<p align="center"><img src="art/progress.svg" alt="36% of the way to the public beta" width="100%"></p>

<p align="center"><img src="art/hero.svg" alt="rati0's empty chat: sessions in the sidebar, the mark beside the greeting, the composer" width="100%"></p>
<p align="center"><sub>The empty chat, drawn from rati0's design language.</sub></p>

## The idea

- **Local first.** rati0 is for the model you own, not one you rent. The
  model runs on the same machine, and nothing leaves it unless you let it.
- **Made for small models in tight memory.** Contexts are saved and never
  read twice, new chats start hot, every token counts, and the model never
  fights a build for the RAM.
- **A tool, not a companion.** The agent knows your machine and your
  projects, plans them on a board, and helps you design, create and code.
  It doesn't talk for the sake of talking. Everything it does is there to
  get your projects and your day done.
- **Projects first, chat second.** A project is a folder with a board. It
  starts with a *phase 0* where the agent learns what the project is and
  writes the plan. Every session after that builds on the plan.
- **Built on pi.** rati0 doesn't write its own agent. Every session is a
  real pi agent, and everything that decides (permissions, tools, model
  moves) is a pi extension. rati0 is the harness around it: memory,
  boards, safety and the interface.
- **rati0 builds rati0.** Most of rati0 is written by its developer's own
  agent, running inside rati0. When the code goes public, anyone can write
  an extension or push an improvement, and their agent can code it for
  them.

## Small models, tight memory

These are the parts that make a laptop model do real work. The numbers are
from the dev machine (a Ryzen AI Max+ 395 with 32 GB, llama.cpp, a 27B
model).

- **Hot starts.** A new chat begins from a pre-baked head (tools, prompt,
  memory, the project's documents). The first reply comes in 7 s instead of
  157.
- **Contexts that survive.** Switching away saves a conversation's model
  state to disk, and coming back restores it in seconds instead of
  re-reading it for half an hour. The sidebar shows which chats are live,
  saved or cold.
- **Every token counts.** A head is read once and reused, a saved context
  is never read again, and the model gets the plan and memory up front
  instead of searching for them.
- **model_yield.** Before a build, the model saves its context and
  unloads. The build gets the RAM to itself, then the model reloads and
  restores.
- **RAM in check.** The shell's memory cap follows what is really free, and
  when you're away the model saves and unloads.

## Things it does

- **Boards as plans.** Every project folder has a plan drawn as a board,
  with owners, progress marks and the sessions that worked on each card.
- **A safety net.** The agent's shell runs in a sandbox with no network by
  default. Every turn is checkpointed and can be rewound. What a session
  may do lives in one small policy file.
- **A screen of its own.** The agent gets its own desktop session and
  browser to work in, and asks before anything could send data out.
- **Senses.** Vision on every model, and listening through a small speech
  model.
- **Made to be yours.** Seven colorways, and the app knows whether you're
  at the desk, studying or away and behaves accordingly. There's a study
  tree that grows with the hours.

## The look

rati0 has its own design language: a warm near-black ground, one red, soft
shapes for what you touch, square slightly tilted blocks for what the
machine emits, and a spiral of triangles as its mark.

<p align="center"><img src="art/marks.svg" alt="The mark's four states: idle, processing, thinking, writing" width="100%"></p>

It comes in seven colorways:

<p align="center"><img src="art/colorways.svg" alt="Seven colorways: ember, obsidian, shallows, thermal, glacier, bloom, relic" width="100%"></p>

## Where it's going

- **Alpha:** the core above, tested on real projects.
- **Reshape:** the codebase gets reshaped into clean modules.
- **Features:** the current feature list, finished.
- **Autopilot:** an auto mode where the agent works through its board with
  a supervisor watching, web search behind a strict gate, new models, and a
  new UI.
- **The intelligence hub:** image, video and audio generation and design
  abilities, all local and sized to your machine.
- **Beta:** Windows, macOS and Linux. **The code and the app go
  public here**, open to extensions and pull requests.

The percentage above is an estimate of the way to the beta. It gets
updated as the work lands.

---

<sub>rati0 is a personal project by <a href="https://github.com/facthhor">@facthhor</a>. Nothing to install yet.</sub>
