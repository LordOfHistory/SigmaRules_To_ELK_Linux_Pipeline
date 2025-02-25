# Linux SigmaRules import in Kibana Security

This repository contains a pipeline to import linux sigma rules into kibana security. The log ingestion in ELK must be done through the [auditd manager integration](https://www.elastic.co/guide/en/integrations/current/auditd_manager.html) available in elastic.

To configure the integration is recomended to follow this [guide](https://www.elastic.co/security-labs/linux-detection-engineering-with-auditd).

## Using the pipeline

If your scenario is as proposed, to import the rules you only need to get the [sigma cli tool](https://github.com/SigmaHQ/sigma-cli), the [sigma rules](https://github.com/SigmaHQ/sigma/releases) and the pipeline.

Once installed and working, you can execute the command:

```bash
sigma convert --target lucene -p ecs_windows -p linux-pipeline.yml --format siem_rule_ndjson ./rules/linux > linux-rules.ndjson
```

This will generate a ndjson that you can directly use in kibana security.

😸 Good luck and happy threat hunt. 😄
