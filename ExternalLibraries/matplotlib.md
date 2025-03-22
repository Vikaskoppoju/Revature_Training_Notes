# 🎨 **Matplotlib📊🚀**  

Matplotlib is an amazing **data visualization library** in Python. Whether you're working with **line plots, bar charts, scatter plots, histograms, or pie charts**, Matplotlib has got you covered! 🖌️✨  
 

---

# **📌 1. Installation & Setup**
Before we begin, let's ensure that **Matplotlib** is installed.

```python
!pip install matplotlib
```
Now, let's **import** Matplotlib and enable inline plotting in Jupyter Notebook.

```python
import matplotlib.pyplot as plt
import numpy as np

# Enable inline plots in Jupyter Notebook
%matplotlib inline  
```

🔹 **`%matplotlib inline`** ensures that plots are displayed **inside the notebook** instead of a separate window.

---

# **📊 2. Creating a Simple Line Plot**  
Let’s start with a basic **temperature trend visualization** 🌡️.

```python
# Temperature data over a week
days = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]
temperature = [30, 32, 33, 31, 29, 28, 27]

plt.plot(days, temperature, marker="o", linestyle="--", color="red", linewidth=2, markersize=8, label="Temperature (°C)")
plt.xlabel("Days of the Week")
plt.ylabel("Temperature (°C)")
plt.title("📈 Temperature Trend Over the Week")
plt.legend()
plt.grid(True)
plt.show()
```

### **🔹 Key Features Used:**
✅ **`marker="o"`** → Adds circular markers for each data point  
✅ **`linestyle="--"`** → Dashed line style  
✅ **`color="red"`** → Line color  
✅ **`legend()`** → Shows a label for the plot  
✅ **`grid(True)`** → Adds a background grid  

---

# **📊 3. Scatter Plot - Social Media Followers Growth 📱**
A scatter plot is great for showing **trends** and **correlations**. Let’s visualize **Instagram follower growth** over 10 months.

```python
months = np.arange(1, 11)  # 10 months
followers = [1000, 2500, 3000, 6000, 7500, 11000, 15000, 20000, 26000, 30000]
colors = np.random.rand(10)

plt.scatter(months, followers, c=colors, cmap="viridis", edgecolor="black", s=100)
plt.xlabel("Months")
plt.ylabel("Followers Count")
plt.title("📲 Instagram Follower Growth Over 10 Months")
plt.colorbar(label="Growth Intensity")
plt.show()
```
### **🔹 Key Features Used:**
✅ **`scatter()`** → Creates a scatter plot  
✅ **`cmap='viridis'`** → Applies a color map  
✅ **`edgecolor='black'`** → Outlines points for clarity  
✅ **`colorbar()`** → Adds a color scale  

---

# **📊 4. Bar Chart - Monthly Sales Report 🛍️**
Let’s visualize **monthly sales of a fashion store** using a **bar chart**.

```python
months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun"]
sales = [5000, 7000, 8000, 6500, 9000, 10000]

plt.bar(months, sales, color=["red", "green", "blue", "orange", "purple", "cyan"])
plt.xlabel("Months")
plt.ylabel("Sales ($)")
plt.title("🛒 Monthly Sales Report")
plt.show()
```
### **🔹 Key Features Used:**
✅ **`bar()`** → Creates a bar chart  
✅ **Custom Colors** → Makes visualization more engaging  

---

# **📊 5. Histogram - Exam Scores Distribution 📚**
A histogram is useful for understanding **data distributions**. Let’s visualize **students' exam scores**.

```python
exam_scores = np.random.randint(50, 100, 200)  # 200 students' scores

plt.hist(exam_scores, bins=10, color="blue", edgecolor="black", alpha=0.7)
plt.xlabel("Scores")
plt.ylabel("Number of Students")
plt.title("📚 Exam Score Distribution")
plt.show()
```

### **🔹 Key Features Used:**
✅ **`hist()`** → Creates a histogram  
✅ **`bins=10`** → Groups scores into 10 bins  
✅ **`alpha=0.7`** → Adjusts transparency  

---

# **📊 6. Pie Chart - Market Share of Smartphone Brands 📱**
A pie chart is useful for showing **proportions**. Let’s visualize **smartphone market share**.

```python
brands = ["Apple", "Samsung", "Xiaomi", "OnePlus", "Others"]
market_share = [40, 30, 15, 10, 5]
colors = ["gold", "lightblue", "red", "green", "grey"]

plt.pie(market_share, labels=brands, colors=colors, autopct="%1.1f%%", startangle=140, shadow=True)
plt.title("📊 Smartphone Market Share")
plt.show()
```
### **🔹 Key Features Used:**
✅ **`pie()`** → Creates a pie chart  
✅ **`autopct="%1.1f%%"`** → Displays percentages  
✅ **`shadow=True`** → Adds a shadow effect  

---

# **📊 7. Multiple Plots in One Figure - Weather Trends ☀️🌧️**
Let’s compare **temperature** and **humidity** over 7 days in a **single figure**.

```python
days = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]
temperature = [30, 32, 33, 31, 29, 28, 27]
humidity = [80, 75, 78, 72, 70, 68, 65]

fig, ax = plt.subplots(2, 1, figsize=(6, 6))  # 2 rows, 1 column

ax[0].plot(days, temperature, marker="o", color="red", linestyle="--", label="Temperature (°C)")
ax[0].set_title("🌡️ Temperature Over the Week")
ax[0].legend()
ax[0].grid(True)

ax[1].plot(days, humidity, marker="s", color="blue", linestyle="-", label="Humidity (%)")
ax[1].set_title("💧 Humidity Over the Week")
ax[1].legend()
ax[1].grid(True)

plt.tight_layout()
plt.show()
```
### **🔹 Key Features Used:**
✅ **`subplots()`** → Creates multiple plots  
✅ **Custom markers for each plot**  
✅ **`tight_layout()`** → Prevents overlapping  

---

# **🚀 Summary - What Have We Learned?**
✅ **Matplotlib is powerful for data visualization**  
✅ **We created engaging plots (line, scatter, bar, histogram, pie, multi-plots)**  
✅ **Customization makes plots more informative**  
✅ **Matplotlib is useful for business reports, social media growth, exam analysis, and more!**  
