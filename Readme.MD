# 🚀 DevOps Implementation: Jenkins, EKS & SonarQube Integration

## 🔧 Jenkins Setup

### Infrastructure Setup
- Created Jenkins **Master and Agent EC2 instances**
- Configured **Route 53 (R53)** records for access

### 🔌 Installed Plugins
- Pipeline Stage View  
- Pipeline Utility Steps  
- AWS Credentials  
- AWS Steps  
- Rebuild  
- Ansi Color  
- SonarScanner  

> 🔄 Restarted Jenkins after plugin installation

---

## 🔐 Credentials Management

Configured required credentials in Jenkins:

- **SSH Credentials** (for agent connection)  
  - ID: `ssh-auth`

- **AWS Credentials** (for deployments)  
  - `aws-creds`  
  - `aws-creds-dev`  
  - `aws-creds-prod`

- **SonarQube Credentials**  
  - Generated token from SonarQube server  
  - ID: `sonar-auth`

---

## ⚙️ Jenkins Configuration

### 🔗 Master-Agent Setup
- Configured secure connection between Jenkins master and agents

### 🔍 SonarQube Integration
- Installed and configured **SonarScanner**
- Connected Jenkins with SonarQube server

### 📦 Shared Libraries
- Configured global pipeline library:

---

## ☸️ EKS Setup

- Ensured `roboshop` namespace exists
- Allowed Jenkins agent access to **EKS control plane (port 443 HTTPS)**

---

# 🔎 SonarQube Quality Metrics

| Metric | Description |
|------|------------|
| 🔴 Bugs | Runtime errors that affect application behavior |
| 🟠 Code Smells | Poor coding practices affecting maintainability |
| 🟡 Coverage | % of code covered by tests |
| 🟣 Issues | Total = Bugs + Smells + Vulnerabilities |
| 🟢 Maintainability Rating | Code maintainability grade (A–E) |
| 🔐 Security Rating | Security grade (A–E) |
| 🛡️ Vulnerabilities | Security weaknesses exploitable by attackers |

---

# 🚀 SonarQube Implementation Journey

## 📌 Overview
Initially, the project had **no code quality checks**.  
I led the initiative to implement SonarQube across all components.

---

## 🟢 Phase 1 – Initial Setup (Month 1)

- Installed and configured SonarQube server
- Integrated SonarQube with Jenkins pipelines
- Created projects in SonarQube
- Asked teams to add `sonar-project.properties`
- Ran initial scans to generate baseline reports

🎯 **Goal:** Visibility without blocking developers

---

## 🟡 Phase 2 – Developer Adoption (Months 2–3)

- Educated developers on reading reports
- Set 2.5 months timeline to fix issues
- Conducted weekly tracking sessions
- Encouraged:
  - Unit testing
  - Code refactoring
  - Removing duplications
  - Fixing vulnerabilities

---

## 🔴 Phase 3 – Quality Gate Enforcement (Months 3–4)

- Introduced Quality Gates in CI/CD pipeline
- Initially: warning mode (no failure)
- Gave 2 weeks buffer
- Later: enforced strict rules

🚨 Pipeline fails if:
- Bugs exist  
- Coverage below threshold  
- Security issues found  

---

# 📈 Outcome

- ✅ Standardized code quality across projects  
- ✅ Improved test coverage (~80%)  
- ✅ Reduced vulnerabilities  
- ✅ Improved maintainability  
- ✅ Developers became self-reliant  

🏆 **Awarded Best Performer for this implementation**

---

#  Key Skills Demonstrated

- CI/CD Integration (Jenkins + SonarQube)  
- DevSecOps Practices  
- Change Management Strategy  
- Developer Collaboration  
- Code Quality & Security Enforcement  

---

#  Real-time Usage / Scenario

In a real project:
- Developer pushes code → Jenkins pipeline triggers  
- SonarQube scans code → checks quality & security  
- If Quality Gate fails → pipeline stops ❌  
- Developer fixes issues → re-run pipeline ✅  