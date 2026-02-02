# **🛒 Optimization or Friction? EU Recommendation System A/B Test**

### **📌 Project Overview:**
This project evaluates the performance of a new recommendation system interface for an e-commerce platform targeting the EU market. While the business goal was a 10% conversion lift, the analysis revealed a critical data integrity paradox that challenged the validity of the experiment.


### **🎯 Business Goals:**
Target Audience: New EU users.

Success Metric: 10% increase in conversion at every funnel stage (product_page → product_cart → purchase).

Test Duration: 14 days (Dec 7 - Dec 21, 2020).


### **🛠️ Technical Stack**
Language: Python

Libraries: Pandas (Data Manipulation), Matplotlib/Seaborn (Visualization), Statsmodels (Statistical Testing), NumPy.

Tools: Google Colab.


### **🔍 Key Finding: The "Broken Funnel":**
In Group A, the number of unique users who completed a purchase was higher than those who added items to their cart. This logical impossibility suggests that:
The legacy system has a tracking failure for product_cart events.
Users are utilizing a "Buy Now" shortcut that bypasses the traditional cart stage.

### **⚖️ Statistical Testing**
I performed a Z-Test for Proportions to validate the results:

Purchase Stage: $p$-value = 0.020 (Statistically significant).

Conclusion: Despite the $p < 0.05$, the result is a False Positive. The significance is driven by the corrupted baseline in Group A rather than the success of the new interface in Group B.

### **🚀 Strategic Recommendations**
Halt Rollout: The 10% lift target was not met, and the data environment is currently unreliable.
Infrastructure Audit: Technical investigation is required for Group A's event triggers.
UX Optimization: Data suggests EU users prefer "Fast-Track" checkout. Future iterations should focus on optimizing "One-Click Buy" features rather than just recommendation widgets.
