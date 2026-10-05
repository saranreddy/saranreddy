# Saran Alla

Platform / MLOps engineer focused on AWS.

I build reliable data and ML platforms with **Terraform**, **SageMaker**, and **Kafka** (including multi-region disaster recovery), and I care about the boring parts that make systems trustworthy: IaC, pipelines, CI, and clear runbooks.

## Public work

The AWS starters below are GitHub Templates: click "Use this template", apply to your own AWS account, and destroy when done.

### MLOps on SageMaker
From a first pipeline to a shared platform for many teams.

- **[sagemaker-mlops-pipeline-starter](https://github.com/saranreddy/sagemaker-mlops-pipeline-starter)** — download-and-apply SageMaker Pipelines starter (process → train → evaluate → register → deploy), with Terraform bootstrap and a full “run against your AWS account” guide. GitHub Template.
- **[sagemaker-model-monitor-starter](https://github.com/saranreddy/sagemaker-model-monitor-starter)** — companion to the MLOps pipeline starter: SageMaker Model Monitor data-quality baselines + monitoring schedules, Terraform + CLIs. GitHub Template — delete endpoints/schedules when done.
- **[sagemaker-multi-team-platform-starter](https://github.com/saranreddy/sagemaker-multi-team-platform-starter)** — scale SageMaker from a few data scientists to dozens without growing the platform team: one Terraform entry onboards a team (Studio profiles, ABAC-isolated role, S3/ECR/model registry, instance allowlist), with per-team Budgets, an idle-resource reaper, and endpoint alarms routed to the owning team. GitHub Template — near-zero idle cost; destroy when done.

### Streaming and event-driven
Kafka and serverless messaging on AWS.

- **[aws-msk-kafka-starter](https://github.com/saranreddy/aws-msk-kafka-starter)** — download-and-apply Amazon MSK (Serverless) starter: Terraform VPC + cluster, Python producer/consumer with IAM auth. GitHub Template — destroy when done; NAT/MSK costs add up if left up.
- **[aws-eventbridge-lambda-sqs-starter](https://github.com/saranreddy/aws-eventbridge-lambda-sqs-starter)** — download-and-apply EventBridge + Lambda + SQS starter: custom bus → Lambda → SQS/DLQ for durable failures, Terraform + demo CLIs. GitHub Template — pennies for a short demo; destroy when done.
- **[kafka-dr-confluent-aws](https://github.com/saranreddy/kafka-dr-confluent-aws)** — active-passive Kafka disaster recovery on Confluent Cloud (AWS) with Cluster Linking: Terraform, Python producer/consumer apps on ECS Fargate, scripted failover/failback and drill runner, an MM2 comparison, and CI (Terraform validate, unit tests, shellcheck, Docker builds, Trivy scan).

### Terraform foundations
How a team runs Terraform safely across environments.

- **[aws-terraform-remote-state-starter](https://github.com/saranreddy/aws-terraform-remote-state-starter)** — Terraform the team way: S3 remote state with DynamoDB locking, dev/stage/prod environments sharing one module, and GitHub Actions plan-on-PR / apply-on-merge via OIDC with per-environment least-privilege roles. GitHub Template — pennies per month.

### AI agents
Multi-agent systems that take software work from issue to production.

- **[pr-to-prod-agents](https://github.com/saranreddy/pr-to-prod-agents)** — PR-to-Production agent team: label a GitHub issue `agent:build` and a LangGraph supervisor runs planner, coder, reviewer, tester, deployer, and reporter agents through a human approval gate, a staging deploy with health-check rollback, and a final report on the issue. Per-agent least-privilege permissions with an audit log, sandboxed code execution, and 51 passing tests. Runs end to end locally with mocked GitHub and LLM calls; Bedrock, webhook intake, and the AWS CDK deploy are the next milestones.
- **[mini-debug-assist](https://github.com/saranreddy/mini-debug-assist)** — download-and-deploy mini Uber Debug Assist: a CloudWatch alarm wakes a LangGraph agent on Bedrock (Claude Sonnet 5.5 / Opus 5.5) that runs parallel root-cause subagents over MCP tools (CloudWatch Logs, X-Ray, GitHub, AppConfig), test-validates a fix, and opens a PR for human review. CDK deploy, local mock mode, one-command teardown.

## In progress

Being built in the open now. Expect rough edges until each one is marked stable.

- **[aws-rag-quality-gate-starter](https://github.com/saranreddy/aws-rag-quality-gate-starter)** — download-and-apply RAG starter: document Q&A with citations on Bedrock + Aurora pgvector, with an automated evaluation quality gate that blocks deploys when answer quality drops. Terraform.
- **[aws-cdc-lakehouse-starter](https://github.com/saranreddy/aws-cdc-lakehouse-starter)** — change data capture from RDS Postgres through Debezium on MSK Connect and MSK Serverless into Iceberg tables on S3 (Glue), queried with Athena. Terraform, smoke test, honest teardown.
- **[sagemaker-self-service-training-starter](https://github.com/saranreddy/sagemaker-self-service-training-starter)** — "bring your train.py": self-service SageMaker training for many data scientists, via a small CLI and one shared, tested pipeline template. Plugs into the multi-team platform starter.
- **Atlas** — engineering intelligence platform (private). TypeScript product work alongside the AWS platform craft above.

## Private work

Not public, so no links here.

- **kafka-dr-aws-native** — private, archived repo: the same Kafka DR pattern as kafka-dr-confluent-aws on an AWS-native stack (Amazon MSK in two regions with MSK Replicator, Glue Schema Registry, ECS Fargate apps, DynamoDB and CloudWatch, with failover/failback scripts and CI).

## Currently

Shipping public, clone-and-run AWS starters that show how I work in production — not toy demos. Working on Kafka and MLOps platform engineering: multi-region Kafka DR patterns on AWS.

## Get in touch

Open to engagements, consulting, and questions about any of these projects. Email me at **[saranreddy2002@gmail.com](mailto:saranreddy2002@gmail.com)**.
