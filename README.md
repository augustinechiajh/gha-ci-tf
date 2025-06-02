# Simple Terraform Reusable Action
This GitHub Action performs Terraform CI checks, including:

- `terraform fmt` (formatting)
- `terraform validate` (syntax and configuration checks)
- `tflint` (Terraform linter)

> Pulls a Docker image running a lightweight Alpine, containing Terraform and TFLint.

## How to run this in your GitHub Actions pipeline

Add the following to your workflow to run CI checks on your Terraform configuration:

```yaml
jobs:
  terraform-ci:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Run Terraform CI checks
        uses: augustinechiajh/gha-ci-tf@main
        with:
          terraform-work-dir: 'iac/tf'  # specify your own directory, iac/tf is default

