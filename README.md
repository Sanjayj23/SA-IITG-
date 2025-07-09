# 🚗 Dynamic Parking Pricing Simulation

## 📄 Project Overview
This project implements a **dynamic pricing engine** for urban parking spaces using real-time data streams, designed for the **Summer Analytics 2025 Capstone Project** hosted by **Consulting & Analytics Club × Pathway**.

### ✅ Objective:
- Dynamically adjust parking prices using:
  - Occupancy
  - Queue Length
  - Traffic Congestion
  - Special Days
  - Vehicle Type
  - Competitor Prices

- Ensure:
  - Smooth & explainable price changes
  - Real-time price updates
  - Visualization of pricing behavior over time

---

## 📂 Dataset Details:
Collected from urban parking lots:
- **14 Locations**
- **73 Days**  
- **18 Time Points Per Day** (Every 30 min from 8:00 AM to 4:30 PM)
  
**Features:**
- Latitude, Longitude  
- Capacity & Occupancy  
- Queue Length  
- Traffic Level  
- Special Day Flag  
- Vehicle Type  
- Timestamp (Date + Time)

---

## 🧠 Models Implemented:
### 1️⃣ Baseline Linear Model:
- Simple price adjustment based on occupancy:
Price(t+1) = Price(t) + α × (Occupancy / Capacity)

### 2️⃣ Demand-Based Model:
Price adjusted based on a demand function considering multiple factors:
- Occupancy Rate
- Queue Length
- Traffic
- Special Day
- Vehicle Type  

> Price bounded between **0.5x** and **2x** of base price.

### 3️⃣ Competitive Model (Advanced):
- Adds competitor parking prices via location proximity.
- Adjusts prices based on:
  - Nearby parking lot prices.
  - Occupancy saturation.

---

## ⚙️ Technologies Used:
- **Python**
- **Pandas, Numpy** – Data Manipulation & Modeling  
- **Pathway** – Streaming Simulation  
- **Bokeh** – Real-time Visualization

---

## 📈 Visualization:
Real-time interactive plots showing:
- Baseline Price
- Demand-Based Price
- Competitive Price  

Plots show smooth price transitions over time, satisfying business constraints.

---

## 📝 How to Run:
1. Open `dynamic_parking_pricing.ipynb` in **Google Colab**.
2. Upload `dataset.csv` (provided).
3. Run all cells.
4. Interactive price graph will be displayed.

---

## 📊 Results:
- Smooth, realistic dynamic pricing.
- Clear comparison of 3 models.
- Prices adapt to demand and competition effectively.

---

## 🚀 Submission Prepared By:
- **Participant:** Sanjay Jangir 
- **Summer Analytics 2025 – Consulting & Analytics Club, IIT Guwahati**

---

