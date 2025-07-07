Real-Time Smart Parking Dynamic Pricing System
Overview
This project implements a real-time dynamic pricing engine for smart parking systems. It leverages historical and live occupancy data to optimize parking prices using multiple models. Key features include robust data preparation, feature engineering, three pricing models, a real-time simulation pipeline, and interactive dashboards for visualization. The system is designed for extensibility, making it easy to integrate new features, models, or live data sources.

Table of Contents
Overview

Tech Stack

Architecture Diagram

Project Architecture & Workflow

Setup & Installation

Usage

Repository Structure

Working Code

Documentation

License

Contact & Acknowledgments

Tech Stack
Component	Technology/Libraries
Programming	Python 3.8+
Data Processing	pandas, numpy
Real-Time Engine	Pathway
Visualization	Bokeh, matplotlib
Machine Learning	scikit-learn (optional, for advanced models)
Utilities	Google Colab (optional), warnings
Architecture Diagram

flowchart TD
    A[Raw Parking Data (CSV)] --> B[Data Preparation & Feature Engineering]
    B --> C1[Baseline Linear Model]
    B --> C2[Demand-Based Model]
    B --> C3[Competitive Model]
    C1 & C2 & C3 --> D[Real-Time Pricing Engine]
    D --> E[Streaming Data Simulation (Pathway)]
    E --> F[Interactive Dashboard (Bokeh)]
    F --> G[User/Reviewer]
Project Architecture & Workflow
1. Data Preparation
Loads historical parking data from dataset.csv.

Cleans data, checks for missing values, and engineers features:

Occupancy rate, demand pressure, datetime parsing, hour, day of week, weekend flag.

2. Feature Engineering
Adds advanced features for demand and competitive pricing:

Queue length, traffic condition, special day indicator, vehicle type weighting.

Computes a distance matrix for competitive pricing using the Haversine formula.

3. Pricing Models
Baseline Linear Model: Sets price as a linear function of occupancy rate, bounded within 0.5x–2x base price.

Demand-Based Model: Considers occupancy, queue, traffic, special days, and vehicle type; normalizes demand and adjusts price.

Competitive Model: Inherits demand-based logic and adjusts price based on nearby competitor prices using the distance matrix.

4. Real-Time Processing
Simulates a real-time data stream using Pathway, replaying historical data in temporal order.

The RealTimePricingEngine processes each data point, applies all three models, and logs pricing history.

5. Visualization
Interactive Bokeh dashboard displays:

Real-time prices for each location.

Average occupancy rate over time.

Easily customizable to add more locations or metrics.

6. Extensibility
Modular codebase allows easy integration of new features, models, or live data sources.

The notebook is annotated for clarity and reproducibility.

Setup & Installation
Clone the repository:

bash
git clone https://github.com/yourusername/smart-parking-pricing.git
cd smart-parking-pricing
Install dependencies:

bash
pip install pathway==0.2.1 bokeh pandas numpy matplotlib
Prepare the dataset:

Place your dataset.csv file in the repository root directory.

Usage
Open the Jupyter notebook:


jupyter notebook SA_final_project.ipynb
Run all cells to:

Install dependencies

Load and explore data

Engineer features

Build and test pricing models

Simulate real-time streaming

Launch the interactive dashboard

Repository Structure

.
├── SA_final_project.ipynb    
├── dataset.csv            
├── README.md               
Working Code
All scripts and the main notebook (SA_final_project.ipynb) are present and tested to run without errors, provided the dataset is correctly formatted and placed as dataset.csv in the root directory.

Ensure all dependencies are installed as specified above.

Documentation
Notebook Annotations: The notebook contains detailed markdown cells explaining each step, model, and visualization.

Customization: Instructions are included for adding new features, tuning models, and integrating live data sources.

License
This project is licensed under the MIT License.

Contact & Acknowledgments

Acknowledgments: Built using Pathway, Bokeh, Pandas, and NumPy. Dataset structure inspired by smart city parking initiatives.
