# 📊 Digital-Wallet-Failure-Analyst
### Understanding and Reducing Authentication Friction 


---

# 🧭 Why This Problem Matters

In modern payment systems, authentication is required for fraud prevention and compliance. However, layers such as 3DS and OTP introduce friction into the user journey.

This creates a fundamental trade-off:

> The same mechanisms that protect transactions can also prevent them from completing.

From a product perspective, this directly impacts:
- Conversion rate  
- Revenue realization  
- User experience  

This project focuses on answering:

> How much of payment failure is driven by authentication friction, and how much can be improved?

---

# 🔍 Framing the Investigation

Instead of treating failures as isolated events, this analysis approaches the payment flow as a system with bottlenecks.

Key objectives:
- Identify where friction accumulates  
- Quantify which failure types matter most  
- Understand user behavior under friction  
- Estimate the impact of targeted improvements  

The goal is not just reporting, but enabling decision-making.

---

# 🧱 Building the Analytical Layer

Using SQL, raw transaction data was transformed into structured datasets:

- Failure rate by time (hour-level)
- Error hierarchy (L1 → L2)
- Top failure contributors
- User attempt sequences (retry behavior)

This enables:
- Pattern detection  
- Root cause analysis  
- Scenario simulation  

---

# ⚠️ Where Failures Actually Come From

Failures are highly concentrated rather than evenly distributed.

A small number of error types drive most failures:

- **3DS Timeout** → primary contributor  
- **Invalid OTP** → secondary contributor  

Key implication:

> Fixing a few high-impact issues is more effective than optimizing everything equally.

---

# ⏱️ Friction Scales With Time

Authentication success is strongly correlated with duration.

By analyzing 3DS Duration:

- Short duration → high success rate  
- Longer duration → sharply increasing failure rate  

A clear inflection point appears at ~35 seconds.

> Beyond this threshold, failure probability increases significantly.

This shows that latency is a critical driver of failure.

---

# 🔁 Failures Are Not Always Final

User behavior analysis shows:

- Users who retry quickly often succeed  
- Success rate improves across attempts  

This indicates:
- Some failures are recoverable  
- Improving retry experience can increase success rate  

---

# 🧪 Scenario Simulation

To move from insight to action, a simulation layer was built in Power BI.

Instead of asking "what is happening", the model answers:

> What happens if we fix specific failure drivers?

### Inputs:
- % reduction in 3DS timeout  
- % reduction in OTP errors  

### Outputs:
- Projected failure rate  
- Impact contribution by driver  
- Scenario comparison  

---

# 📉 Key Findings From Simulation

- Improvements show diminishing returns  
- 3DS reduction has significantly higher impact than OTP improvements  

Key takeaway:

> 3DS is the primary bottleneck in the system.

---

# 🧠 Product Implications

### 1. Friction is the main constraint
Failures are driven by user interaction with authentication, not system randomness.

### 2. Time is a critical lever
Reducing authentication duration can significantly improve success rate.

### 3. Recovery is an opportunity
Better retry flows can convert failures into successes.

### 4. Prioritization is essential
Focus should be on high-impact drivers like 3DS.

---

# 🛠️ Tools & Technologies

- **SQL** → Data transformation and aggregation  
- **Power BI** → Visualization and simulation  
- **DAX** → Dynamic measures and scenario modeling  

---

# 📊 Visualization Strategy

The dashboard is designed to answer:

- Where is the problem? → Time & error breakdown  
- Why does it happen? → Duration & behavior  
- What should we do? → Simulation  

Key visuals:
- Failure rate by hour  
- Error distribution  
- Duration vs failure  
- Waterfall (impact breakdown)  
- Scenario line chart  

---

# 🚀 Final Takeaway

> Payment failure is primarily a friction problem within authentication flows.

Reducing 3DS-related friction provides the highest impact on improving success rate.

This project demonstrates how combining:
- Behavioral analysis  
- System thinking  
- Scenario modeling  

can drive actionable product decisions.

## 🔗 Live Dashboard  
👉 https://app.powerbi.com/groups/me/reports/58fb1c27-98f5-40d8-b7d6-aea29ffce121?ctid=5b98a1d4-abc3-42cd-896e-2e1b240dc662&pbi_source=linkShare
