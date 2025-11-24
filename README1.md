AWS Interview Questions for a Tech Architecture Role

🧱 1. Core Architecture & Design
1.	Explain the Well-Architected Framework. How do you apply its five (or six) pillars in real architectures?
2.	How do you design a multi-tier architecture on AWS that is scalable, secure, and cost-optimized?
3.	What strategies do you use to design highly available architectures across multiple AZs and multiple regions?
4.	When would you choose monolithic vs microservices architecture on AWS?
5.	How do you design an application to be fault-tolerant against an AZ outage? A regional outage?
6.	Describe how you design for compliance (PCI, HIPAA, GDPR) on AWS.
7.	Explain CAP theorem and how it applies to AWS services.
8.	How do you design for eventual consistency in distributed systems?
________________________________________
☁️ 2. Networking & VPC
1.	Explain the components of a VPC: subnets, route tables, IGW, NAT Gateway, NACLs, SGs.
2.	Difference between Security Groups and NACLs?
3.	How do you architect a hybrid cloud solution with AWS?
4.	What is Transit Gateway, and when would you use it?
5.	How do you design multi-VPC network architecture in an enterprise environment?
6.	Explain PrivateLink vs VPC Peering vs TGW.
7.	Design a secure VPC for a public-facing web app.
________________________________________
🧊 3. Compute (EC2, ECS, EKS, Lambda)
1.	When would you choose EC2 vs Lambda vs ECS vs EKS?
2.	Explain the difference between Fargate and EC2-backed ECS.
3.	How do you design auto-scaling for a stateless service?
4.	What are the best practices for running containers on AWS?
5.	How do you migrate a monolith app into microservices on AWS?
6.	Explain the cold-start problem in Lambda and how to mitigate it.
________________________________________
🗄️ 4. Databases & Storage
1.	Difference between RDS, Aurora, DynamoDB — when to choose each?
2.	Explain DynamoDB partition keys, sort keys, and partitioning.
3.	How do you design read-heavy architecture using caching (ElastiCache, DAX)?
4.	How to ensure cross-region DR for RDS or Aurora?
5.	How does S3 ensure durability (11 nines)?
6.	Explain S3 performance optimization techniques (prefixes, multipart uploads, transfer acceleration).
________________________________________
🔐 5. Security, IAM & Governance
1.	Explain IAM roles vs users vs groups.
2.	What are AWS Organizations and Service Control Policies?
3.	How do you design a multi-account strategy?
4.	Best practices for secrets management (SSM Parameter Store, Secrets Manager, KMS)?
5.	How do you secure APIs in API Gateway?
6.	What is Zero Trust architecture, and how do you apply it on AWS?
________________________________________
♻️ 6. CI/CD, DevOps, & Automation
1.	Explain a CI/CD pipeline on AWS using CodePipeline, CodeBuild, CodeDeploy.
2.	How would you automate infrastructure using Terraform or CloudFormation?
3.	What is a blue/green deployment and how do you implement it on ECS/Lambda/EC2?
4.	Explain canary and traffic-shifting deployments in App Mesh or API Gateway.
5.	How do you design observability using CloudWatch, X-Ray, OpenTelemetry?
________________________________________
📈 7. Scalability & Performance
1.	Explain horizontal vs vertical scaling on AWS.
2.	How do you design for burst traffic?
3.	When to use CloudFront, global accelerator, or multi-region architecture?
4.	How would you reduce latency for global users?
5.	How do you design throttling and rate limiting?
6.	Explain caching at client, edge, and server tiers.
________________________________________
💰 8. Cost Optimization
1.	How do you reduce EC2 costs in large environments?
2.	Explain when to use spot instances vs reserved instances vs savings plans.
3.	How would you optimize DynamoDB costs?
4.	How would you design S3 lifecycle policies for cost efficiency?
5.	Explain CloudWatch costs and how to reduce them.
________________________________________
⚙️ 9. Reliability & Disaster Recovery
1.	Explain RTO and RPO and design an architecture to meet them.
2.	What are the AWS DR strategies (Backup & Restore, Pilot Light, Warm Standby, Multi-Site)?
3.	How do you design a multi-region failover using Route 53?
4.	Explain chaos engineering and how you would apply it.
________________________________________
🛠️ 10. Real System Design Scenarios
You may be asked to design solutions such as:  
  •	Build a global e-commerce platform on AWS.  
  •	Design a real-time streaming analytics system (Kinesis vs Kafka vs MSK).  
  •	Move an on-prem enterprise system to AWS with minimal downtime.  
  •	Architect a serverless event-driven workflow using Lambda + SQS + EventBridge.  
  •	Design a multi-tenant SaaS platform with isolation and cost efficiency.  
