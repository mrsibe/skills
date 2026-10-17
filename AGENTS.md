# Repository instructions

## Scope

This is a personal, cross-agent Skills library, not an Agent framework.
See README.md for the current skill list. Do not add new skills, example skills,
or placeholder SKILL.md files unless explicitly requested.

## Layout

- `skills/<skill-name>/SKILL.md`: skill entry points, one level deep.
- `CONTRIBUTING.md`: authoring and validation conventions.

Read `CONTRIBUTING.md` before adding or changing a skill. Keep reusable methods
separate from project-specific configuration. Add optional directories and
runtime dependencies only when required. Keep the README skill list up to date
and use Skills CLI for installation instructions instead of client path tables.

## Validation and safety

There is no test module, automated test runner, build command or CI. Do not add
test infrastructure unless explicitly requested. Validate skill metadata and local
links when appropriate, and report only checks that were actually performed.

Never execute bundled scripts without inspecting them. Do not add secrets,
private business data, global installations, or unrelated tooling. Commits,
remote creation, pushes and releases require an explicit request.

Keep user-facing documentation in Chinese unless requested otherwise.
