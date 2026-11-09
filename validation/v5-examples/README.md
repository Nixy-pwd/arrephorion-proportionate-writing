# v5 — matched with/without examples for the README

Purpose: give each README example case the same form as the Hume case: same configuration, same source and task, with and without the full skill (v0.3). Planned for ChatGPT work mode; all runs were made in Codex (Sol 6.1, high), so the Gate control pairs with the existing Codex v0.3 skill run. Fresh session per file, nothing else pasted; first run is the one used.

| File | Case | Condition | Pairs with |
|---|---|---|---|
| `gate-control.md` | Linux VM gate record | without skill | existing Codex skill run, `../v2-case/run-v0.3-codex-raw.md` |
| `pm2s-control.md` | PM2S audit (B1 facts, prompt verbatim) | without skill | `pm2s-skill.md` |
| `pm2s-skill.md` | PM2S audit | with skill v0.3 | `pm2s-control.md` |

These runs supply README examples, not a new evaluation. Examples are chosen to illustrate the defensive-writing definition and the guard; any errors found in the skill outputs will be shown too.

Runs: `run-gate-control-codex-raw.md`; `run-pm2s-control-codex-raw.md` (answered in Chinese, then English); `run-pm2s-skill-codex-zh-raw.md` (run 1, Chinese) and `run-pm2s-skill-codex-en-raw.md` (run 2, English). The prompt set no language. The English README quotes the English outputs, the Chinese README the Chinese ones.
