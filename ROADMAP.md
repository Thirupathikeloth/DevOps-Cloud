# 100-Day DevOps, Cloud & Platform Engineering Roadmap

**Start:** Thursday, 8 October 2026. **End:** Friday, 15 January 2027.
**Level:** absolute beginner. I have never typed a Linux or Git command.
**Time:** 3 hours a day.
**Computer:** HP Omen, Windows, 16 GB RAM, 1 TB storage.

## Daily structure (3 hours)

| Part | Time | What happens |
|---|---|---|
| 1. Learn | 60 min | Concepts in simple English. Every new term: what it is, why we use it, how it works, where companies use it, a real-world example |
| 2. Guided hands-on | 70 min | One or two commands at a time, each explained. I run them and report back before we continue |
| 3. Independent practice | 35 min | A task I solve myself. No answer given straight away |
| 4. Review | 15 min | 3–5 questions, common mistakes, key commands, interview points, summary |

**Weekly review days** (every 7th day) work differently:
- They still teach new material, but less of it.
- About 1 hour goes to the review itself: a mini assessment, a troubleshooting challenge and interview questions on topics already learned.

## Starting from zero

- No command is used before it has been explained: what it does, what each part means, what the output should look like, and how to check it worked.
- New words are explained the first time they appear, using everyday comparisons.
- If something is unclear, we stay on it until it makes sense. A day is only "done" when I understand it and have finished the practice.

## Legend
- ⚠️ = AWS lab that may use credits. Cost warning before, cleanup after.
- 🔐 = security focus
- 🛠️ = troubleshooting scenario
- 🎯 = interview questions
- 📦 = adds a piece to the final project

## Time per area

| Area | Days | Dates |
|---|---|---|
| Computer basics & setup | 1–2 | 8–9 Oct |
| **Networking (deep)** | 3–13 (11 days) | 10–20 Oct |
| **Linux** | 14–29 (16 days) | 21 Oct – 5 Nov |
| Git & GitHub | 30–34 (5 days) | 6–10 Nov |
| Bash & Python automation | 35–40 (6 days) | 11–16 Nov |
| **AWS (deep)** | 41–59 (19 days) | 17 Nov – 5 Dec |
| **Docker (deep), incl. ECS on AWS** | 60–68 (9 days) | 6–14 Dec |
| Terraform & Ansible | 69–74 (6 days) | 15–20 Dec |
| CI/CD & DevSecOps | 75–79 (5 days) | 21–25 Dec |
| **Kubernetes, Helm & EKS** | 80–89 (10 days) | 26 Dec – 4 Jan |
| Observability | 90–92 (3 days) | 5–7 Jan |
| GitOps & Platform Engineering | 93–95 (3 days) | 8–10 Jan |
| Final project & assessment | 96–100 (5 days) | 11–15 Jan |

**The final project is built step by step.** Its GitHub repo is created on Day 34. Each phase adds its piece:

| Phase | What it adds |
|---|---|
| Scripting | Automation scripts |
| AWS | Architecture design |
| Docker | Container images |
| Terraform | Infrastructure as code |
| CI/CD | Pipelines |
| Kubernetes | Helm chart |
| Observability | Monitoring |
| GitOps | Argo CD |

Days 96–100 put the pieces together, harden, document and assess them.

## The full plan

### Phase 0: Starting from zero

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **1** | Thu 8 Oct | Computer basics & your first commands | Computer parts (CPU, RAM, storage), operating system, programs, files, folders, GUI vs terminal, what a command is, client & server, what a network and the internet are | Open PowerShell, read the prompt, first commands: `hostname`, `whoami`, `ipconfig`, `ping` | First commands typed |
| **2** | Fri 9 Oct | Setting up a DevOps workstation | What WSL2 is (Linux inside Windows), what a code editor is, what Git is (in one sentence), how your home internet works (modem, router, ISP) | Install Windows Terminal, WSL2 + Ubuntu, VS Code, Git. Check GitHub login. Trace the path: laptop → router → ISP | Tools installed |

### Phase 1: Networking in depth

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **3** | Sat 10 Oct | Network building blocks | OSI 7 layers vs TCP/IP 4 layers, MAC addresses, switches vs routers, ARP, frames vs packets | `ipconfig /all`, `arp -a`, find your MAC and gateway, look at your router's admin page (read only) | Layer diagram in your own words |
| **4** | Sun 11 Oct | IPv4 addressing | Binary basics, IPv4 structure, public vs private ranges (10/8, 172.16/12, 192.168/16), loopback, APIPA, IPv6 basics | Binary ↔ decimal drills, find private vs public IP, `ping 127.0.0.1`, see WSL2's own IP (a real NAT example) | — |
| **5** | Mon 12 Oct | Subnet masks & CIDR | Network vs host part, masks, `/8 /16 /24 /28`, network & broadcast address, usable hosts | 20 subnet calculation exercises (by hand, then checked with a calculator tool) | Subnetting cheat sheet |
| **6** | Tue 13 Oct | Subnet design | Splitting one network into many, planning for growth, why AWS reserves 5 IPs per subnet | Design an IP plan for a company: offices, servers, public/private zones | IP plan document |
| **7** | Wed 14 Oct | Wireshark: see packets for real + **Weekly review 1** | How packet capture works, capture filters, reading a packet layer by layer | Capture and read ARP and ping (ICMP) packets | 🎯 Networking Qs, 🛠️ "Can't reach the internet" |
| **8** | Thu 15 Oct | DNS in depth & DHCP | Resolver → root → TLD → authoritative, A/AAAA/CNAME/MX/TXT/NS records, TTL, caching, hosts file, DHCP "DORA" process | `nslookup`, `Resolve-DnsName`, `dig`, `ipconfig /displaydns /flushdns`, capture a DNS query in Wireshark | 🛠️ "DNS not resolving" |
| **9** | Fri 16 Oct | Transport layer: ports, TCP & UDP | Ports & sockets, well-known ports, TCP 3-way handshake, TCP vs UDP, connection states | `netstat -ano`, `Test-NetConnection -Port`, `ss -tulpn`, capture a TCP handshake | Port cheat sheet |
| **10** | Sat 17 Oct | HTTP, HTTPS & TLS | HTTP methods, status codes, headers, cookies, REST APIs, TLS handshake, certificates & CAs | `curl -v`, browser DevTools Network tab, inspect a site's certificate, call a public API | — |
| **11** | Sun 18 Oct | Routing, NAT, firewalls & VPN 🔐 | Routing tables, default gateway, hops, NAT/PAT, stateful vs stateless firewalls, VPN basics | `route print`, `ip route`, `tracert`/`traceroute`, look at Windows Firewall rules | Diagram: how one web request travels |
| **12** | Mon 19 Oct | Load balancers, proxies & CDN | L4 vs L7 load balancing, algorithms, health checks, forward vs reverse proxy, CDN & caching | Draw a production web architecture, follow a request through a CDN (response headers) | Architecture diagram #1 |
| **13** | Tue 20 Oct | SSH basics & network troubleshooting | How SSH encrypts a session, a layer-by-layer troubleshooting method, the network troubleshooting toolkit | 🛠️ "Website is down", 🛠️ "Slow website": investigate step by step | ✅ Networking foundations complete |

### Phase 2: Linux

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **14** | Wed 21 Oct | Linux introduction + **Weekly review 2** | Kernel, shell, distributions, file system layout (`/etc /var /home`), how to read any command (command, options, arguments), `man`, `--help` | `pwd`, `ls`, `cd`, explore the file system | 🎯 Networking Qs |
| **15** | Thu 22 Oct | Files & directories | Absolute vs relative paths, hidden files, wildcards | `mkdir`, `touch`, `cp`, `mv`, `rm`, build a fake company folder tree | — |
| **16** | Fri 23 Oct | Viewing & searching | Pipes `\|`, redirects `> >> 2>`, stdin/stdout/stderr | `cat`, `less`, `head`, `tail -f`, `grep`, `find` on sample logs | — |
| **17** | Sat 24 Oct | Text processing & editors | nano and vim basics, filters, archives | `sort`, `uniq`, `cut`, `wc`, `awk`, `sed`, `tar`, `gzip` | Log report one-liners |
| **18** | Sun 25 Oct | Users, groups & sudo 🔐 | root vs normal users, `/etc/passwd`, `/etc/group`, sudoers | `useradd`, `usermod`, `passwd`, `groups`, `su`, `sudo` | — |
| **19** | Mon 26 Oct | Permissions 🔐 | rwx, numeric modes, ownership, umask, setuid/setgid/sticky bit, least privilege | `chmod`, `chown`, lock down team folders | — |
| **20** | Tue 27 Oct | Processes, CPU & memory | PIDs, parent/child, signals, foreground/background, load average, swap | `ps`, `top`, `htop`, `kill`, `nice`, `free`, `uptime` | 🛠️ "CPU at 100%" |
| **21** | Wed 28 Oct | Mini lab + **Weekly review 3** | Putting days 14–20 together | Multi-user server: users, groups, permissions, process checks | 🎯 Linux Qs |
| **22** | Thu 29 Oct | Packages & systemd | apt, repositories, systemd units, service lifecycle, enable at boot | Install nginx, `systemctl start/stop/enable/status`, write a simple unit file | — |
| **23** | Fri 30 Oct | Environment variables & shell config 🔐 | `env`, `export`, `PATH`, `.bashrc`, aliases, why secrets never go in code | Customize your shell, set and use variables safely | — |
| **24** | Sat 31 Oct | Linux networking (networking revisited) | Linux network tools, `/etc/hosts`, `/etc/resolv.conf`, nginx as reverse proxy & load balancer | `ip`, `ss`, `dig`, `curl`, `tcpdump`, nginx proxying to 2 backend apps | Reverse proxy lab |
| **25** | Sun 1 Nov | SSH in depth 🔐 | Key pairs, `known_hosts`, `~/.ssh/config`, file transfer, tunnels, hardening | `ssh-keygen`, run an SSH server, `scp`, `rsync`, disable password login | — |
| **26** | Mon 2 Nov | Logs | `/var/log`, journald, log levels, log rotation | `journalctl -u`, `logrotate`, 🛠️ "nginx won't start" | — |
| **27** | Tue 3 Nov | Disk, storage & cron | Partitions, filesystems, mounts, inodes, cron syntax | `df`, `du`, `lsblk`, `mount`, `crontab -e`, scheduled backup | 🛠️ "Disk is full" |
| **28** | Wed 4 Nov | Linux security + **Weekly review 4** 🔐 | Updates, `ufw`, fail2ban, audit basics | Harden your server | 🎯 Linux Qs |
| **29** | Thu 5 Nov | Linux troubleshooting lab | A step-by-step server troubleshooting method, writing technical documentation | Mixed 🛠️ scenarios, finish and document the lab | ✅ **Project 1: Linux server administration lab** |

### Phase 3: Git & GitHub

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **30** | Fri 6 Nov | Version control & Git basics | What version control is, repository, working area → staging → commit, how Git stores history | `git config`, `init`, `status`, `add`, `commit`, `log`, `diff` | — |
| **31** | Sat 7 Nov | Branches & history | Branches, HEAD, merging, fast-forward, undoing changes safely | `switch`, `merge`, `restore`, `revert`, `reset` (safely) | — |
| **32** | Sun 8 Nov | GitHub & remotes 🔐 | Remotes, SSH authentication, clone/push/pull/fetch | SSH keys for GitHub, push Project 1 | Project 1 on GitHub |
| **33** | Mon 9 Nov | Pull requests, conflicts & .gitignore 🔐 | PR workflow, code review, protected branches, conflicts, what to do if a secret leaks | Open and review a PR, create and resolve a conflict, `.gitignore` | 🛠️ "I committed a secret" |
| **34** | Tue 10 Nov | Git workflows & portfolio | GitHub Flow, GitFlow, trunk-based development, commit messages, tags & releases | Portfolio README, create the final project repo | 📦 Final project repo created |

### Phase 4: Bash & Python automation

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **35** | Wed 11 Nov | Bash basics + **Weekly review 5** | Shebang, variables, quoting, arguments, exit codes | System info report script | 🎯 Git Qs |
| **36** | Thu 12 Nov | Bash conditions & loops | `if`, `[[ ]]`, `for`, `while`, `case` | Service checker script | — |
| **37** | Fri 13 Nov | Bash functions & error handling | Functions, `set -euo pipefail`, `trap`, logging | Health-check script run by cron | 📦 Mini-project: health checker |
| **38** | Sat 14 Nov | Python basics for automation | Virtual environments, `pip`, data types, lists/dicts, loops, functions | Small automation exercises | — |
| **39** | Sun 15 Nov | Python: files, errors & env vars 🔐 | File I/O, `try/except`, `os`, `subprocess`, `logging`, env variables | Log analyzer script | — |
| **40** | Mon 16 Nov | Python: APIs & JSON | REST APIs, JSON, `requests`, intro to `boto3` (AWS from Python) | GitHub API report generator | 📦 Mini-project: API automation |

### Phase 5: AWS in depth

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **41** | Tue 17 Nov | Cloud concepts & AWS account 🔐 | IaaS/PaaS/SaaS, Regions, AZs, edge locations, shared responsibility, pricing models, the Free plan | Create your account on the **Free plan** (6 months, $100 credits up to $200), root MFA, budgets, credit alerts | Safe AWS account |
| **42** | Wed 18 Nov | IAM part 1 🔐 + **Weekly review 6** | Users, groups, policies, reading policy JSON | Admin user, groups, custom read-only policy, stop using root | 🎯 Scripting Qs |
| **43** | Thu 19 Nov | IAM part 2 + AWS CLI 🔐 | Roles, STS, temporary credentials, IAM Identity Center, Access Analyzer | Configure the AWS CLI with short-lived credentials | — |
| **44** | Fri 20 Nov | EC2 ⚠️ | AMIs, instance types, key pairs, user data, instance metadata | Launch, SSH in, bootstrap nginx with user data, clean up | — |
| **45** | Sat 21 Nov | EBS, Security Groups & Elastic IP ⚠️ | Volume types, snapshots, stateful firewall rules, EIP cost | Attach and mount a volume, snapshot it, tighten security group rules | — |
| **46** | Sun 22 Nov | S3 🔐 | Buckets, objects, versioning, lifecycle, encryption, bucket policies, Block Public Access | Static website on S3, versioning lab | — |
| **47** | Mon 23 Nov | VPC part 1 ⚠️ | VPC, public/private subnets, route tables, Internet Gateway | Build a 2-AZ VPC by hand using your Day 6 IP plan | — |
| **48** | Tue 24 Nov | VPC part 2 ⚠️ | NAT Gateway (cost!), NACLs vs Security Groups, SSM Session Manager | Private server reaches the internet through NAT (short lab), access it without SSH | 🛠️ "Server can't reach the internet" |
| **49** | Wed 25 Nov | VPC part 3 + **Weekly review 7** ⚠️ | VPC endpoints, VPC peering, flow logs, Reachability Analyzer, Transit Gateway & Site-to-Site VPN (concepts) | Peer two VPCs, read flow logs, debug a blocked connection | 🎯 Networking & AWS Qs |
| **50** | Thu 26 Nov | Host a website on AWS ⚠️ | Putting EC2 + VPC + S3 together | Website on EC2 in your VPC + static assets on S3 | ✅ **Project 2: Host a website on AWS**, 🛠️ "EC2 unreachable" |
| **51** | Fri 27 Nov | Load balancers ⚠️ | ALB vs NLB, listeners, target groups, health checks | ALB in front of 2 EC2 servers in 2 AZs | — |
| **52** | Sat 28 Nov | Auto Scaling & high availability ⚠️ | Launch templates, ASG, scaling policies, multi-AZ design | Auto-scaled web tier, stress test it, watch it scale | — |
| **53** | Sun 29 Nov | Route 53 & certificates ⚠️ | Hosted zones, routing policies, health checks, ACM certificates | DNS records for your app (domain optional), HTTPS on the ALB | — |
| **54** | Mon 30 Nov | RDS ⚠️ | Managed databases, Multi-AZ, read replicas, backups, subnet groups | Private RDS reached from EC2 only | 🛠️ "App can't connect to the database" |
| **55** | Tue 1 Dec | CloudWatch, CloudTrail & EventBridge | Metrics, logs, alarms, dashboards, audit trail, event rules | CPU alarm + email (SNS), find who did what in CloudTrail | — |
| **56** | Wed 2 Dec | Secrets & encryption 🔐 + **Weekly review 8** | Secrets Manager vs SSM Parameter Store, KMS, encryption at rest & in transit | App reads the database password from SSM, never from code | 🎯 AWS Qs |
| **57** | Thu 3 Dec | Lambda & serverless basics | Serverless, Lambda, triggers, API Gateway, event-driven automation | Lambda that stops forgotten EC2 instances on a schedule (saves money) | 📦 Cost-saver automation |
| **58** | Fri 4 Dec | Cost, backup & DR | Cost Explorer, tags, RPO/RTO, AWS Backup, DR strategies, Well-Architected Framework | Cost review, backup plan, tag everything | — |
| **59** | Sat 5 Dec | 3-tier architecture ⚠️ | Production-style design | ALB + ASG + private RDS + monitoring, then full cleanup | ✅ Project 2 upgraded to high availability, 📦 architecture design |

### Phase 6: Docker in depth

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **60** | Sun 6 Dec | Containers | Containers vs VMs, namespaces & cgroups (simply), Docker engine, image vs container | Install Docker, `run`, `ps -a`, `logs`, `exec`, `stop`, `rm` | — |
| **61** | Mon 7 Dec | Images & Dockerfiles | Layers, build cache, FROM/RUN/COPY/CMD | Containerize a Python web app | — |
| **62** | Tue 8 Dec | Dockerfile best practices | CMD vs ENTRYPOINT, `.dockerignore`, multi-stage builds, small base images | Shrink your image size, compare before/after | — |
| **63** | Wed 9 Dec | Registries + **Weekly review 9** | Docker Hub, Amazon ECR, tags, versioning, immutable tags | Push to Docker Hub and ECR | 🎯 AWS Qs |
| **64** | Thu 10 Dec | Volumes & storage | Volumes vs bind mounts, data persistence | Database container whose data survives restarts | — |
| **65** | Fri 11 Dec | Docker networking (networking revisited) | Bridge, host and none networks, container DNS, port mapping | App + database talking over a custom network | 🛠️ "Container can't reach the database" |
| **66** | Sat 12 Dec | Docker Compose | Multi-service apps, `.env` files, healthchecks, `depends_on` | Web + database + cache stack | — |
| **67** | Sun 13 Dec | Container security & troubleshooting 🔐 | Non-root users, minimal images, Trivy scanning, exit codes, OOM kills | Scan and fix your image, 🛠️ "Container keeps restarting" | ✅ **Project 3: Dockerize an application**, 📦 app images |
| **68** | Mon 14 Dec | Containers on AWS: ECS & Fargate ⚠️ | ECS clusters, task definitions, services, Fargate, ECS vs EKS | Run your image on Fargate behind an ALB, then clean up | — |

### Phase 7: Infrastructure as Code

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **69** | Tue 15 Dec | Terraform basics ⚠️ | What IaC is, HCL syntax, providers, resources, `init/plan/apply/destroy` | S3 bucket + EC2 with Terraform | — |
| **70** | Wed 16 Dec | Variables, outputs & state + **Weekly review 10** | Variables, `tfvars`, locals, outputs, data sources, what the state file is | Parameterize your config | 🎯 Docker Qs |
| **71** | Thu 17 Dec | Remote state & modules ⚠️ | S3 backend, state locking, writing and using modules | Move state to S3, write a VPC module | — |
| **72** | Fri 18 Dec | Terraform AWS build ⚠️ | Building a full environment | VPC + ALB + ASG + RDS with modules | ✅ **Project 4: AWS infrastructure with Terraform**, 📦 infrastructure |
| **73** | Sat 19 Dec | Terraform security & troubleshooting 🔐 | Secrets & state, `tflint`, `checkov`, environments (dev/prod) | 🛠️ "Terraform apply failed": fix broken configs | — |
| **74** | Sun 20 Dec | Ansible | Configuration management, inventory, playbooks, roles, idempotency | Configure Terraform-built servers with Ansible | — |

### Phase 8: CI/CD & DevSecOps

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **75** | Mon 21 Dec | CI/CD + GitHub Actions basics | CI vs Continuous Delivery vs Continuous Deployment, pipelines, artifacts, workflows, runners | Lint + test workflow | — |
| **76** | Tue 22 Dec | GitHub Actions full pipeline 🔐 | Docker builds in CI, GitHub secrets, OIDC to AWS (no stored keys) | Code → Build → Test → Image → ECR → Deploy | ✅ **Project 6: GitHub Actions pipeline**, 📦 CI |
| **77** | Wed 23 Dec | Jenkins basics + **Weekly review 11** | Controller, agents, jobs, plugins | Jenkins in Docker, first job | 🎯 Terraform Qs |
| **78** | Thu 24 Dec | Jenkins pipelines | Declarative `Jenkinsfile`, stages, credentials store | Pipeline that deploys to an EC2 Docker host | ✅ **Project 5: Jenkins CI/CD pipeline** |
| **79** | Fri 25 Dec | DevSecOps 🔐 | Secret scanning (gitleaks), dependency scanning, SAST, image scanning, branch protection | Add security gates, 🛠️ "Pipeline failed" | — |

### Phase 9: Kubernetes

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **80** | Sat 26 Dec | Kubernetes architecture | Cluster, control plane, worker nodes, API server, etcd, scheduler, kubelet | Local cluster with kind, explore it with `kubectl` | — |
| **81** | Sun 27 Dec | Pods & YAML | YAML syntax, the Pod spec explained line by line | Run, inspect and debug Pods | — |
| **82** | Mon 28 Dec | Deployments & ReplicaSets | Desired state, rolling updates, rollbacks | Deploy, update and roll back your app | — |
| **83** | Tue 29 Dec | Services, networking & Ingress | ClusterIP/NodePort/LoadBalancer, cluster DNS, Ingress controller | Expose your app through Ingress | — |
| **84** | Wed 30 Dec | Config, Secrets, namespaces & storage 🔐 + **Weekly review 12** | ConfigMaps, Secrets, namespaces, PV/PVC, StorageClasses | App + database with persistent storage | 🎯 CI/CD Qs |
| **85** | Thu 31 Dec | Health checks, resources & scaling | Liveness/readiness/startup probes, requests/limits, HPA | Add probes and limits, autoscale under load | — |
| **86** | Fri 1 Jan | Kubernetes security 🔐 | RBAC, service accounts, NetworkPolicies, Pod Security Standards | Restrict who can do what, block pod-to-pod traffic | — |
| **87** | Sat 2 Jan | Kubernetes troubleshooting lab | A step-by-step way to investigate a cluster | 🛠️ CrashLoopBackOff, ImagePullBackOff, Pending, OOMKilled, Service has no endpoints | ✅ **Project 7: Deploy an app to Kubernetes** |
| **88** | Sun 3 Jan | Helm | Charts, values, templates, releases, upgrades, rollbacks | Helm chart for your app | 📦 Helm chart |
| **89** | Mon 4 Jan | Amazon EKS ⚠️ | Managed Kubernetes, node groups, IAM for pods, EKS costs | EKS with Terraform, deploy, destroy the same day | — |

### Phase 10: Observability

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **90** | Tue 5 Jan | Monitoring & Prometheus | Monitoring vs observability, metrics, Prometheus, exporters, PromQL basics | kube-prometheus-stack with Helm | — |
| **91** | Wed 6 Jan | Grafana & alerting + **Weekly review 13** | Dashboards, alert rules, SLIs/SLOs/error budgets | App + infrastructure dashboards, alerts | ✅ **Project 8: Prometheus & Grafana**, 📦 monitoring, 🎯 Kubernetes Qs |
| **92** | Thu 7 Jan | Logging & tracing | Central logging (Loki, CloudWatch Logs Insights), tracing & OpenTelemetry basics | 🛠️ "High CPU", 🛠️ "Slow app": investigate using metrics, logs and traces | — |

### Phase 11: GitOps & Platform Engineering

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **93** | Fri 8 Jan | GitOps & Argo CD | GitOps principles, Argo CD, sync, drift detection, self-heal | Deploy your Helm chart through Argo CD | ✅ **Project 9: GitOps with Argo CD**, 📦 GitOps |
| **94** | Sat 9 Jan | GitOps in practice 🔐 | Dev/prod environments, promotion through Git, rollback through Git, secrets in GitOps (External Secrets) | Promote a release from dev to prod with a pull request | — |
| **95** | Sun 10 Jan | Platform Engineering | DevOps vs Platform Engineering, internal developer platforms, developer experience, golden paths, self-service, Backstage, how the different roles work together | Build a golden-path template that creates a new service | — |

### Phase 12: Final project

| Day | Date | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|---|
| **96** | Mon 11 Jan | Final: architecture & infrastructure ⚠️ | Production-style design, cost plan | Architecture diagram, Terraform for VPC + EKS + ECR | — |
| **97** | Tue 12 Jan | Final: CI + GitOps CD ⚠️ | End-to-end delivery flow | GitHub → Actions → ECR → Helm values → Argo CD → app on EKS | — |
| **98** | Wed 13 Jan | Final: observability & security 🔐 + **Weekly review 14** | Production readiness checklist | Prometheus/Grafana, alerts, RBAC, network policies, secrets, scanning | 🎯 Full-stack scenario Qs |
| **99** | Thu 14 Jan | Final: documentation & cleanup | Writing for recruiters and engineers | README, architecture diagram, troubleshooting log, security notes, resume bullets, full AWS cleanup | ✅ **Final project complete** |
| **100** | Fri 15 Jan | Final assessment | Explaining your work with confidence | Mock interview, scenario questions, big troubleshooting challenge | 🎓 100 days complete |

## Projects summary

| # | Project | Day | Date |
|---|---|---|---|
| 1 | Linux server administration lab | 29 | 5 Nov |
| 2 | Host a website on AWS (upgraded to HA 3-tier on Day 59) | 50 / 59 | 26 Nov / 5 Dec |
| 3 | Dockerize an application | 67 | 13 Dec |
| 4 | AWS infrastructure with Terraform | 72 | 18 Dec |
| 6 | GitHub Actions pipeline | 76 | 22 Dec |
| 5 | Jenkins CI/CD pipeline | 78 | 24 Dec |
| 7 | Deploy an app to Kubernetes | 87 | 2 Jan |
| 8 | Prometheus & Grafana monitoring | 91 | 6 Jan |
| 9 | GitOps with Argo CD | 93 | 8 Jan |
| Final | Production-style Cloud/DevOps platform | 99 | 14 Jan |

## AWS Free plan strategy
- **Create the account on Day 41 (17 Nov 2026), not earlier.** The Free plan lasts 6 months (about 180 days) or until the credits run out, whichever comes first. Starting on Day 41 means it covers every AWS day in this course and lasts until about mid-May 2027.
- **Credits:** $100 at sign-up, plus up to $100 more for completing AWS onboarding activities.
- **Protecting the credits:** delete resources after every lab, watch the credit balance, and keep the expensive labs (NAT Gateway, RDS, ECS, EKS) to a few hours.

## Rules for this course
- A day is only marked complete when the practice is done and I can explain it in my own words.
- If a topic needs more time, we take it. Dates move if needed; it is better to extend than to rush.
- No passwords, API keys, tokens or secrets in GitHub, ever.
- AWS labs: warning first, then the lab, then cleanup. Check the Billing console after every AWS day.
