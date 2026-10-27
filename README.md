# kyle-chalmers: Claude Code plugin marketplace

> **New catalog:** Discover portable skills and the data workflow suites in [kyle-chalmers-skills](https://github.com/kyle-chalmers/kyle-chalmers-skills). This marketplace keeps its existing `kyle-chalmers` identifier for compatibility. Existing suite installation commands continue to work.

One `marketplace add` for the whole family of data-discipline plugins:

```
/plugin marketplace add kyle-chalmers/claude-plugins
/plugin install ticketwright@kyle-chalmers
/plugin install jobwright@kyle-chalmers
/plugin install streamsnow@kyle-chalmers
/plugin install healwright@kyle-chalmers
/plugin install ai-data-security@kyle-chalmers
/plugin install kyle-chalmers-skills@kyle-chalmers
```

Install only the ones you need. Each plugin still lives (and can be installed from) its own repo;
this marketplace saves you adding a separate marketplace for each one. Check each plugin's README
for its runtime requirements and for project-scope install commands.

## The family: complementary, not overlapping

| Plugin | Governs | Front door |
|---|---|---|
| [ticketwright](https://github.com/kyle-chalmers/ticketwright) | Ticket-driven analysis work: prior-art recall, QC review pyramid, ship gates | `/ticket` |
| [jobwright](https://github.com/kyle-chalmers/jobwright) | The orchestration jobs themselves: catalog, compliance, drift-checked deploys | `/start-job` |
| [streamsnow](https://github.com/kyle-chalmers/streamsnow) | Streamlit-in-Snowflake apps: scaffold, validate, review, gated ship | `/build-app` |
| [healwright](https://github.com/kyle-chalmers/healwright) | Failed data jobs: audit, a healer you own, in-job failure triggers, guarded AI fix PRs (Databricks today) | `/self-healing-audit` |
| [ai-data-security](https://github.com/kyle-chalmers/ai-data-security) | What your AI tooling can see and touch: secrets, configs, data tiers, DB grants | `/ai-data-security:security-audit` |
| [kyle-chalmers-skills](https://github.com/kyle-chalmers/kyle-chalmers-skills) | Portable coding workflows: session handoffs, reviews, workflow design, meeting-to-ticket drafts | Six skills, e.g. `/kyle-chalmers-skills:next-session-prompt` |

The hand-offs are deliberate: ticketwright's "pause before any prod job deploy" is jobwright's
`/safe-deploy`; a dashboard a ticket produces ships through streamsnow; when a job jobwright
shipped fails in production, healwright classifies it and routes code bugs to a draft fix PR a
human merges; ai-data-security audits the access all of them rely on.

The data suites share the same design system: one front door per plugin, short setup steps,
config-driven portability (no tool names in skills), and deterministic script verdicts the model
narrates. The ones that ship hooks (ticketwright, jobwright, streamsnow) keep them mechanical and
fail-open, have them announce themselves, and explain them in a hook transparency section of
their README.

MIT licensed, like the plugins. See [LICENSE](LICENSE).
