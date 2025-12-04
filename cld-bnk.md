💡 **Key Points for Banking Projects**

**Hybrid architecture:** Use ECS/EKS for core services, Lambda for event-driven workflows (fraud detection, notifications).

**Container images:** All microservices are stored in ECR and pulled securely by ECS/EKS.

**Event-driven decoupling:** SQS/SNS/EventBridge ensures scalability and loose coupling between services.

**Data security:** Enforce encryption, IAM policies, and VPC isolation for sensitive financial data.

**Observability:** Logs, metrics, and tracing are mandatory for compliance and incident response.


