# Beauty & Wellness Analytics - Week 3

## Data Cleaning and Preprocessing Pipeline Development

A robust, reproducible pipeline to clean raw Beauty & Wellness data and prepare it for analysis and modeling.

### Objective
Develop a data cleaning pipeline to handle missing values, duplicates, outliers, and inconsistencies, and perform normalization.

### Dataset
- **Products:** 5000 rows - product, category, brand, price, rating
- **Customers:** 8000 rows - age, skin_type, hair_type, city
- **Reviews:** 15000 rows - rating, review_text, purchase_date

### Pipeline Flow

Raw Data → Profiling → Missing Values → Duplicates → Outliers → Standardizing → Text Cleaning → Feature Engineering → Encoding + Scaling → Train-Test Split → Clean Data


### Key Steps
1. **Missing Values:** Price → Median, Skin Type → Mode, Review → "No Review"
2. **Duplicates:** `drop_duplicates()` on product + brand + size
3. **Outliers:** IQR Method, Price capped to 5000
4. **Standardizing:** Oily / oily / OILY → oily, Date → YYYY-MM-DD, Unit → ml
5. **Text Cleaning:** Lowercase, remove emoji, hashtag, extra spaces
6. **Feature Engineering:** `price_per_ml`, `is_premium`, `review_length`
7. **Scaling & Encoding:** One-Hot for skin_type, StandardScaler for price, age
8. **Split:** 80% Train, 20% Test

### Tools Used
Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, NLTK

### Installation
```bash
pip install -r requirements.txt
python clean_data.py
