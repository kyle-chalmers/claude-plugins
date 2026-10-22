# kyle-chalmers — Claude Code plugin marketplace

> **New catalog:** Discover portable skills and the data workflow suites in [kyle-chalmers-skills](https://github.com/kyle-chalmers/kyle-chalmers-skills). This marketplace keeps its existing `kyle-chalmers` identifier for compatibility. Existing suite installation commands continue to work.

One `marketplace add` for the whole family of data-discipline plugins:

```
/plugin marketplace add kyle-chalmers/claude-plugins
/plugin install ticketwright@kyle-chalmers
/plugin install jobwright@kyle-chalmers
/plugin install streamsnow@kyle-chalmers
/plugin install ai-data-security@kyle-chalmers
```

Each plugin still lives (and can be installed from) its own repo; this marketplace just
removes three of the four `marketplace add` commands.

## The family — complementary, not overlapping

| Plugin | Governs | Front door |
|---|---|---|
| [ticketwright](https://github.com/kyle-chalmers/ticketwright) | Ticket-driven analysis work: prior-art recall, QC review pyramid, ship gates | `/ticket` |
| [jobwright](https://github.com/kyle-chalmers/jobwright) | The orchestration jobs themselves: catalog, compliance, drift-checked deploys | `/start-job` |
| [streamsnow](https://github.com/kyle-chalmers/streamsnow) | Streamlit-in-Snowflake apps: scaffold, validate, review, gated ship | `/start-app` |
| [ai-data-security](https://github.com/kyle-chalmers/ai-data-security) | What your AI tooling can see and touch: secrets, configs, data tiers, DB grants | `/ai-data-security:security-audit` |

The hand-offs are deliberate: ticketwright's "pause before any prod job deploy" is jobwright's
`/safe-deploy`; a dashboard a ticket produces ships through streamsnow; ai-data-security audits
the access all three rely on.

All four share the same design system: one front door per plugin, ≤5-question setup wizards,
config-driven portability (no tool names in skills), mechanical fail-open guard hooks that
announce themselves, deterministic script verdicts the model narrates, and hook transparency
sections in every README.

MIT licensed, like the plugins.
