# Agent Directives & Workflow Rules

### Execution Rules
1. **Planning First:** Always present a clear architectural or implementation plan before making file changes or running scaffolding commands. Never write code until the user explicitly approves the plan.
2. **Incremental Execution:** Implement features one component or endpoint at a time. After completing a unit of work, pause and request confirmation before moving to the next item.
3. **Automated Git Commits:**
   - Once a task or feature slice is verified, create a clean Git commit.
   - Use conventional commit messages (e.g., `feat(backend): add certifications resource`, `feat(frontend): create timeline component`).
   - Do not bundle multiple unrelated features into a single commit.

### Stack & Architecture
- **Backend:** Quarkus (Java), standard REST endpoints, OpenAPI/Swagger UI, clean service/repository layer.
- **Frontend:** Angular (latest standalone components, TypeScript, responsive layout).
- **Structure:** Monorepo with two subdirectories:
  - `/backend` (Quarkus service)
  - `/frontend` (Angular application)

### Git & Branching Strategy
1. **Feature Branches:**
   - Every significant milestone or feature slice must have its own branch off `main`.
   - Branch naming format: `feature/<feature-name>` (e.g., `feature/projects-showcase`, `feature/studies-education`).
2. **Branch Workflow:**
   - Before writing code for a feature, ensure working tree is clean, switch to `main`, and run `git checkout -b feature/<feature-name>`.
   - Implement the feature incrementally with logical commits on that branch.
   - Do NOT merge back into `main` automatically.
3. **Completion & Review:**
   - When the feature is complete and verified, stop and notify the user.
   - Wait for approval before merging into `main` (via `git checkout main && git merge feature/<feature-name>`) or deleting the feature branch.