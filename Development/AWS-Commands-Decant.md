# AWS Commands - Decant Group

Quick reference for AWS ECS commands used in Decant Group projects.

## AWS SSO Portal
🔗 https://d-93675b1b68.awsapps.com/start#/

---

## Production Environment

### Login
```bash
aws sso login --profile prod
```

### ECS Execute Command
```bash
aws ecs execute-command \
    --profile prod \
    --region eu-west-1 \
    --cluster wp-prod-inventory-ecs-cluster \
    --task <TASK_ID> \
    --container inventory \
    --command "/bin/bash" --interactive
```

**Notes:**
- Cluster: `wp-prod-inventory-ecs-cluster`
- Region: `eu-west-1`
- Container: `inventory`

---

## Staging Environment

### Login
```bash
aws sso login --profile staging
```

### ECS Execute Command
```bash
aws ecs execute-command \
    --profile staging \
    --region eu-west-1 \
    --cluster wp-staging-inventory-ecs-cluster \
    --task <TASK_ID> \
    --container inventory \
    --command "/bin/bash" --interactive
```

**Notes:**
- Cluster: `wp-staging-inventory-ecs-cluster`
- Region: `eu-west-1`
- Container: `inventory`

---

## Tips
- Replace `<TASK_ID>` with actual task ID from ECS console
- Make sure you're logged in to the correct profile before running commands
- Use AWS Console to find task IDs if needed

---
*Last updated: October 7, 2025*
