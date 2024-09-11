# Cron Job with GitHub Actions

This repository demonstrates how to set up a cron job using GitHub Actions. The job runs every 2 minutes and can also be triggered manually.

## Setup

The cron job is defined in `.github/workflows/cron.yml`.

### Triggers

- **Scheduled**: Runs every 2 minutes using the cron pattern: `*/2 * * * *`.
  - [Learn more about GitHub Actions cron syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#onschedule)
- **Manual**: Can be triggered manually via GitHub using `workflow_dispatch`.
  - [Learn more about manually triggering workflows](https://docs.github.com/en/actions/using-workflows/manually-running-a-workflow)

### Tasks

- **Checkout**: Clones the repository using `actions/checkout@v2`.
  - [Checkout Action Documentation](https://github.com/actions/checkout)
- **Data Synchronization**: Sends a `POST` request to an API using secret values.

## Requirements

### Secrets

Add the following secrets to the repository:
- `CRON_API_TOKEN`
- `CRON_API_URL`
- `CRON_API_PATH`
  - [Managing Secrets in GitHub Actions](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## Manual Run

1. Go to the **Actions** tab.
2. Select the **Run Cron Job** workflow.
3. Click **Run workflow**.
   - [Guide on running workflows manually](https://docs.github.com/en/actions/using-workflows/manually-running-a-workflow)
