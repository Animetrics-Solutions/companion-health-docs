Infrastructure & Deployment — Companion Health
Classification: INTERNAL — CONFIDENTIAL
Version: v2.0
Status: Production-Aligned Draft

⸻

1. ROLE IN SYSTEM

This layer defines:
	•	How the system runs in production
	•	How services scale
	•	How reliability is ensured
	•	How partners securely access the platform

This directly impacts:
	•	System uptime
	•	Data integrity
	•	Partner trust
	•	Enterprise readiness

⸻

2. DEPLOYMENT PHILOSOPHY

The system must evolve through three stages:

Stage 1 — Local / MVP
Stage 2 — Cloud Single Region
Stage 3 — Multi-Region Scaled

⸻

2.1 Core Principles
	•	Stateless compute
	•	Event-driven ingestion
	•	Isolated tenancy
	•	Horizontal scalability

⸻

3. INFRASTRUCTURE ARCHITECTURE

3.1 High-Level Infra Flow

Client / Data Source
→ API Gateway
→ Ingestion Service
→ Message Queue (Pub/Sub)
→ Processing Workers
→ Signal Engine
→ Risk Models
→ Fetch API
→ External Consumers

⸻

3.2 Core Components

API Gateway

Role:
	•	Entry point
	•	Authentication
	•	Rate limiting

⸻

Ingestion Service

Role:
	•	Accept incoming data
	•	Validate schema
	•	Push to queue

⸻

Message Queue (Critical)

Recommended:
	•	GCP Pub/Sub
	•	AWS SQS + SNS

⸻

Purpose:
	•	Decouple ingestion from processing
	•	Handle bursts
	•	Improve reliability

⸻

Processing Workers

Role:
	•	Consume messages
	•	Normalize data
	•	Generate signals

⸻

Model Service

Role:
	•	Run CKD model
	•	Return risk scores

⸻

Fetch API Service

Role:
	•	Expose intelligence externally

⸻

Data Stores

Telemetry → TimescaleDB / Bigtable
Metadata → PostgreSQL
Cache → Redis

⸻

4. ENVIRONMENT SETUP

4.1 Environments

Development
	•	Local machine
	•	Minimal infra

Staging
	•	Full system
	•	Testing environment

Production
	•	Scaled system
	•	Live data

⸻

4.2 Environment Rules
	•	No direct production testing
	•	Separate databases per environment
	•	Config-driven deployments

⸻

5. CONTAINERIZATION

5.1 Standard
	•	Docker for all services

⸻

5.2 Service Containers
	•	API service
	•	Worker service
	•	Model service

⸻

5.3 Benefits
	•	Consistent environments
	•	Easy deployment
	•	Scalability

⸻

6. ORCHESTRATION

6.1 Recommended
	•	Kubernetes (future)
	•	Docker Compose (initial)

⸻

6.2 Scaling Model
	•	Scale API horizontally
	•	Scale workers based on queue load

⸻

7. CI/CD PIPELINE

7.1 Flow

Code Push
→ Build
→ Test
→ Deploy

⸻

7.2 Requirements
	•	Automated testing
	•	Version control
	•	Rollback capability

⸻

8. SECURITY ARCHITECTURE

8.1 Authentication
	•	API keys
	•	JWT tokens

⸻

8.2 Data Security
	•	Encryption in transit (HTTPS)
	•	Encryption at rest

⸻

8.3 Multi-Tenant Security
	•	tenant_id enforcement
	•	Query isolation

⸻

8.4 Secrets Management
	•	Use secure vaults
	•	No hardcoded credentials

⸻

9. OBSERVABILITY & MONITORING

9.1 Logging
	•	Request logs
	•	Error logs
	•	System logs

⸻

9.2 Metrics
	•	API latency
	•	Error rates
	•	Throughput

⸻

9.3 Tracing
	•	End-to-end request tracking
	•	OpenTelemetry recommended

⸻

10. RELIABILITY ENGINEERING

10.1 Failure Modes
	•	Data ingestion failure
	•	API downtime
	•	Model errors

⸻

10.2 Mitigation
	•	Retry logic
	•	Dead Letter Queues
	•	Fallback responses

⸻

10.3 Uptime Goal
	•	MVP: 95%
	•	Production: 99.9%

⸻

11. SCALING STRATEGY

11.1 Horizontal Scaling
	•	Add more API instances
	•	Add more workers

⸻

11.2 Data Scaling
	•	Partition telemetry data
	•	Optimize time-series queries

⸻

11.3 Future
	•	Multi-region deployment
	•	Edge processing (IoT)

⸻

12. COST OPTIMIZATION

12.1 Principles
	•	Start minimal
	•	Scale on demand

⸻

12.2 Strategies
	•	Serverless ingestion (future)
	•	Auto-scaling workers

⸻

13. BACKUP & RECOVERY

13.1 Backup
	•	Regular DB snapshots

⸻

13.2 Recovery
	•	Restore from snapshot
	•	Replay ingestion logs

⸻

14. DEPLOYMENT CHECKLIST

Before production:
	•	API tested
	•	Data validated
	•	Security configured
	•	Monitoring active
