build-lists: true
theme: Next, 1
autoscale: true

[.footer: #### Igor Karpovich]

## It's all about microservices
### Engineering challenges of running Docker Swarm

---

# Disclaimer

## Neither whales nor gophers were harmed

---
# The Goal

Decrease time to market, increase engineering speed and and product quality.

Increase number of engineers involved, improve cross-team communication.

Decrease number of incidents, improve incident resolution time.

---

# The Way

Disposable products:
- Immutable infrastructure
- Containers
- Microservices

---
# The WHY

- Experiment fast and safe
- Be happy to make mistakes and learn
- See anomalies and improvements at scale

---

![](base.png)

# Version Zero
## First microservice (2015)

- REST API only
- Monitoring coverage
- Plugged into core app
- Traditional deployment
- Written in PHP

---

![](swarm.jpg)

# Swarm
## Out of the box

- Service discovery
- Networking (mesh routing and custom networks)
- Volumes (EBS/EFS in AWS)
- Orchestration with Compose
- Configs, secrets

---

![](swarm.jpg)

# Swarm
## Missing bits

- Job runner
- Cron scheduler
- Autoscaling
- Access control
- Monitoring
- Request tracing

---

# How do we do the rest?

---

![](docker.jpg)

# Docker API!

```go
import "github.com/docker/docker/client"

func main() {
  client, err := client.NewClientWithOpts(client.FromEnv)
  stack := DeployStack(client, ymlPath)
  PollStackTasks(stack)
}

```

---

![right](goblin.png)

# Goblin

## Microservice framework

---

## Some of Goblin's features

- Runtime (module) management
- Config management
- Storage & Cache
- Transport (HTTP Server/Client, WS router)
- Monitoring client and metrics (Gin, WS router, go runtime)
- Logging (context data injection, sentry integration)
- Healthchecks
- Tracing

^ Mention SDK

---

![right](healthchecks.png)

# Healthchecks as metrics

- Docker native support
- Expose metrics
- Push to InfluxDB
- Visualisation

---

![](jaeger.png)

# Distributed tracing
## Trace everything!
- HTTP/WS Server
- HTTP Client
- SQL
- NoSQL
- MQ
- Events
- Emails

---

# Platform toolkit

- Clusters self-deployment (traefik, CI, monitoring, logging, tracing)
- GitOps
- Secret management
- Service wide event broadcast
- SSO, identity management (ACL, JWT, SAML)
- Scheduler
- Job runner
- Change Audit
- Multi-route email delivery
- Monitoring (InfluxDB, Grafana, Slack, TV dashboards)

---

# Questions!

[.footer: #### Twitter: @ikarpovich]
