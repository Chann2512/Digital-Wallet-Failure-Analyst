# 📊 Digital Wallet Failure Analysis  
### Quantifying and Reducing Authentication Friction in Payment Flows

---

## 🧭 Problem Context

In modern payment systems, authentication layers such as 3DS and OTP are essential for fraud prevention and regulatory compliance.  

However, these same mechanisms introduce friction into the user journey.

> The mechanisms designed to secure transactions can also become the primary reason they fail.

From a product perspective, this directly impacts:
- Conversion rate  
- Revenue realization  
- User experience  

This analysis aims to answer:

> To what extent are payment failures driven by authentication friction, and where should we intervene for maximum impact?

---

## 🔍 Analytical Approach

Rather than treating failures as isolated outcomes, this project models the payment flow as a system with identifiable bottlenecks.

The analysis focuses on:

- Locating where friction accumulates  
- Quantifying the dominant failure drivers  
- Understanding user behavior under failure conditions  
- Estimating the impact of targeted improvements  

The objective is not just descriptive analytics, but decision-oriented insight.

---

## 🧱 Data Modeling & Transformation

Using SQL, raw transaction data was transformed into analytical layers:

- Failure rate over time (hour-level granularity)  
- Hierarchical error classification (L1 → L2)  
- Top contributing failure drivers  
- User-level attempt sequencing (retry behavior)  

These datasets enable:
- Pattern detection  
- Root cause decomposition  
- Scenario-based simulation  

---

## ⚠️ Failure Concentration: A Small Number of Drivers Dominate

Failures are not evenly distributed.

Instead, they are highly concentrated in a few key error types:

- **3DS Timeout** → primary contributor  
- **Invalid OTP** → secondary contributor  

> A small number of failure modes account for a disproportionate share of total failures.

**Implication:**  
Targeting high-impact failure categories yields significantly higher ROI than broad optimizations.

---

## ⏱️ Authentication Latency as a Core Driver

Failure probability increases with authentication duration.

Analysis of 3DS duration reveals:

- Short duration → high success rate  
- Increasing duration → sharply rising failure probability  
- Clear inflection point at ~35 seconds  

> Beyond this threshold, user drop-off and timeout risk increase significantly.

**Implication:**  
Latency is not just a technical metric — it is a primary driver of conversion loss.

---

## 🔁 Failures Are Partially Recoverable

User behavior analysis shows:

- Users who retry quickly often succeed  
- Success rates improve across subsequent attempts  

This suggests:

- A portion of failures is recoverable  
- User behavior adapts under friction  

**Implication:**  
Improving retry flows and guidance can convert failed transactions into successful ones.

---

## 🧪 From Insight to Action: Scenario Simulation

To move beyond diagnosis, a simulation layer was developed in Power BI.

Instead of asking *“what is happening”*, the model answers:

> What is the expected impact if specific failure drivers are improved?

### Inputs:
- Reduction in 3DS timeout (%)  
- Reduction in OTP errors (%)  

### Outputs:
- Projected failure rate  
- Contribution by driver  
- Scenario comparison  

---

## 📉 Simulation Insights

- Improvements exhibit diminishing returns  
- Reducing 3DS timeout delivers significantly higher impact than OTP improvements  

> 3DS friction is the dominant constraint in the system.

---

## 🧠 Product Implications

### 1. Authentication friction is the primary constraint  
Failures are largely driven by user interaction with authentication flows, not random system errors.

### 2. Time is a critical lever  
Reducing authentication latency can directly improve conversion.

### 3. Recovery is an opportunity  
Well-designed retry experiences can recover otherwise lost transactions.

### 4. Prioritization drives impact  
Focusing on 3DS-related issues yields the highest return on effort.

---

## 🛠️ Tools & Technologies

- **SQL** → Data transformation & modeling  
- **Power BI** → Visualization & simulation  
- **DAX** → Dynamic measures & scenario modeling  

---

## 📊 Visualization Strategy

The dashboard is structured to answer three key questions:

- **Where is the problem?** → Time & error distribution  
- **Why does it happen?** → Duration & behavioral patterns  
- **What should we do?** → Scenario simulation  

Key visuals include:

- Failure rate by hour  
- Error distribution  
- Duration vs. failure rate  
- Impact waterfall chart  
- Scenario comparison line chart  

---

## 🚀 Final Takeaway

> Payment failure is fundamentally a friction problem within authentication flows.

Reducing 3DS-related friction presents the highest leverage opportunity to improve transaction success rates.

This project demonstrates how combining:
- Behavioral analysis  
- System-level thinking  
- Scenario modeling  

can drive actionable product decisions.

---

## 📷 Dashboard Preview

![Dashboard](https://github.com/user-attachments/assets/9e62e719-5440-4373-862b-a5c87623a8d8)

---

## 🔗 Live Dashboard

👉 [View on Power BI](https://app.powerbi.com/view?r=eyJrIjoiNDEzYmY5ODAtNjY4Ny00OTRhLWIxZmMtYzZiY2U0ZWVmYTE3IiwidCI6ImJlODMyOWE3LTcyMTgtNDlhMy05YWMxLWQ3Yjk1NDU2M2YzOSIsImMiOjEwfQ%3D%3D)
