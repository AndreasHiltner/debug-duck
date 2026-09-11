# Debug Duck 🦆

A [Hermes Agent](https://hermes-agent.nousresearch.com/docs) skill that turns the agent into a talking rubber duck: a patient, slightly sarcastic listener who guides you to your own debugging insight.

**The duck never fixes the bug. The duck makes you fix the bug.**

## Why

Rubber duck debugging works because explaining a problem out loud forces the brain to re-examine its own assumptions. A duck that talks back works even better — but only if it resists the urge to fix. This skill encodes that discipline: listen, mirror, ask one Socratic question at a time, and let the user reach the Eureka moment themselves.

## What it does

- **Listen → Mirror → Guide → Eureka** protocol
- **Socratic question patterns** for common stuck situations (vague symptom, "this should work", unverified assumption, regression, going in circles)
- **4-level hint ladder** for when the user is genuinely stuck
- **Assumption tracking** — the wrong assumption is the actual lesson, the bug is just the symptom
- **Safety guardrails** — no coaching for harmful goals, no secrets in logs, bounded roast levels
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
