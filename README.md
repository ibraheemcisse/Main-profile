<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ibrahim Cisse - Infrastructure Engineer</title>
</head>
<body>

<h1>Hi, I'm Ibrahim! <br/>
<a href="https://github.com/ibraheemcisse">Infrastructure Engineer</a>, 
<a href="https://linkedin.com/in/ibrahim-c-a2b6501a0/">Platform & SRE</a>
</h1>

<p>
I build infrastructure and then intentionally break it to understand how it fails.
</p>

<p>
4 years operating production systems in fintech (AWS, 99.9% uptime). Built a 
Kubernetes cluster from bare metal and chaos-tested it - node failures, memory 
exhaustion, pod crashes. One test revealed that local storage creates a 25-hour 
outage scenario. Documented everything in SRE-style postmortems.
</p>

<p>
I also participated in an AWS-funded proof of concept where I built the same 
application 4 times with different infrastructure. Load tested 239,000+ requests. 
Found that Kubernetes cost 5x more than Fargate with worse latency for single 
applications. That's engineering judgment.
</p>

<p>
Tech: Kubernetes, AWS, Terraform, Chaos Engineering, Production Operations<br/>
Open to: Platform Engineer, SRE, Infrastructure Engineer roles
</p>

---

<h2>🎬 Video Walkthrough</h2>
<ul>
    <li><a href="[YouTube link]">8-Minute Infrastructure Lab Demo - Chaos Engineering in Action</a></li>
    <li>Watch me build, deploy, and intentionally break a Kubernetes cluster</li>
</ul>

---

<h2>🏗️ Infrastructure Projects</h2>

<ul>
<b>Production Kubernetes Lab - Chaos Engineering:</b>
    <li><a href="https://github.com/ibraheemcisse/infrastructure-lab">
        Bare Metal Kubernetes with Security Hardening & Chaos Tests</a></li>
    <li>Built 3-node cluster (Terraform + Kubespray)</li>
    <li>Security: Non-root containers, read-only FS, RBAC, NetworkPolicies</li>
    <li>Chaos tests: Node failure (25h outage), Memory OOM, Pod crashes</li>
    <li>Observability: Prometheus + Grafana + postgres_exporter</li>
    <li>Key finding: Local storage creates single point of failure</li>
</ul>

<ul>
<b>AWS Infrastructure Trade-offs Analysis:</b>
    <li><a href="https://github.com/ibraheemcisse/devops-dashboard">
        Same App, 4 Architectures - Cost vs Performance Study</a></li>
    <li>AWS Lift program funded ($550 credits)</li>
    <li>Built: Single EC2 → Load-balanced → ECS Fargate → Kubernetes + Istio</li>
    <li>Load tested: 239,000+ requests across 5 days</li>
    <li>Result: Fargate optimal ($2/day vs K8s $11/day, lower latency)</li>
    <li><a href="[Medium article link]">Read the full write-up</a></li>
</ul>

<ul>
<b>Kubernetes Automation & Operations:</b>
    <li><a href="https://github.com/ibraheemcisse/multi-node-kubernetes-cluster">
        Multi-node Kubernetes with Terraform</a></li>
    <li><a href="https://github.com/ibraheemcisse/KEDA-HTTP-Add-On-with-Autoscaling-on-Kubernetes-EKS-">
        KEDA HTTP Autoscaling on EKS</a></li>
    <li><a href="https://github.com/ibraheemcisse/End-to-end-k8s-Microservice-application-deployment">
        End-to-End Microservices Deployment</a></li>
    <li><a href="https://github.com/ibraheemcisse/kubernetes-cluster-upgrade">
        Kubernetes Cluster Upgrade Procedures</a></li>
</ul>

<ul>
<b>AWS Cloud Architecture:</b>
    <li><a href="https://github.com/ibraheemcisse/AWS-VPC-Setup-Guide-Production-Ready-Infrastructure">
        Production-Ready AWS VPC Architecture</a></li>
</ul>

<ul>
<b>Operations & Monitoring:</b>
    <li><a href="https://github.com/ibraheemcisse/System_Health_Check">
        System Health Check Automation</a></li>
    <li><a href="https://github.com/ibraheemcisse/Network_Diagnostic_Script">
        Network Diagnostic Tool (Recognized by Datadog engineers)</a></li>
</ul>

---

<h2>📝 Technical Writing</h2>

<ul>
<b>Infrastructure & Architecture:</b>
    <li><a href="[Medium link]">Building the Same App Four Times: Infrastructure Trade-offs</a></li>
    <li><a href="[Medium link]">When Your Database Node Dies: A 25-Hour Kubernetes Story</a></li>
</ul>

<ul>
<b>Kubernetes Deep Dives:</b>
    <li><a href="https://medium.com/@info_37956/deploying-a-flask-application-on-google-kubernetes-engine-gke-e143c8c14d66">
        Deploying Flask on GKE</a></li>
    <li><a href="https://medium.com/@info_37956/setting-up-and-troubleshooting-hpa-and-vpa-in-kubernetes-593aac3ddb9f">
        HPA and VPA Troubleshooting</a></li>
    <li><a href="https://medium.com/@info_37956/minikube-setting-up-metrics-server-rbac-and-kubectl-context-2ea89ec6d07f">
        Metrics Server and RBAC Setup</a></li>
</ul>

<ul>
<b>AWS Solutions:</b>
    <li><a href="https://medium.com/@info_37956/deployment-of-an-amazon-rds-multi-az-and-read-replica-in-aws-b1c8f3a76c79">
        RDS Multi-AZ and Read Replicas</a></li>
    <li><a href="https://medium.com/@info_37956/cloudformation-for-a-retail-company-lab-ca1416c1f548">
        CloudFormation Infrastructure as Code</a></li>
    <li><a href="https://medium.com/@info_37956/utilize-aws-vpc-flow-logs-to-monitor-network-traffic-dabec829faa4">
        VPC Flow Logs for Network Monitoring</a></li>
</ul>

---

<h2>📊 Chaos Engineering Postmortems</h2>

<p>All failure scenarios documented with root cause analysis:</p>

<ol>
    <li><a href="https://github.com/ibraheemcisse/infrastructure-lab/blob/main/postmortems/005-pod-crashloop-chaos.md">
        Pod CrashLoopBackOff During Rolling Update</a></li>
    <li><a href="https://github.com/ibraheemcisse/infrastructure-lab/blob/main/postmortems/006-node-failure-storage-affinity.md">
        Node Failure with Local Storage (25-hour outage)</a></li>
    <li><a href="https://github.com/ibraheemcisse/infrastructure-lab/blob/main/postmortems/007-statefulset-migration.md">
        StatefulSet Migration</a></li>
    <li><a href="https://github.com/ibraheemcisse/infrastructure-lab/blob/main/postmortems/008-memory-oom-chaos.md">
        Memory OOM Kill</a></li>
    <li>PostgreSQL Monitoring Setup</li>
</ol>

---

<h2>🎓 Education & Certifications</h2>

<dl>
    <dt><b>Bachelor of Engineering (Hons)</b></dt>
    <dd>Electronic and Communication Engineering - Anglia Ruskin University</dd>
    
    <dt><b>Certified Kubernetes Administrator (CKA)</b></dt>
    <dd>Scheduled: April 2026</dd>
    
    <dt><b>Microsoft Certified: Azure Fundamentals (AZ-900)</b></dt>
    <dd>Credential ID: I402-6928</dd>
    
    <dt><b>Google IT Support Professional Certification</b></dt>
    <dd>Credential ID: AB6KQ5A5MPE4</dd>
    
    <dt><b>Prometheus Monitoring & Alerting</b></dt>
    <dd>Credential ID: UC-83556853-c5b9-4e46-b40a-e3612bd24240</dd>
    
    <dt><b>HashiCorp Certified Terraform Associate</b></dt>
    <dd>Credential ID: F3B8F05EB893</dd>
</dl>

---

<h2>🛠️ Technical Skills</h2>

<p><b>Cloud & Infrastructure:</b> AWS (EC2, ECS, VPC, RDS, S3), Azure, Terraform, Ansible</p>
<p><b>Kubernetes:</b> Cluster operations, Kubespray, EKS, StatefulSets, RBAC, Security contexts, Helm, KEDA</p>
<p><b>Observability:</b> Prometheus, Grafana, PagerDuty, CloudWatch</p>
<p><b>Operations:</b> Linux systems, On-call rotations, Incident response, Chaos engineering</p>
<p><b>Networking:</b> TCP/IP, DNS, Load balancers, Network diagnostics</p>
<p><b>Databases:</b> PostgreSQL, MySQL, Redis</p>
<p><b>CI/CD:</b> GitHub Actions, Jenkins, ArgoCD</p>
<p><b>Scripting:</b> Bash, Python, SQL</p>

---

<h2>🤳 Connect With Me</h2>

<a href="https://www.linkedin.com/in/ibrahim-cisse-a2b6501a0/" target="_blank">
    <img align="left" alt="Ibrahim Cisse | LinkedIn" width="22px" 
         src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />
</a>
<a href="https://github.com/ibraheemcisse" target="_blank">
    <img align="left" alt="Ibrahim Cisse | GitHub" width="22px" 
         src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/github.svg" />
</a>
<a href="mailto:ibrahim.umar.cisse@gmail.com">
    <img align="left" alt="Ibrahim Cisse | Email" width="22px" 
         src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/gmail.svg" />
</a>

<br/><br/>

<p>
Open to Platform Engineer, SRE, and Infrastructure Engineer roles.<br/>
All code is open source. All failures are documented. All lessons are shared.
</p>

</body>
</html>
