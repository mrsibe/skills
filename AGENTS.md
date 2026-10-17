# Repository instructions

## Scope

This is a personal, cross-agent Skills library, not an Agent framework.
The repository currently contains the paper-reading skill. Do not add new skills,
example skills, or placeholder SKILL.md files unless explicitly requested.

## Layout

- `skills/<skill-name>/SKILL.md`: future skill entry points, one level deep.
- `tests/<skill-name>/`: future trigger cases, evaluation inputs and regressions.
- `CONTRIBUTING.md`: authoring and validation conventions.

Read `CONTRIBUTING.md` before adding or changing a skill. Keep reusable methods
separate from project-specific configuration. Add optional directories and
runtime dependencies only when required.

## Validation and safety

There is currently no automated test runner, build command or CI. Manual regression
cases and their execution protocol are in tests/paper-reading/README.md. Do not
invent commands or treat unexecuted cases as passed. Distinguish static validation
from model behavior, effectiveness and cross-client testing.

Never execute bundled scripts without inspecting them. Do not add secrets,
private business data, global installations, or unrelated tooling. Commits,
remote creation, pushes and releases require an explicit request.

Keep user-facing documentation in Chinese unless requested otherwise.
