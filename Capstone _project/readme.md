#  Dynamic Pricing for Urban Parking Lots

**Capstone Project | Summer Analytics 2025  
Consulting & Analytics Club – IIT Guwahati**

---

##  Abstract

This project presents a real-time, data-driven pricing engine for 14 urban parking lots. The pricing models were developed using only Python, Pandas, and Numpy — simulating smart, demand-based pricing decisions without using any external machine learning libraries.

The solution dynamically adjusts parking fees based on features such as occupancy, queue length, traffic conditions, special day flags, and vehicle types, helping improve space utilization and revenue while reducing overcrowding.

---

##  Problem Statement

Urban parking spaces are limited and often mispriced. Static pricing fails to reflect real-time demand, resulting in:
- Overcrowded lots with no incentive to divert traffic
- Underutilized lots where fixed prices repel demand

The goal is to build **dynamic pricing models** that:
- Start with a base price ($10)
- Adjust prices in real-time based on demand indicators
- Provide a smoother, more intelligent pricing structure

---

##  Dataset Overview

- **Time span:** 73 days  
- **Time frequency:** Every 30 minutes (8:00 AM to 4:30 PM)  
- **Parking lots:** 14 unique locations  
- **Key features:**
  - `Occupancy`, `Capacity`, `QueueLength`
  - `TrafficConditionNearby` (low/average/high)
  - `IsSpecialDay` (holiday or event)
  - `VehicleType` (car, bike, truck)
  - `Timestamp` (from `date + time`)

---

##  Methodology

###  Model 1: Baseline Linear Model

**Formula:**  
\[
Price_{t+1} = Price_t + \alpha \cdot \left( \frac{Occupancy}{Capacity} \right)
\]

- Starts with base price $10  
- Increases linearly with occupancy  
- Simple reference model

---

###  Model 2: Demand-Based Pricing

**Demand Function:**  
\[
Demand = \alpha \cdot \left( \frac{Occupancy}{Capacity} \right) + \beta \cdot QueueLength - \gamma \cdot TrafficLevel + \delta \cdot IsSpecialDay + \epsilon \cdot VehicleWeight
\]

**Price Formula:**  
\[
Price = BasePrice \cdot (1 + \lambda \cdot \text{Normalized Demand})
\]

- Traffic conditions converted to numeric scale  
- Vehicle types weighted (e.g., truck > car > bike)  
- Prices capped between \$5 and \$20  

---

## Visual Results

We used `matplotlib` to generate:
- Time series plots of pricing for each model
- Comparative graphs for Model 1 vs. Model 2
- Observed smoother, more realistic pricing in Model 2


---

## How to Run

1. Clone the repository or upload the notebook to Google Colab.
2. Upload the dataset file: `dataset.csv`.
3. Run the notebook from top to bottom.
4. Visualizations and results will appear at the end.

>  No external ML libraries required — pure `pandas`, `numpy`, `matplotlib`.

---

##  Key Learnings

- Feature engineering for real-time demand prediction  
- Simulating time-series pricing behavior  
- Writing models from scratch using basic Python tools  
- Visualizing and comparing pricing strategies  
- Working with real-world constraints and optimization ideas

---

##  Author

**Radha Krishna**  
Capstone Participant, Summer Analytics 2025  
Aspiring AI & Data Science Engineer | Passionate about ML for real-world impact


