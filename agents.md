from pathlib import Path



agents = r"""# AGENTS.md



## Project overview



This repository contains a software application developed as part of a school project.



Before making changes:



1. Read the task description completely.

2. Identify the affected files and modules.

3. Search for existing implementations before creating new ones.

4. Review existing tests related to the feature.

5. Prefer consistency with the existing architecture over introducing new patterns.



Critical areas:



- Authentication and authorization logic

- Database schema and migrations

- API contracts and public interfaces

- Configuration files

- CI/CD configuration

- Security-related code



Do not modify critical areas unless the task explicitly requires it.



---



## Development commands



Replace commands below with project-specific commands if needed.



- Install dependencies: `npm install`

- Start development server: `npm run dev`

- Run tests: `npm test`

- Run linting: `npm run lint`

- Run type checking: `npm run typecheck`

- Build project: `npm run build`

- Format code: `npm run format`



---



## Code style



- Follow the existing code style.

- Use strict typing whenever possible.

- Do not use `any` without a documented reason.

- Keep functions focused on a single responsibility.

- Reuse existing helpers instead of duplicating logic.

- Follow the current folder structure.

- Do not introduce new architectural patterns without approval.

- Prefer readability over clever solutions.

- Keep changes as small as possible.



---



## Testing rules



- Every new feature must include tests.

- Every bug fix must include a regression test.

- A regression test must fail before the fix and pass after the fix.

- Never remove tests without explaining why.

- Update tests when requirements change.

- Verify edge cases and error handling.

- Do not claim a bug is fixed without evidence from tests.

- Run all relevant tests before marking work complete.



Required quality checks before completion:



- Tests

- Linting

- Type checking

- Build verification



If any check fails, the task is not complete.



---



## Git workflow



- Never commit directly to `main`.

- Never push directly to `main`.

- Create or use a feature branch for every task.

- Keep pull requests small and focused.

- One pull request should solve one problem.

- Explain all modified files in the final summary.

- Do not merge code that fails tests, linting, type checking, or build validation.



Recommended repository protections:



- Branch protection enabled on `main`

- Required pull request review

- Required CI status checks

- Required passing tests before merge



---



## Scope control



- Only modify files directly related to the task.

- Do not perform unrelated refactoring.

- Do not rename files, APIs, routes, database fields, or components unless required.

- Do not delete code without justification.

- Do not rewrite working functionality to "improve" it unless requested.

- If a change affects more than 5 files, explain why before proceeding.

- Prefer the smallest safe solution.



---



## Security rules



- Never commit secrets.

- Never commit passwords.

- Never commit API keys or tokens.

- Never expose private credentials.

- Never disable authentication to make tests pass.

- Never disable authorization checks.

- Validate all user input.

- Avoid logging sensitive user information.

- Follow least-privilege principles.



---



## Dependency rules



- Prefer existing dependencies.

- Check whether functionality already exists before adding a package.

- Do not add production dependencies without justification.

- Explain why a dependency is required.

- Avoid unnecessary upgrades.

- Review dependency security implications before adding packages.



---



## Before modifying critical systems



Request confirmation before:



- Database schema changes

- Database migrations

- Authentication changes

- Authorization changes

- Public API changes

- Dependency additions

- Dependency removals

- File deletions

- Security-sensitive changes

- Large-scale refactoring



---



## Completion checklist



Before declaring work complete:



- [ ] Requirements reviewed

- [ ] Changed files reviewed

- [ ] No unrelated files modified

- [ ] Tests executed successfully

- [ ] Regression tests added when fixing bugs

- [ ] Linting passed

- [ ] Type checking passed

- [ ] Build passed

- [ ] No secrets added

- [ ] Documentation updated if necessary

- [ ] Summary of changes prepared



---



## When unsure



- Ask for clarification.

- Do not guess requirements.

- Propose a short implementation plan.

- Explain risks before making major changes.

- If a bug cannot be reproduced, state that clearly.

- If a failing test cannot be explained, stop and report the issue.

- Prefer asking questions over making assumptions.

"""



plan = r"""# AI_QUALITY_PLAN.md



## Chosen AI Rules File



I chose `AGENTS.md` because it is supported by OpenAI Codex and can also be used as a repository-wide instruction file for multiple coding assistants.



## Sources Used



1. OpenAI Codex documentation about AGENTS.md

2. AGENTS.md standard documentation

3. Anthropic Claude Code documentation

4. GitHub documentation about branch protection and pull requests

5. GitHub documentation about required status checks and CI



## Main Risks When Using AI



- Breaking existing functionality

- Introducing regressions

- Making excessive changes

- Modifying architecture without justification

- Skipping validation steps

- Adding insecure code

- Adding unnecessary dependencies



## How The Rules Prevent Broken Code Reaching Main



The rules require:



- feature branches

- pull requests

- regression testing

- linting

- build validation

- type checking

- code review



This creates multiple quality gates before code can reach `main`.



## Required Successful Commands



The following commands must succeed before completion:



- npm test

- npm run lint

- npm run typecheck

- npm run build



Replace with actual project commands if different.



## How Existing Functionality Is Protected



- Regression tests are required for bug fixes.

- Existing tests may not be removed without justification.

- Unrelated refactoring is prohibited.

- Scope is limited to task-related files.

- Critical changes require approval.



## Technical Protections Required



The following require technical enforcement:



- Branch protection

- Required pull request reviews

- CI pipeline

- Required status checks

- Automated test execution



## Evidence



Example acceptable evidence:



- GitHub Actions screenshot

- CI pipeline result

- Terminal output showing successful tests

- Build success output



## Self-Assessment



The most useful rule is the requirement for regression tests because it directly prevents old bugs from returning.



A remaining risk is that AI can still misunderstand requirements even when tests pass.



In a future version I would add project-specific architecture rules and automated security scanning.



The file is intentionally specific, measurable, and verifiable rather than relying on vague instructions such as "write good code."

"""



base = Path("/mnt/data")

(base/"AGENTS.md").write_text(agents, encoding="utf-8")

(base/"AI_QUALITY_PLAN.md").write_text(plan, encoding="utf-8")



print(str(base/"AGENTS.md"))

print(str(base/"AI_QUALITY_PLAN.md"))