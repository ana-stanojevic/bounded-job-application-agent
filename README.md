# Bounded Job Application Agent

> Typical agents maximize activity.  
> This system maximizes **expected value under uncertainty, cost, and execution risk**.

Low-confidence opportunities are intentionally skipped.  
**Quality over quantity is a design choice.**

---

## 🧠 Overview

This project is a **decision-centric AI system** for job search and application.

Instead of blindly applying to jobs, the agent:
- evaluates opportunities under uncertainty  
- prioritizes based on expected value  
- executes selectively with bounded resources  
- keeps a human in the final loop  

---

## ⚙️ System Architecture

Intake → Ranking → Bounded Decision Runtime → Execution → Human Submit

<p align="center">
  <img src="https://raw.githubusercontent.com/ana-stanojevic/bounded-job-application-agent/main/assets/architecture.png" width="600"/>
</p>

---

## 🔁 Decision Process

The system separates **information gathering** from **decision making**.

First, it runs an internal loop:

- plan → select tool → execute → evaluate  

This loop may use tools (e.g. browser, retrieval) to reduce uncertainty and improve the estimate of expected value.

After sufficient confidence is reached, the system commits to a single decision:

- **Prepare application**  
- **Queue for later**  
- **Skip**  
- **Escalate to human**  


---
## 🔄 Learning & Adaptation

The system continuously updates its behavior based on outcomes.

- Ranking is updated based on observed success signals  
- Decision thresholds are adjusted over time  
- Retry and escalation policies evolve  

This forms a feedback loop that improves decision quality, not just execution throughput.

---

## 🔍 What Makes This Different

Most agents:
- maximize number of actions  
- ignore cost / uncertainty  
- over-execute  

This system:
- optimizes **expected value per action**  
- uses **policy gates + budget constraints**  
- treats execution as **expensive and risky**  
- explicitly models **confidence, cost, and downside**  

---

## 🧠 Decision Runtime

At the core is a bounded decision loop:

- state tracking  
- policy gating  
- expected value estimation  
- budget-aware execution  

Actions are not free — each one is evaluated before execution.

---

## 🧪 Example Run

120 jobs → 18 filtered → 6 shortlisted → 2 prepared → 1 escalated → 1 submitted

---

## 🛠️ Current Status

- 🚧 In build  
- ⏳ Demo coming soon  
 

---

## 📎 Notes

Human always makes the final submit decision.  
The system is designed for **decision quality, not throughput**.
