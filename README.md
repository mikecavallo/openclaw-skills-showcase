# OpenClaw skills I use (curated)

A small, curated set of third-party [OpenClaw](https://clawhub.ai) skills that I install in my
agent workspace. **I did not write any of the code or documentation in this repository.** Each
skill is an unmodified copy installed from the ClawHub registry, kept here with its original
author credit so I can reference the exact versions I run.

Each skill folder contains an `ATTRIBUTION.md` with the author, source, license and the result of
a file-by-file comparison against the upstream release.

## Skills

| Skill | Version | Author | Source | License | Local changes |
| --- | --- | --- | --- | --- | --- |
| [agent-orchestrator](agent-orchestrator/) | 0.1.0 | aatmaan1 | [ClawHub](https://clawhub.ai/aatmaan1/skills/agent-orchestrator) | None stated | None |
| [elite-longterm-memory](elite-longterm-memory/) | 1.2.2 | NextFrontierBuilds | [GitHub](https://github.com/NextFrontierBuilds/elite-longterm-memory) | MIT (declared) | None |
| [agent-autonomy-kit](agent-autonomy-kit/) | 1.0.0 | Ryan Campbell / Team Reflectt | [GitHub](https://github.com/reflectt/agent-autonomy-kit) | MIT (declared) | None |

### agent-orchestrator

A prompt-only skill (Markdown, no code) that tells an agent how to break a large task into
subtasks, write a short `SKILL.md` for each sub-agent, coordinate them through an
inbox/outbox/status file protocol, then merge the results and clean up. The `references/` folder
holds the communication protocol and sub-agent templates.

### elite-longterm-memory

A memory playbook for agents: a write-ahead "session state" file, a curated `MEMORY.md`, daily
logs, optional LanceDB vector search and optional Mem0 or cloud backup. It ships a small Node CLI
(`bin/elite-memory.js`) that creates the template files and reports their status. The vector
search features expect the OpenClaw `memory-lancedb` plugin and an `OPENAI_API_KEY`.

### agent-autonomy-kit

Guidance and templates for keeping an agent working between prompts: a task queue
(`templates/QUEUE.md`), a heartbeat routine that pulls from the queue
(`templates/HEARTBEAT.md`), and example `openclaw cron` jobs for scheduled work. This copy matches
upstream commit `07560dd`; newer upstream versions add queue-checking scripts that are not
included here.

## Installing

Install from the original authors rather than from this repo, so you get their latest versions
and license terms:

```bash
# ClawHub (each slug has more than one publisher, so specify the owner)
# agent-orchestrator    -> @aatmaan1/agent-orchestrator
# elite-longterm-memory -> @nextfrontierbuilds/elite-longterm-memory
# agent-autonomy-kit    -> @ryancampbell/agent-autonomy-kit

# Or from GitHub / npm
git clone https://github.com/reflectt/agent-autonomy-kit.git skills/agent-autonomy-kit
npx elite-longterm-memory init
```

## Original work

None. This repository contains no original code or documentation by me apart from this README
and the `ATTRIBUTION.md` files.

## Licenses

Each skill remains under its author's terms; see the table above and each folder's
`ATTRIBUTION.md`. `agent-orchestrator` has no stated license, so all rights stay with its author.
Nothing in this repository is relicensed by me.

## Contact

Mike Cavallo, [Business Runs Better](https://businessrunsbetter.com), hello@businessrunsbetter.com
