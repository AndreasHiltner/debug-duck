# Debug Duck 🦆

A [Hermes Agent](https://hermes-agent.nousresearch.com/docs) skill that turns the agent into a talking rubber duck: a patient, slightly sarcastic listener who guides you to your own debugging insight.

**The duck never fixes the bug. The duck makes you fix the bug.**

## Why

Explaining a problem out loud forces you to re-examine your own assumptions — that's the whole trick behind rubber duck debugging. A duck that talks back works even better — but only if it resists the urge to fix. This skill encodes that discipline: listen, mirror, ask one Socratic question at a time, and let the user reach the Eureka moment themselves.

## What it does

- **Listen → Mirror → Guide → Eureka** protocol
- **Socratic question patterns** for common stuck situations (vague symptom, "this should work", unverified assumption, wrong value, regression, wrong mental model, going in circles)
- **4-level hint ladder** for when the user is genuinely stuck
- **Assumption tracking** — the wrong assumption is the actual lesson, the bug is just the symptom
- **Privacy-first session logging** — logs go to `~/.hermes/cache/scratch/` (user-private, 24h auto-prune), `chmod 600`, with secret redaction before every write
- **Exit conditions** — clean handling for "found it but won't fix", "it's not a bug", and session resumption
- **Safety guardrails** — no coaching for harmful *or dual-use* goals, no secrets in logs, a bounded 2-level roast scale
- **Handoffs** to `systematic-debugging` (root-cause verification) and `test-driven-development` (regression tests)

## Install

```bash
mkdir -p ~/.hermes/skills/software-development
cp SKILL.md ~/.hermes/skills/software-development/debug-duck/SKILL.md
```

The skill loads automatically when the user is stuck and wants to talk it through.

## Usage

```
User: "My cron job doesn't run and I'm stuck."
Duck: "Go on — I'm not interrupting."
User: "It worked last week, now the log is empty..."
Duck: "So it worked last week, and now the log is empty. Did I get that right?"
...
User: "Oh. The config file moved. That's it."
Duck: "Quack. Now — want a regression test for that?"
```

## License

MIT — see [LICENSE](LICENSE).
