
# Zomato Data Analysis 📊

This project explores customer preferences, cost patterns, and rating distributions using Zomato’s restaurant dataset. The analysis offers key insights into user behavior, online order trends, and restaurant types, enabling better business decisions in the food service industry.

---

## 📁 Dataset Used
- **File**: `Zomato data .csv`
- Contains details like:
  - Restaurant type
  - Cost for two
  - Ratings
  - Online order availability
  - Votes

---

## 📊 Key Analyses Performed

- **Data Cleaning**
  - Converted ratings to numeric by removing denominators.
  - Ensured no null values remain.

- **Type of Restaurant**
  - Countplot to determine most common types.
  - Result: Dining restaurants are the most preferred.

- **Votes vs. Restaurant Type**
  - Line plot of total votes by type.
  - Dining restaurants receive the most engagement.

- **Rating Distribution**
  - Histogram shows most ratings fall between 3.5 and 4.0.

- **Cost for Two**
  - Most restaurants fall into the ₹300 category.

- **Online vs Offline Ratings**
  - Boxplot comparison shows online orders receive better ratings.

- **Heatmap of Online Orders vs Restaurant Type**
  - Cafes receive more online orders.
  - Dining restaurants lean towards offline.

---

## 📎 Libraries Used
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

---

## 📌 How to Run

```bash
# Clone the repository
git clone https://github.com/PriyanshuM04/Zomato.git
cd Zomato

# Ensure Jupyter or any Python IDE is set up
# Open and run the notebook or script containing the analysis
```

---

## 📈 Sample Visuals
- Countplot of Restaurant Types
- Rating Distribution Histogram
- Boxplot of Online vs Offline Orders
- Heatmap: Restaurant Type vs Online Orders

---

## 📌 Conclusion Highlights
- Dining restaurants are the most popular.
- Online orders tend to have higher customer ratings.
- Cost-sensitive segments prefer mid-range restaurants (~₹300).
- User behavior varies between cafés and dine-in formats.

---

## 🤝 Contributions
Feel free to fork this project, add insights, or expand the analysis!

---

## 🧑‍💻 Author
**Priyanshu Mallick**  
[GitHub Profile](https://github.com/PriyanshuM04)
