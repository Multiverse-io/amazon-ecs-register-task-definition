# Amazon ECS Register Task Definition — Repo-Specific BugBot Rules

> Org-wide rules are enforced via Cursor Team Rules.

## Purpose

- This is a fork of the AWS `amazon-ecs-deploy-task-definition` GitHub Action. It registers ECS task definitions and deploys to ECS services. Changes here affect deployment pipelines across the org.

## Build & Distribution

- The action entry point is `index.js` and the bundled output is in `dist/`. After modifying `index.js`, rebuild the dist bundle before committing. The `dist/` directory must be committed since GitHub Actions run from it directly.
- The action interface is defined in `action.yml`. Changes to inputs/outputs are breaking changes for all consuming workflows.

## Testing

- Tests are in `index.test.js`. Run tests before committing changes to the action logic.

## Security

- This action handles AWS credentials and ECS deployments. Do not log or expose AWS credentials, task definition secrets, or container environment variables in action output.
