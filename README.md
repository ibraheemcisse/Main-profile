<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ibrahim Cisse — Infrastructure Engineer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #080c10;
      --surface: #0e1419;
      --border: #1e2830;
      --accent: #00d4ff;
      --accent2: #ff6b35;
      --text: #e8edf2;
      --muted: #6b7f8e;
      --green: #00ff88;
      --syne: 'Syne', sans-serif;
      --mono: 'JetBrains Mono', monospace;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--mono);
      font-size: 14px;
      line-height: 1.6;
      overflow-x: hidden;
      cursor: crosshair;
    }

    /* Grid background */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
      background-size: 40px 40px;
      pointer-events: none;
      z-index: 0;
    }

    /* Glow orbs */
    .orb {
      position: fixed;
      border-radius: 50%;
      pointer-events: none;
      z-index: 0;
      filter: blur(80px);
      opacity: 0.15;
    }
    .orb1 { width: 500px; height: 500px; background: var(--accent); top: -200px; right: -100px; animation: drift 12s ease-in-out infinite alternate; }
    .orb2 { width: 400px; height: 400px; background: var(--accent2); bottom: 200px; left: -150px; animation: drift 15s ease-in-out infinite alternate-reverse; }
    @keyframes drift { from { transform: translate(0,0); } to { transform: translate(40px, 30px); } }

    main { position: relative; z-index: 1; max-width: 900px; margin: 0 auto; padding: 0 24px 80px; }

    /* ── HEADER ── */
    header {
      padding: 80px 0 60px;
      border-bottom: 1px solid var(--border);
    }

    .status-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: rgba(0,255,136,0.08);
      border: 1px solid rgba(0,255,136,0.2);
      color: var(--green);
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      padding: 5px 12px;
      border-radius: 2px;
      margin-bottom: 28px;
    }
    .status-dot {
      width: 6px; height: 6px;
      background: var(--green);
      border-radius: 50%;
      animation: pulse-dot 2s ease-in-out infinite;
    }
    @keyframes pulse-dot {
      0%, 100% { opacity: 1; box-shadow: 0 0 0 0 rgba(0,255,136,0.4); }
      50% { opacity: 0.7; box-shadow: 0 0 0 4px rgba(0,255,136,0); }
    }

    h1 {
      font-family: var(--syne);
      font-size: clamp(38px, 7vw, 64px);
      font-weight: 800;
      line-height: 1.05;
      letter-spacing: -0.02em;
      margin-bottom: 8px;
    }
    h1 span { color: var(--accent); }

    .title-line {
      font-family: var(--syne);
      font-size: clamp(14px, 2.5vw, 18px);
      color: var(--muted);
      font-weight: 400;
      margin-bottom: 24px;
      letter-spacing: 0.05em;
    }
    .title-line strong { color: var(--accent2); font-weight: 600; }

    .tagline {
      max-width: 520px;
      color: #9ab0bf;
      line-height: 1.75;
      margin-bottom: 32px;
    }

    .header-stats {
      display: flex;
      flex-wrap: wrap;
      gap: 0;
      border: 1px solid var(--border);
      border-radius: 4px;
      overflow: hidden;
      max-width: 520px;
      margin-bottom: 32px;
    }
    .stat {
      flex: 1;
      min-width: 120px;
      padding: 14px 18px;
      border-right: 1px solid var(--border);
      transition: background 0.2s;
    }
    .stat:last-child { border-right: none; }
    .stat:hover { background: rgba(0,212,255,0.05); }
    .stat-num {
      font-family: var(--syne);
      font-size: 22px;
      font-weight: 700;
      color: var(--accent);
      display: block;
    }
    .stat-label { font-size: 10px; color: var(--muted); text-transform: uppercase; letter-spacing: 0.1em; }

    .header-links { display: flex; flex-wrap: wrap; gap: 10px; }
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      padding: 9px 18px;
      font-family: var(--mono);
      font-size: 12px;
      font-weight: 500;
      border-radius: 2px;
      text-decoration: none;
      letter-spacing: 0.05em;
      transition: all 0.2s;
    }
    .btn-primary {
      background: var(--accent);
      color: var(--bg);
      border: 1px solid var(--accent);
    }
    .btn-primary:hover { background: transparent; color: var(--accent); }
    .btn-secondary {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border);
    }
    .btn-secondary:hover { border-color: var(--accent); color: var(--accent); }

    /* ── SECTIONS ── */
    section { margin-top: 64px; }

    .section-label {
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 10px;
      font-weight: 500;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 28px;
    }
    .section-label::before { content: '//'; color: var(--muted); }
    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    h2 {
      font-family: var(--syne);
      font-size: 26px;
      font-weight: 700;
      margin-bottom: 6px;
      color: var(--text);
    }

    /* ── PROJECT CARDS ── */
    .project-grid {
      display: grid;
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 4px;
      overflow: hidden;
    }
    .project-grid.cols-2 { grid-template-columns: repeat(auto-fill, minmax(380px, 1fr)); }

    .project-card {
      background: var(--surface);
      padding: 22px 24px;
      text-decoration: none;
      color: inherit;
      display: block;
      transition: background 0.2s;
      position: relative;
      overflow: hidden;
    }
    .project-card::before {
      content: '';
      position: absolute;
      left: 0; top: 0;
      width: 3px; height: 100%;
      background: var(--accent);
      transform: scaleY(0);
      transition: transform 0.2s;
      transform-origin: bottom;
    }
    .project-card:hover { background: rgba(0,212,255,0.04); }
    .project-card:hover::before { transform: scaleY(1); }

    .project-card.featured::before { background: var(--accent2); }
    .project-card.featured:hover { background: rgba(255,107,53,0.04); }

    .card-top {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 10px;
    }
    .card-name {
      font-family: var(--syne);
      font-size: 15px;
      font-weight: 600;
      color: var(--text);
    }
    .card-arrow {
      color: var(--muted);
      font-size: 16px;
      transition: transform 0.2s, color 0.2s;
    }
    .project-card:hover .card-arrow { transform: translate(3px, -3px); color: var(--accent); }

    .card-desc {
      font-size: 12px;
      color: var(--muted);
      line-height: 1.65;
      margin-bottom: 14px;
    }

    .card-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
    }
    .tag {
      font-size: 10px;
      padding: 3px 8px;
      background: rgba(0,212,255,0.06);
      border: 1px solid rgba(0,212,255,0.15);
      color: var(--accent);
      border-radius: 2px;
      letter-spacing: 0.05em;
    }
    .tag.orange {
      background: rgba(255,107,53,0.06);
      border-color: rgba(255,107,53,0.2);
      color: var(--accent2);
    }
    .tag.green {
      background: rgba(0,255,136,0.06);
      border-color: rgba(0,255,136,0.2);
      color: var(--green);
    }

    /* ── POSTMORTEM / INCIDENT LIST ── */
    .incident-list { display: grid; gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: 4px; overflow: hidden; }

    .incident-item {
      display: flex;
      align-items: center;
      gap: 16px;
      padding: 16px 20px;
      background: var(--surface);
      text-decoration: none;
      color: inherit;
      transition: background 0.2s;
    }
    .incident-item:hover { background: rgba(255,107,53,0.04); }

    .incident-num {
      font-family: var(--syne);
      font-size: 11px;
      font-weight: 600;
      color: var(--accent2);
      width: 28px;
      flex-shrink: 0;
    }

    .incident-title { flex: 1; font-size: 13px; color: var(--text); }
    .incident-meta { font-size: 11px; color: var(--muted); flex-shrink: 0; }

    /* ── SKILLS GRID ── */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 4px;
      overflow: hidden;
    }
    .skill-group {
      background: var(--surface);
      padding: 18px 20px;
    }
    .skill-group-name {
      font-size: 10px;
      font-weight: 500;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 10px;
    }
    .skill-items { display: flex; flex-wrap: wrap; gap: 5px; }
    .skill-pill {
      font-size: 11px;
      padding: 3px 8px;
      background: rgba(255,255,255,0.04);
      border: 1px solid var(--border);
      color: #9ab0bf;
      border-radius: 2px;
    }

    /* ── CERTS ── */
    .certs-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 4px;
      overflow: hidden;
    }
    .cert-card {
      background: var(--surface);
      padding: 18px 20px;
      display: flex;
      gap: 14px;
      align-items: flex-start;
    }
    .cert-icon {
      font-size: 20px;
      flex-shrink: 0;
      line-height: 1;
      margin-top: 2px;
    }
    .cert-name { font-family: var(--syne); font-size: 13px; font-weight: 600; margin-bottom: 4px; }
    .cert-meta { font-size: 11px; color: var(--muted); }
    .cert-badge {
      display: inline-block;
      margin-top: 6px;
      font-size: 10px;
      padding: 2px 7px;
      background: rgba(0,255,136,0.08);
      border: 1px solid rgba(0,255,136,0.2);
      color: var(--green);
      border-radius: 2px;
    }
    .cert-badge.pending {
      background: rgba(255,107,53,0.08);
      border-color: rgba(255,107,53,0.2);
      color: var(--accent2);
    }

    /* ── WRITING ── */
    .writing-list { display: grid; gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: 4px; overflow: hidden; }
    .writing-item {
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 15px 20px;
      background: var(--surface);
      text-decoration: none;
      color: inherit;
      transition: background 0.2s;
    }
    .writing-item:hover { background: rgba(0,212,255,0.04); }
    .writing-cat {
      font-size: 10px;
      width: 90px;
      flex-shrink: 0;
      padding: 2px 6px;
      border-radius: 2px;
      text-align: center;
    }
    .cat-infra { background: rgba(0,212,255,0.08); border: 1px solid rgba(0,212,255,0.2); color: var(--accent); }
    .cat-k8s { background: rgba(0,255,136,0.08); border: 1px solid rgba(0,255,136,0.2); color: var(--green); }
    .cat-aws { background: rgba(255,107,53,0.08); border: 1px solid rgba(255,107,53,0.2); color: var(--accent2); }
    .writing-title { flex: 1; font-size: 13px; }
    .writing-arrow { color: var(--muted); font-size: 14px; transition: transform 0.2s, color 0.2s; }
    .writing-item:hover .writing-arrow { transform: translate(3px, -3px); color: var(--accent); }

    /* ── FOOTER ── */
    footer {
      margin-top: 80px;
      padding-top: 28px;
      border-top: 1px solid var(--border);
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: gap;
      gap: 16px;
    }
    .footer-note { font-size: 11px; color: var(--muted); }
    .footer-links { display: flex; gap: 16px; }
    .footer-links a { font-size: 11px; color: var(--muted); text-decoration: none; transition: color 0.2s; }
    .footer-links a:hover { color: var(--accent); }

    /* Fade-in animation */
    .fade-up {
      opacity: 0;
      transform: translateY(20px);
      animation: fadeUp 0.5s forwards;
    }
    @keyframes fadeUp { to { opacity: 1; transform: translateY(0); } }
    .d1 { animation-delay: 0.05s; }
    .d2 { animation-delay: 0.15s; }
    .d3 { animation-delay: 0.25s; }
    .d4 { animation-delay: 0.35s; }
    .d5 { animation-delay: 0.45s; }
    .d6 { animation-delay: 0.55s; }

    @media (max-width: 600px) {
      .header-stats { flex-direction: column; }
      .stat { border-right: none; border-bottom: 1px solid var(--border); }
      .stat:last-child { border-bottom: none; }
      .project-grid.cols-2 { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <div class="orb orb1"></div>
  <div class="orb orb2"></div>

  <main>
    <!-- ── HEADER ── -->
    <header>
      <div class="status-badge fade-up d1">
        <span class="status-dot"></span>
        Open to work · Platform Engineer / SRE / Infra
      </div>

      <h1 class="fade-up d2">Ibrahim<br /><span>Cisse</span></h1>
      <p class="title-line fade-up d3">
        Infrastructure Engineer &nbsp;·&nbsp; <strong>Platform & SRE</strong>
      </p>

      <p class="tagline fade-up d4">
        I build infrastructure and then intentionally break it to understand how it fails.
        4 years operating production systems in fintech on AWS at 99.9% uptime.
      </p>

      <div class="header-stats fade-up d5">
        <div class="stat">
          <span class="stat-num">4 yrs</span>
          <span class="stat-label">Production Ops</span>
        </div>
        <div class="stat">
          <span class="stat-num">99.9%</span>
          <span class="stat-label">Uptime SLA</span>
        </div>
        <div class="stat">
          <span class="stat-num">239K+</span>
          <span class="stat-label">Requests Load Tested</span>
        </div>
        <div class="stat">
          <span class="stat-num">5</span>
          <span class="stat-label">Chaos Postmortems</span>
        </div>
      </div>

      <div class="header-links fade-up d6">
        <a href="https://github.com/ibraheemcisse" target="_blank" class="btn btn-primary">↗ GitHub</a>
        <a href="https://linkedin.com/in/ibrahim-cisse-a2b6501a0/" target="_blank" class="btn btn-secondary">LinkedIn</a>
        <a href="mailto:ibrahim.umar.cisse@gmail.com" class="btn btn-secondary">Email</a>
        <a href="[YouTube link]" class="btn btn-secondary">▶ 8-Min Demo</a>
      </div>
    </header>

    <!-- ── FEATURED PROJECTS ── -->
    <section>
      <div class="section-label">Featured Work</div>
      <div class="project-grid cols-2">

        <a href="https://github.com/ibraheemcisse/infrastructure-lab" target="_blank" class="project-card featured">
          <div class="card-top">
            <span class="card-name">Production Kubernetes Lab</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">
            Bare-metal Kubernetes cluster chaos-tested against node failures, memory exhaustion,
            and pod crashes. One test revealed a 25-hour outage scenario from local storage misconfig.
          </p>
          <div class="card-tags">
            <span class="tag orange">chaos engineering</span>
            <span class="tag orange">kubernetes</span>
            <span class="tag orange">postmortems</span>
            <span class="tag orange">bare metal</span>
          </div>
        </a>

        <a href="#aws-analysis" class="project-card featured">
          <div class="card-top">
            <span class="card-name">AWS Infrastructure Trade-offs</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">
            AWS-funded PoC: built the same application 4 times with different infra. Found Kubernetes
            costs 5× more than Fargate with worse latency for single-app workloads. 239K+ load-tested requests.
          </p>
          <div class="card-tags">
            <span class="tag orange">AWS</span>
            <span class="tag orange">load testing</span>
            <span class="tag orange">cost analysis</span>
            <span class="tag orange">fargate</span>
          </div>
        </a>

      </div>
    </section>

    <!-- ── ALL PROJECTS ── -->
    <section>
      <div class="section-label">All Projects</div>
      <div class="project-grid cols-2">

        <a href="https://github.com/ibraheemcisse/multi-node-kubernetes-cluster" target="_blank" class="project-card">
          <div class="card-top">
            <span class="card-name">Multi-Node K8s with Terraform</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">Multi-node Kubernetes cluster provisioned end-to-end with Terraform.</p>
          <div class="card-tags">
            <span class="tag">Terraform</span>
            <span class="tag">Kubernetes</span>
          </div>
        </a>

        <a href="https://github.com/ibraheemcisse/KEDA-HTTP-Add-On-with-Autoscaling-on-Kubernetes-EKS-" target="_blank" class="project-card">
          <div class="card-top">
            <span class="card-name">KEDA HTTP Autoscaling on EKS</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">Event-driven autoscaling using KEDA HTTP add-on on Amazon EKS.</p>
          <div class="card-tags">
            <span class="tag">KEDA</span>
            <span class="tag">EKS</span>
            <span class="tag">Autoscaling</span>
          </div>
        </a>

        <a href="https://github.com/ibraheemcisse/End-to-end-k8s-Microservice-application-deployment" target="_blank" class="project-card">
          <div class="card-top">
            <span class="card-name">End-to-End Microservices Deployment</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">Full microservices application deployed on Kubernetes with CI/CD pipeline.</p>
          <div class="card-tags">
            <span class="tag">Kubernetes</span>
            <span class="tag">Microservices</span>
            <span class="tag">CI/CD</span>
          </div>
        </a>

        <a href="https://github.com/ibraheemcisse/kubernetes-cluster-upgrade" target="_blank" class="project-card">
          <div class="card-top">
            <span class="card-name">Kubernetes Cluster Upgrade</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">Documented zero-downtime Kubernetes version upgrade procedures for production clusters.</p>
          <div class="card-tags">
            <span class="tag">Kubernetes</span>
            <span class="tag">Operations</span>
          </div>
        </a>

        <a href="https://github.com/ibraheemcisse/AWS-VPC-Setup-Guide-Production-Ready-Infrastructure" target="_blank" class="project-card">
          <div class="card-top">
            <span class="card-name">Production-Ready AWS VPC</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">Comprehensive production-grade AWS VPC architecture with subnets, routing, and security groups.</p>
          <div class="card-tags">
            <span class="tag">AWS</span>
            <span class="tag">VPC</span>
            <span class="tag">Networking</span>
          </div>
        </a>

        <a href="https://github.com/ibraheemcisse/Network_Diagnostic_Script" target="_blank" class="project-card">
          <div class="card-top">
            <span class="card-name">Network Diagnostic Tool</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">Network diagnostics script recognized by Datadog engineers for its thoroughness.</p>
          <div class="card-tags">
            <span class="tag green">Bash</span>
            <span class="tag green">Networking</span>
            <span class="tag green">Datadog</span>
          </div>
        </a>

        <a href="https://github.com/ibraheemcisse/System_Health_Check" target="_blank" class="project-card">
          <div class="card-top">
            <span class="card-name">System Health Check Automation</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">Automated system health checks for production Linux environments.</p>
          <div class="card-tags">
            <span class="tag green">Bash</span>
            <span class="tag green">Linux</span>
            <span class="tag green">Monitoring</span>
          </div>
        </a>

        <!-- ── PLACEHOLDER FOR NEW REPOS ── -->
        <!-- Copy the block below to add more projects:
        <a href="YOUR_GITHUB_LINK" target="_blank" class="project-card">
          <div class="card-top">
            <span class="card-name">Project Name</span>
            <span class="card-arrow">↗</span>
          </div>
          <p class="card-desc">Short description of what it does and why it matters.</p>
          <div class="card-tags">
            <span class="tag">Tag1</span>
            <span class="tag">Tag2</span>
          </div>
        </a>
        -->

      </div>
    </section>

    <!-- ── CHAOS POSTMORTEMS ── -->
    <section>
      <div class="section-label">Chaos Engineering Postmortems</div>
      <div class="incident-list">

        <a href="https://github.com/ibraheemcisse/infrastructure-lab/blob/main/postmortems/005-pod-crashloop-chaos.md" target="_blank" class="incident-item">
          <span class="incident-num">INC-005</span>
          <span class="incident-title">Pod CrashLoopBackOff During Rolling Update</span>
          <span class="incident-meta">Rolling Update ·</span>
        </a>

        <a href="https://github.com/ibraheemcisse/infrastructure-lab/blob/main/postmortems/006-node-failure-storage-affinity.md" target="_blank" class="incident-item">
          <span class="incident-num">INC-006</span>
          <span class="incident-title">Node Failure with Local Storage → 25-Hour Outage Scenario</span>
          <span class="incident-meta">Storage · SEV-1</span>
        </a>

        <a href="https://github.com/ibraheemcisse/infrastructure-lab/blob/main/postmortems/007-statefulset-migration.md" target="_blank" class="incident-item">
          <span class="incident-num">INC-007</span>
          <span class="incident-title">StatefulSet Migration</span>
          <span class="incident-meta">StatefulSet ·</span>
        </a>

        <a href="https://github.com/ibraheemcisse/infrastructure-lab/blob/main/postmortems/008-memory-oom-chaos.md" target="_blank" class="incident-item">
          <span class="incident-num">INC-008</span>
          <span class="incident-title">Memory OOM Kill</span>
          <span class="incident-meta">Memory ·</span>
        </a>

        <div class="incident-item" style="opacity:0.5;">
          <span class="incident-num">INC-009</span>
          <span class="incident-title">PostgreSQL Monitoring Setup</span>
          <span class="incident-meta">DB ·</span>
        </div>

      </div>
    </section>

    <!-- ── TECHNICAL WRITING ── -->
    <section>
      <div class="section-label">Technical Writing</div>
      <div class="writing-list">

        <a href="#" class="writing-item">
          <span class="writing-cat cat-infra">Infrastructure</span>
          <span class="writing-title">Building the Same App Four Times: Infrastructure Trade-offs</span>
          <span class="writing-arrow">↗</span>
        </a>

        <a href="#" class="writing-item">
          <span class="writing-cat cat-infra">Infrastructure</span>
          <span class="writing-title">When Your Database Node Dies: A 25-Hour Kubernetes Story</span>
          <span class="writing-arrow">↗</span>
        </a>

        <a href="https://medium.com/@info_37956/deploying-a-flask-application-on-google-kubernetes-engine-gke-e143c8c14d66" target="_blank" class="writing-item">
          <span class="writing-cat cat-k8s">Kubernetes</span>
          <span class="writing-title">Deploying Flask on GKE</span>
          <span class="writing-arrow">↗</span>
        </a>

        <a href="https://medium.com/@info_37956/setting-up-and-troubleshooting-hpa-and-vpa-in-kubernetes-593aac3ddb9f" target="_blank" class="writing-item">
          <span class="writing-cat cat-k8s">Kubernetes</span>
          <span class="writing-title">HPA and VPA Troubleshooting</span>
          <span class="writing-arrow">↗</span>
        </a>

        <a href="https://medium.com/@info_37956/minikube-setting-up-metrics-server-rbac-and-kubectl-context-2ea89ec6d07f" target="_blank" class="writing-item">
          <span class="writing-cat cat-k8s">Kubernetes</span>
          <span class="writing-title">Metrics Server and RBAC Setup</span>
          <span class="writing-arrow">↗</span>
        </a>

        <a href="https://medium.com/@info_37956/deployment-of-an-amazon-rds-multi-az-and-read-replica-in-aws-b1c8f3a76c79" target="_blank" class="writing-item">
          <span class="writing-cat cat-aws">AWS</span>
          <span class="writing-title">RDS Multi-AZ and Read Replicas</span>
          <span class="writing-arrow">↗</span>
        </a>

        <a href="https://medium.com/@info_37956/cloudformation-for-a-retail-company-lab-ca1416c1f548" target="_blank" class="writing-item">
          <span class="writing-cat cat-aws">AWS</span>
          <span class="writing-title">CloudFormation Infrastructure as Code</span>
          <span class="writing-arrow">↗</span>
        </a>

        <a href="https://medium.com/@info_37956/utilize-aws-vpc-flow-logs-to-monitor-network-traffic-dabec829faa4" target="_blank" class="writing-item">
          <span class="writing-cat cat-aws">AWS</span>
          <span class="writing-title">VPC Flow Logs for Network Monitoring</span>
          <span class="writing-arrow">↗</span>
        </a>

      </div>
    </section>

    <!-- ── SKILLS ── -->
    <section>
      <div class="section-label">Technical Skills</div>
      <div class="skills-grid">
        <div class="skill-group">
          <div class="skill-group-name">Cloud & Infra</div>
          <div class="skill-items">
            <span class="skill-pill">AWS EC2</span><span class="skill-pill">ECS</span>
            <span class="skill-pill">VPC</span><span class="skill-pill">RDS</span>
            <span class="skill-pill">S3</span><span class="skill-pill">Azure</span>
            <span class="skill-pill">Terraform</span><span class="skill-pill">Ansible</span>
          </div>
        </div>
        <div class="skill-group">
          <div class="skill-group-name">Kubernetes</div>
          <div class="skill-items">
            <span class="skill-pill">Cluster Ops</span><span class="skill-pill">Kubespray</span>
            <span class="skill-pill">EKS</span><span class="skill-pill">StatefulSets</span>
            <span class="skill-pill">RBAC</span><span class="skill-pill">Helm</span>
            <span class="skill-pill">KEDA</span>
          </div>
        </div>
        <div class="skill-group">
          <div class="skill-group-name">Observability</div>
          <div class="skill-items">
            <span class="skill-pill">Prometheus</span><span class="skill-pill">Grafana</span>
            <span class="skill-pill">PagerDuty</span><span class="skill-pill">CloudWatch</span>
          </div>
        </div>
        <div class="skill-group">
          <div class="skill-group-name">Operations</div>
          <div class="skill-items">
            <span class="skill-pill">Linux</span><span class="skill-pill">On-call</span>
            <span class="skill-pill">Incident Response</span><span class="skill-pill">Chaos Eng</span>
          </div>
        </div>
        <div class="skill-group">
          <div class="skill-group-name">CI/CD & Scripting</div>
          <div class="skill-items">
            <span class="skill-pill">GitHub Actions</span><span class="skill-pill">Jenkins</span>
            <span class="skill-pill">ArgoCD</span><span class="skill-pill">Bash</span>
            <span class="skill-pill">Python</span><span class="skill-pill">SQL</span>
          </div>
        </div>
        <div class="skill-group">
          <div class="skill-group-name">Networking & DB</div>
          <div class="skill-items">
            <span class="skill-pill">TCP/IP</span><span class="skill-pill">DNS</span>
            <span class="skill-pill">Load Balancers</span><span class="skill-pill">PostgreSQL</span>
            <span class="skill-pill">MySQL</span><span class="skill-pill">Redis</span>
          </div>
        </div>
      </div>
    </section>

    <!-- ── CERTIFICATIONS ── -->
    <section>
      <div class="section-label">Education & Certifications</div>
      <div class="certs-grid">

        <div class="cert-card">
          <span class="cert-icon">🎓</span>
          <div>
            <div class="cert-name">BEng Electronic & Communication</div>
            <div class="cert-meta">Anglia Ruskin University</div>
            <span class="cert-badge">Degree</span>
          </div>
        </div>

        <div class="cert-card">
          <span class="cert-icon">⎈</span>
          <div>
            <div class="cert-name">Certified Kubernetes Administrator</div>
            <div class="cert-meta">Scheduled April 2026</div>
            <span class="cert-badge pending">Upcoming</span>
          </div>
        </div>

        <div class="cert-card">
          <span class="cert-icon">☁️</span>
          <div>
            <div class="cert-name">Azure Fundamentals AZ-900</div>
            <div class="cert-meta">Credential: I402-6928</div>
            <span class="cert-badge">Certified</span>
          </div>
        </div>

        <div class="cert-card">
          <span class="cert-icon">🔧</span>
          <div>
            <div class="cert-name">HashiCorp Terraform Associate</div>
            <div class="cert-meta">Credential: F3B8F05EB893</div>
            <span class="cert-badge">Certified</span>
          </div>
        </div>

        <div class="cert-card">
          <span class="cert-icon">📊</span>
          <div>
            <div class="cert-name">Prometheus Monitoring & Alerting</div>
            <div class="cert-meta">Credential: UC-83556853</div>
            <span class="cert-badge">Certified</span>
          </div>
        </div>

        <div class="cert-card">
          <span class="cert-icon">🖥️</span>
          <div>
            <div class="cert-name">Google IT Support Professional</div>
            <div class="cert-meta">Credential: AB6KQ5A5MPE4</div>
            <span class="cert-badge">Certified</span>
          </div>
        </div>

      </div>
    </section>

    <!-- ── FOOTER ── -->
    <footer>
      <p class="footer-note">All code is open source · All failures are documented · All lessons are shared</p>
      <div class="footer-links">
        <a href="https://github.com/ibraheemcisse" target="_blank">GitHub</a>
        <a href="https://linkedin.com/in/ibrahim-cisse-a2b6501a0/" target="_blank">LinkedIn</a>
        <a href="mailto:ibrahim.umar.cisse@gmail.com">Email</a>
      </div>
    </footer>
  </main>
</body>
</html>
