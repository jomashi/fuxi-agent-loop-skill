# Security Policy / 安全说明

## Reporting a Vulnerability

If you discover a security issue in this project, please do not publish sensitive details in a public issue.

Open a GitHub issue with a minimal non-sensitive description, or contact the maintainer through the repository owner profile.

## Scope

This policy covers:

- `SKILL.md`;
- documentation files;
- installation guidance;
- examples and test prompts.

## Out of Scope

- Third-party agent platforms that consume this skill;
- user-created automations;
- private workflows or local configuration;
- credentials, API keys, or secrets stored outside this repository.

## Security Best Practices

- Do not put private workflow data, passwords, API keys, or local paths into public prompts.
- Run one manual loop turn before scheduling recurring automation.
- Stop before deletion, billing, credential, account, or irreversible actions.
- Treat generated handoffs as instructions that still require verification.