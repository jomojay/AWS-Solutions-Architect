# SAA‑Ecommerce‑Portal 🛒☁️

This personal project delivers a low‑latency, highly available, and secure e‑commerce portal for African customers, complete with relational user data storage and image hosting. Built in weeks 2 of my AWS SAA program, it demonstrates cloud architecture best practices under budget constraints.

---

## 🚀 Project Overview

- **Goal:** Design an online storefront that  
  1. Serves pages and images with minimal latency  
  2. Persists user profiles and order history in a secure relational store  
  3. Scales automatically, with built‑in fault tolerance  
  4. Encrypts data at rest and in transit, with strict access controls  
  5. Implements monitoring, logging, and cost optimization  

---

## 🧱 Architecture Diagram
<div align="center">
  <img src="./assets/e-commerce-1.png" alt="Architectural Diagram for an e-commerce portal
" />
</div>
![Architecture Diagram](architecture-diagram.png)

_Key components_  
1. **Edge CDN (CloudFront):** Caches static assets (product images, CSS, JS) at POPs across Africa.  
2. **API Gateway + Lambda:** Serverless front door for dynamic requests; scales on demand, zero server management.  
3. **Aurora Serverless (MySQL):** Auto‑scaling relational database for user profiles and orders.  
4. **S3 + CloudFront:** Versioned, encrypted buckets for product images, behind a secure CDN.  
5. **WAF & Shield:** Protect against DDoS and OWASP Top 10 web exploits.  
6. **VPC + Private Subnets:** Lambdas and RDS live in private subnets, with NAT for outbound updates.  
7. **Cognito:** User authentication and fine‑grained IAM access.  
8. **CloudWatch & X‑Ray:** Real‑time metrics, centralized logs, and distributed tracing for performance tuning.  
9. **Cost Controls:** Budget alarms, rightsizing recommendations, and reserved concurrency caps. :contentReference[oaicite:1]{index=1}  

---

## 🛠️ Implementation Highlights

| Concern          | Solution                                         | Benefit                   |
|------------------|--------------------------------------------------|---------------------------|
| **Latency**      | CloudFront at regional edge locations            | < 100 ms page loads       |
| **Availability** | Aurora Serverless + multi‑AZ deployment          | 99.99% uptime             |
| **Scalability**  | API Gateway + Lambda on demand                   | Instant auto‑scaling      |
| **Security**     | TLS Everywhere, KMS‑encrypted S3 & RDS volumes   | Data fully encrypted      |
| **Access Control**| Cognito for auth + IAM roles for service access | Least‑privilege enforced  |
| **Monitoring**   | CloudWatch metrics + X‑Ray tracing               | Proactive issue spotting  |
| **Cost**         | Auto‑pause Aurora, reserved concurrency caps     | Cost predictability       |

---

## 🔒 Security & Compliance

- **Encryption at Rest:** AWS KMS‑managed keys for RDS and S3.  
- **Encryption in Transit:** TLS 1.2+ enforced via CloudFront and API Gateway.  
- **Web Protection:** AWS WAF ruleset + Shield Advanced for DDoS protection.  
- **IAM Best Practices:** Role‑based access, no root usage, MFA enforced.  

---

## 📈 Observability

- **Dashboards:** CloudWatch custom dashboards for latency, error rates, and cost.  
- **Logs:** Centralized application logs in CloudWatch Logs, with retention policies.  
- **Tracing:** AWS X‑Ray to pinpoint bottlenecks in Lambda invocations.  

---

## 💡 Next Steps

- Add CI/CD (CodePipeline) for automated Terraform deployments  
- Implement WebSocket notifications via API Gateway  
- Integrate a GraphQL layer for richer frontend interactions  
- Explore multi‑region failover for disaster recovery  

---

## 🙋 About Our Squad

Part of the SAA Squad Project 1—an AWS architecture challenge to design cost‑effective, fault‑tolerant solutions under real‑world constraints. Reach out if you’d like to collaborate or give feedback!


