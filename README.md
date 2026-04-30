# starbucks-customer-analytics
Sajid's Starbucks projects 
# ============================================================
# STARBUCKS CUSTOMER ANALYTICS & OFFER EFFECTIVENESS
# Author: Sajid Khan
# Dataset: Starbucks Dataset (Kaggle) 
# Tools: Python, Pandas, Matplotlib, Seaborn
# ============================================================
#
# BUSINESS QUESTION:
# Starbucks sent 10 different promotional offers to 17,000 customers
# through their app. Which offers work? On which customers?
# Can we segment customers to target them more effectively?
#
# DATASETS:
#   portfolio.csv  — 10 offer types (BOGO, Discount, Informational)
#   profile.csv    — 17,000 customer demographics
#   transcript.csv — 306,534 events (offers sent, viewed, completed, purchases)
# ============================================================

import pandas as pd
import matplotlib
import matplotlib.pyplot as plt
import seaborn as sns
import ast
import os
 
matplotlib.use('Agg')  # Use non-interactive backend for saving plots
os.makedirs('outputs', exist_ok=True)
print("=" * 60)
print("SECTION 1: LOADING DATA")
print("=" * 60)
 
portfolio  = pd.read_csv('data/portfolio.csv').drop(columns=['Unnamed: 0'], errors='ignore')
profile    = pd.read_csv('data/profile.csv').drop(columns=['Unnamed: 0'], errors='ignore')
transcript = pd.read_csv('data/transcript.csv').drop(columns=['Unnamed: 0'], errors='ignore')
 
print(f"Portfolio  : {portfolio.shape[0]} rows, {portfolio.shape[1]} columns")
print(f"Profile    : {profile.shape[0]} rows, {profile.shape[1]} columns")
print(f"Transcript : {transcript.shape[0]} rows, {transcript.shape[1]} columns")
