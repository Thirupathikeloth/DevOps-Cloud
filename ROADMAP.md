# 90-Day DevOps, Cloud & Platform Engineering Roadmap

**Level:** absolute beginner. **Time:** 2.5 hours a day.

**Each day has 4 parts:**
1. Learn (40–50 min)
2. Guided hands-on (50–60 min)
3. Independent practice (30–40 min)
4. Review (10–15 min)

**Legend**
- ⚠️ = this day uses AWS resources that can cost money. You get a cost warning before the lab and cleanup steps after it.
- 🔐 = security topic. Security is also covered on most other days.
- 🛠️ = troubleshooting scenario
- 🎯 = interview practice
- Every 7th day is a **weekly review**: a mini assessment and a troubleshooting challenge.

## Starting from zero

I am starting with zero experience. I have never typed a Linux or Git command and do not know how they work. So in this course:
- No command is used before it has been explained: what it does, what each part means, what the output should look like, and how to check it worked.
- New words are explained the first time they appear, using everyday comparisons.
- Hands-on steps come one or two commands at a time. I run them, report what I see, and only then continue.
- If something is unclear, we stay on it until it makes sense. Speed is not the goal.

## Why the tools come in this order

| Phase | Days | Why it comes here |
|---|---|---|
| 1. Networking | 1–7 | Every server, cloud, container and cluster talks over a network. If you understand networking, everything later makes sense. |
| 2. Linux | 8–21 | Almost all servers, containers and cloud machines run Linux. |
| 3. Git & GitHub | 22–28 | From here on you save all your work in GitHub. That builds your portfolio. |
| 4. Bash & Python | 29–35 | Automation. You stop typing the same commands by hand. |
| 5. AWS | 36–49 | Real servers and networks in the cloud. |
| 6. Docker | 50–56 | Package any application so it runs the same way everywhere. |
| 7. Terraform + Ansible | 57–63 | Build your AWS setup from code instead of clicking in the console. |
| 8. CI/CD | 64–70 | Build, test, scan and deploy automatically on every code change. |
| 9. Kubernetes | 71–79 | Run containers at scale. Includes Helm and basic EKS. |
| 10. Observability | 80–82 | See what is happening inside your systems: metrics, logs, alerts. |
| 11. Platform Eng. + GitOps | 83–84 | Turn everything you learned into self-service tools for developers. |
| 12. Final project | 85–90 | Put everything together into one production-style platform. |

## The full plan

| Day | Main Topic | What I Learn | Hands-On Practice | Project/Milestone |
|---|---|---|---|---|
| **1** | Computer basics & how computers communicate | What a computer, operating system, program, file and the internet are. What a "terminal" and a "command" are. What a network, client and server are. No experience needed | Open a terminal for the first time and type your first 3 commands, slowly, one by one with explanations. Then use `ping` to see two computers talking | First command typed |
| **2** | IP addresses | IPv4, public vs private IP, localhost, IPv6 basics | Find your private and public IP. Test with `ping 127.0.0.1` | — |
| **3** | Subnets & CIDR | Network vs host part, subnet masks, CIDR (`/24`, `/16`), how many IPs fit in a range | Subnet calculation exercises on paper and with a calculator tool. Plan an office network | Subnetting worksheet |
| **4** | DNS & DHCP | How names become IPs, DNS record types (A, CNAME, MX, TXT), TTL, how DHCP gives you an IP | `nslookup`, `dig`, look at DNS records of real websites | — |
| **5** | Ports, TCP/UDP, HTTP/HTTPS | Ports, TCP vs UDP, HTTP methods and status codes, TLS/HTTPS certificates | Use `curl -v` to read HTTP requests and replies, check open ports | — |
| **6** | SSH, firewalls, NAT, routing, load balancers, proxies | How SSH works, firewall rules, NAT, default gateway, routing table, load balancer, proxy vs reverse proxy | Look at your routing table, run `traceroute`/`tracert`, draw how one web request travels | Network diagram #1 |
| **7** | Network troubleshooting + **Weekly review 1** | A step-by-step way to troubleshoot (layer by layer) | 🛠️ "Website is down", 🛠️ "DNS not resolving" | 🎯 Networking interview Qs |
| **8** | Linux introduction | What Linux is and why servers use it. Kernel, shell, distributions, the file system tree, explained with everyday comparisons | Install Ubuntu step by step (WSL2, a VM, or a cloud shell). How to read a command (command, options, arguments). Your first Linux commands | Linux running |
| **9** | Files & directories | Paths (absolute/relative), `ls`, `cd`, `pwd`, `mkdir`, `cp`, `mv`, `rm` | Build a folder structure for a fake company | — |
| **10** | Viewing & searching text | `cat`, `less`, `head`, `tail`, `grep`, `find`, pipes `\|`, redirects `>` | Search through sample log files | — |
| **11** | Users & groups | root, `sudo`, `/etc/passwd`, `useradd`, `groups` | Create users and teams for the fake company | — |
| **12** | Permissions 🔐 | rwx, `chmod`, `chown`, numeric permissions (755/644), least privilege | Lock down folders so each team only sees its own files | — |
| **13** | Processes, CPU & memory | Processes, PID, `ps`, `top`/`htop`, `kill`, `free`, load average | 🛠️ Find and stop a process that uses too much CPU | — |
| **14** | **Weekly review 2** | Review of days 8–13 | Mini lab: set up a small multi-user server | 🎯 Linux interview Qs |
| **15** | Packages, services & systemd | `apt`, repositories, `systemctl`, unit files, starting services at boot | Install and manage nginx as a service | — |
| **16** | Environment variables & the shell | `env`, `export`, `PATH`, `.bashrc`, why secrets must never be hardcoded 🔐 | Customize your shell and set variables safely | — |
| **17** | Linux networking & SSH 🔐 | `ip`, `ss`, `curl`, `/etc/hosts`, SSH keys, `ssh-keygen`, `~/.ssh/config` | Create SSH keys. Find which program is using a port | — |
| **18** | Logs | `/var/log`, `journalctl`, log rotation | 🛠️ "nginx won't start": investigate it using the logs | — |
| **19** | Disk management | `df`, `du`, mounts, partitions, inodes | 🛠️ "Disk is full": find what is filling it and clean up | — |
| **20** | cron & Linux security 🔐 | crontab syntax, SSH hardening, `ufw` firewall, updates, fail2ban | Schedule a backup with cron, harden SSH | — |
| **21** | Linux troubleshooting + **Weekly review 3** | A step-by-step way to troubleshoot a server | 🛠️ Mixed scenarios | ✅ **Project 1: Linux server administration lab** |
| **22** | Git basics | What version control is, repository, working area vs staging vs commit | `git init`, `add`, `commit`, `log`, `diff` | — |
| **23** | Branches & merging | Branches, `switch`, `merge`, fast-forward vs merge commit | Build a feature on a branch and merge it | — |
| **24** | GitHub | Remote, `clone`, `push`, `pull`, `fetch`, SSH auth to GitHub 🔐 | Push Project 1 to your GitHub | Project 1 on GitHub |
| **25** | Pull requests | PR workflow, code review, protected branches | Open, review and merge a PR on your own repo | — |
| **26** | Merge conflicts & .gitignore | Why conflicts happen and how to fix them, `.gitignore`, secret leaks 🔐 | Create a conflict on purpose and resolve it | — |
| **27** | Git workflows | GitHub Flow, GitFlow, trunk-based development, commit message style | Set up your portfolio README and repo structure | GitHub portfolio started |
| **28** | **Weekly review 4** | Review of Git | 🛠️ "I committed a secret, what now?" | 🎯 Git interview Qs |
| **29** | Bash basics | Shebang (`#!`), variables, input, quotes, exit codes | Your first script: system info report | — |
| **30** | Conditions & loops | `if`, `test`/`[[ ]]`, `for`, `while`, `case` | A script that checks if services are running | — |
| **31** | Functions & error handling | Functions, `set -euo pipefail`, logging, arguments | Server health-check script with cron | Mini-project: health checker |
| **32** | Python basics | Variables, lists, dicts, `if`/loops, functions | Small Python exercises | — |
| **33** | Python for files & errors | Reading/writing files, `try/except`, `os`, env variables 🔐 | Log-file analyzer script | — |
| **34** | Python, APIs & JSON | What an API is, JSON, the `requests` library | Script that calls the GitHub API and saves a report | Mini-project: API automation |
| **35** | **Weekly review 5** | Review of scripting | Automation challenge | 🎯 Scripting interview Qs |
| **36** | Cloud concepts & AWS setup 🔐 | IaaS/PaaS/SaaS, regions, Availability Zones, shared responsibility, the Free Tier | Create your AWS account on the **Free plan** (6 months, $100 credits up to $200), turn on MFA, set budgets and credit alerts | Safe AWS account |
| **37** | IAM 🔐 | Users, groups, roles, policies, least privilege, why you never use the root user day to day | Create an admin IAM user, groups and a custom read-only policy | — |
| **38** | EC2 ⚠️ | Instances, AMIs, instance types, key pairs, user data | Launch a free-tier EC2, connect with SSH, then clean up | — |
| **39** | EBS, Security Groups & Elastic IP ⚠️ | Volumes, snapshots, stateful firewalls, static IPs (and their cost) | Attach a volume, take a snapshot, tighten security group rules | — |
| **40** | S3 🔐 | Buckets, objects, storage classes, versioning, bucket policies, Block Public Access | Host a static website on S3 | — |
| **41** | AWS CLI | Profiles, `aws configure`, SSO/short-lived credentials, output formats, `--query` | Manage EC2 and S3 from the terminal | — |
| **42** | **Weekly review 6** ⚠️ | Review of AWS basics | 🛠️ "EC2 is unreachable" | ✅ **Project 2: Host a website on AWS** |
| **43** | VPC fundamentals ⚠️ | VPC, public/private subnets, route tables, Internet Gateway | Build a custom VPC by hand | — |
| **44** | NAT & NACL ⚠️ | NAT Gateway (and its cost), NACL vs Security Group, bastion host vs SSM Session Manager | Private server reaches the internet through NAT, then delete the NAT | 🛠️ "Server can't reach the internet" |
| **45** | Load balancers ⚠️ | ALB vs NLB, target groups, health checks | Put an ALB in front of 2 EC2 servers | — |
| **46** | Auto Scaling & high availability ⚠️ | Launch templates, Auto Scaling Groups, scaling policies, multi-AZ design | Auto-scaled web tier, stress test it | — |
| **47** | Route 53 & RDS ⚠️ | Hosted zones, routing policies, managed databases, Multi-AZ, backups | Create an RDS database and connect to it from EC2 privately | 🛠️ "App can't connect to the database" |
| **48** | CloudWatch, CloudTrail & secrets 🔐 | Metrics, alarms, logs, audit trails, Secrets Manager vs SSM Parameter Store | CPU alarm + email alert, store a database password in SSM | — |
| **49** | Cost, backup & DR + **Weekly review 7** | Cost Explorer, tagging, RPO/RTO, backup strategies | Cost review of your account, a backup plan | 🎯 AWS interview Qs |
| **50** | Containers | Containers vs virtual machines, images, the Docker engine | Install Docker, `docker run`, `ps`, `logs`, `exec` | — |
| **51** | Dockerfiles | Instructions, layers, build cache, `.dockerignore` | Containerize a simple Python web app | — |
| **52** | Registries | Docker Hub, Amazon ECR, tags, image versioning | Push your image to Docker Hub and ECR | — |
| **53** | Volumes, networks & env vars | Persistent data, bridge networks, passing config safely 🔐 | App + database containers talking to each other | 🛠️ "Container keeps restarting" |
| **54** | Docker Compose | Multi-container apps, `compose.yaml`, `.env` files | Web + database + cache stack with Compose | — |
| **55** | Multi-stage builds & container security 🔐 | Small images, non-root users, image scanning with Trivy | Shrink your image, scan it and fix what it finds | — |
| **56** | **Weekly review 8** | Review of Docker | Docker troubleshooting lab | ✅ **Project 3: Dockerize an application** |
| **57** | Infrastructure as Code & Terraform basics ⚠️ | What IaC is, HCL, providers, resources, `init/plan/apply/destroy` | Create an S3 bucket with Terraform | — |
| **58** | Variables, outputs & state | Input variables, `tfvars`, outputs, what the state file is | Build an EC2 server with variables | — |
| **59** | Remote state & modules ⚠️ | S3 backend, state locking, modules, reusing code | Move your state to S3, write your first module | — |
| **60** | Terraform AWS build ⚠️ | Building a whole VPC with Terraform | VPC + subnets + ALB + EC2 using Terraform | ✅ **Project 4: AWS infrastructure with Terraform** |
| **61** | Terraform security & best practices 🔐 | Keeping secrets out of state, `tflint`, `checkov`, project layout | 🛠️ "Terraform apply failed": fix broken configs | — |
| **62** | Ansible & configuration management | Agentless config, inventory, playbooks, idempotency | Use Ansible to configure servers that Terraform built | — |
| **63** | **Weekly review 9** | Review of IaC | IaC challenge | 🎯 Terraform interview Qs |
| **64** | CI/CD concepts | Continuous Integration, Delivery and Deployment; pipelines, artifacts | Draw the pipeline for your app | — |
| **65** | GitHub Actions basics | Workflows, triggers, jobs, steps, runners | Lint + test workflow | — |
| **66** | GitHub Actions to the registry 🔐 | Building Docker images, secrets, OIDC login to AWS (no stored keys) | Code → Build → Test → Image → ECR | ✅ **Project 6: GitHub Actions pipeline** |
| **67** | Jenkins basics ⚠️ | Controller/agents, jobs, plugins | Install Jenkins in Docker, first job | — |
| **68** | Jenkins pipelines | Declarative `Jenkinsfile`, stages, credentials store | Full pipeline that deploys to an EC2 Docker host | ✅ **Project 5: Jenkins CI/CD pipeline** |
| **69** | Secure CI/CD & DevSecOps 🔐 | Secret scanning (gitleaks), dependency scanning, SAST, image scanning, branch protection | Add security gates to your pipelines | 🛠️ "Pipeline failed" |
| **70** | **Weekly review 10** | Review of CI/CD | Pipeline debugging challenge | 🎯 CI/CD interview Qs |
| **71** | Kubernetes architecture | Cluster, control plane, worker nodes, kubelet, `kubectl` | Install a local cluster (kind/minikube), explore it | — |
| **72** | Pods & YAML | YAML syntax, Pod spec explained line by line | Run, inspect and debug Pods | — |
| **73** | Deployments & ReplicaSets | Desired state, rolling updates, rollbacks | Deploy your app, update it, roll it back | — |
| **74** | Services, Ingress & networking | ClusterIP / NodePort / LoadBalancer, Ingress, cluster DNS | Expose your app with an Ingress | — |
| **75** | Config, Secrets, namespaces & storage 🔐 | ConfigMaps, Secrets, namespaces, PV/PVC | App + database with persistent storage | — |
| **76** | Health checks, resources, scaling & RBAC 🔐 | Probes, requests/limits, HPA, RBAC, Pod security | Add probes and limits, autoscale, restrict access | 🛠️ "Pod in CrashLoopBackOff" |
| **77** | **Weekly review 11** | Review of Kubernetes | K8s troubleshooting lab | ✅ **Project 7: Deploy an app to Kubernetes** |
| **78** | Helm | Charts, values, templates, releases | Turn your app into a Helm chart | — |
| **79** | Basic EKS ⚠️ | Managed Kubernetes, node groups, IAM for pods. Costs real money: short lab, then delete | Create EKS with Terraform, deploy, destroy the same day | — |
| **80** | Monitoring & Prometheus | Metrics, logs, traces, alerts; Prometheus, exporters, PromQL | Install kube-prometheus-stack with Helm | — |
| **81** | Grafana & alerting | Dashboards, alert rules, SLIs/SLOs | App + infrastructure dashboards, alerts | ✅ **Project 8: Prometheus & Grafana monitoring** |
| **82** | Logging, tracing & troubleshooting | Central logging (Loki/CloudWatch Logs), tracing basics | 🛠️ "High CPU", 🛠️ "slow app": investigate using monitoring | — |
| **83** | Platform Engineering | IDP, golden paths, developer experience, self-service, Backstage, how the roles work together | Design a golden-path template for a new service | — |
| **84** | GitOps & Argo CD + **Weekly review 12** | GitOps rules, Argo CD, sync, drift | Deploy with Argo CD from Git | ✅ **Project 9: GitOps with Argo CD** |
| **85** | Final project: design & infrastructure ⚠️ | Architecture design, cost plan | Diagram + Terraform for the VPC, EKS and ECR | Final project started |
| **86** | Final project: CI | Pipeline design | GitHub Actions: test → scan → build → ECR → update Helm values | — |
| **87** | Final project: CD with GitOps ⚠️ | Helm + Argo CD in production style | App deployed automatically through Argo CD | — |
| **88** | Final project: observability & security 🔐 | Hardening checklist | Prometheus/Grafana, alerts, RBAC, network policies, secrets | — |
| **89** | Final project: documentation | Writing engineering docs | README, architecture diagram, troubleshooting log, resume bullets, full cleanup | ✅ **Final project complete** |
| **90** | Final assessment & interview prep | How to explain your projects | Mock interview, scenario questions, a big troubleshooting challenge | 🎓 90-day completion |

## Projects summary

| # | Project | Day finished |
|---|---|---|
| 1 | Linux server administration lab | 21 |
| 2 | Host a website on AWS | 42 |
| 3 | Dockerize an application | 56 |
| 4 | AWS infrastructure with Terraform | 60 |
| 6 | GitHub Actions pipeline | 66 |
| 5 | Jenkins CI/CD pipeline | 68 |
| 7 | Deploy an app to Kubernetes | 77 |
| 8 | Prometheus & Grafana monitoring | 81 |
| 9 | GitOps with Argo CD | 84 |
| Final | Production-style Cloud/DevOps platform | 89 |

## AWS Free plan strategy
- **Account created on Day 36, not earlier.** The Free plan lasts 6 months (about 180 days) or until the credits run out, whichever comes first. Starting on Day 36 means the free period covers every AWS day in this course (36–90) and about 4 more months of practice after it.
- **Credits:** $100 at sign-up, plus up to $100 more for completing AWS onboarding activities.
- **Protecting the credits:** delete resources after every lab, watch the credit balance, and keep the expensive labs (NAT Gateway, EKS, RDS) to a few hours.

## Rules for this course
- A day is only marked complete when the practice is done and I can explain it in my own words.
- No passwords, API keys, tokens or secrets in GitHub, ever.
- AWS labs: warning first, then the lab, then cleanup. Check the Billing console after every AWS day.
