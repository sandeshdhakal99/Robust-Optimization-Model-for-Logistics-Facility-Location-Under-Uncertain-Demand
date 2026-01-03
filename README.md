# Robust Optimization Model for Logistics Facility Location Under Uncertain Demand

This project implements and extends a **robust Mixed‑Integer Linear Programming (MILP)** model for logistics facility location under uncertain demand. Inspired by Chen et al. (2020), the model is built in **Python using Google OR‑Tools** and incorporates multi‑scenario demand, facility disruptions, and unmet demand penalties to support resilient supply chain planning.

---

## Project Overview
Modern supply chains face volatile demand, capacity disruptions, and operational uncertainty. Traditional deterministic models often fail under stress. This project reconstructs a robust optimization model that:

- Selects optimal facility locations  
- Allocates shipments across multiple demand scenarios  
- Minimizes the **worst‑case total cost**  
- Allows unmet demand at a penalty  
- Simulates facility shutdowns and capacity reductions  

The result is a flexible, realistic decision‑support tool for logistics planners.

---

## Key Features
### **1. Robust MILP Model**
- Multiple demand scenarios: Base, Peak, and Facility Disruption  
- Scenario‑specific capacities and disruptions  
- Worst‑case cost minimization  
- Binary facility decisions and shipment allocation variables  

### **2. Model Extension**
- Introduces unmet demand variables  
- Adds penalty cost for unfulfilled demand  
- Allows trade‑offs between cost and service level  
- Improves feasibility under extreme conditions  

### **3. Implementation in Python (Google OR‑Tools)**
- MILP formulation using `pywraplp`  
- Scenario‑based constraints  
- Automated extraction of optimal facility and shipment decisions  
- Modular code for easy experimentation  

### **4. Sensitivity Analysis**
Three major stress tests were conducted:

- **Penalty cost variation**  
- **Peak demand increases**  
- **Facility capacity reductions**  

These analyses reveal how the model adapts to uncertainty and when it becomes optimal to open additional facilities or tolerate unmet demand.

---

## Model Structure
### **Sets**
- Facilities (F1, F2, F3)  
- Customers (C1–C4)  
- Scenarios (Base, Peak, Disruption)

### **Decision Variables**
- `y[i]`: Facility open/close  
- `x[i,j,s]`: Shipment quantity  
- `u[j,s]`: Unmet demand  
- `Z[s]`: Scenario cost  
- `Zmax`: Worst‑case cost  

### **Objective**
Minimize  
\[
Z_{\max}
\]

### **Constraints**
- Demand satisfaction (with unmet demand)  
- Scenario‑specific capacity limits  
- Cost calculation per scenario  
- Binary and non‑negativity constraints  

---

## Results Summary
### **Original Model**
- Required full demand fulfillment  
- Less flexible under disruptions  
- Could become infeasible in extreme scenarios  

### **Extended Model**
- Allows unmet demand with penalties  
- Handles facility shutdowns and capacity drops  
- Produces more realistic, resilient decisions  
- Demonstrates clear cost‑service trade‑offs  

### **Key Insights**
- Penalty cost strongly influences facility openings  
- F3 is consistently the most strategic facility  
- Under high demand or reduced capacity, backup facilities activate  
- The model behaves robustly across all tested scenarios  

---

## Tools & Technologies
| Tool | Purpose |
|------|---------|
| **Python** | Model implementation |
| **Google OR‑Tools** | MILP solver |
| **NumPy / Pandas** | Data handling |
| **Matplotlib** | Sensitivity analysis visualization |

---

## Project Structure
```
/Robust-Facility-Location
│── data/                 # Synthetic demand, cost, and capacity data
│── notebooks/            # Jupyter notebooks for analysis
│── src/                  # Python implementation (OR-Tools)
│── results/              # Sensitivity analysis outputs
│── README.md             # Documentation
```

---

## Managerial Implications
- Robust optimization provides stronger resilience than deterministic models  
- Penalty‑based unmet demand modeling reflects real‑world trade‑offs  
- Scenario planning helps anticipate disruptions before they occur  
- Backup capacity becomes quantifiably justified  
- Open‑source tools like OR‑Tools offer powerful, cost‑effective analytics  

---


---

## ⭐ If you find this project useful, feel free to star the repository!
