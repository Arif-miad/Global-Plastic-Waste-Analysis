<body>
<p align="center">
  <a href="mailto:arifmiahcse952@gmail.com"><img src="https://img.shields.io/badge/Email-arifmiah%40gmail.com-blue?style=flat-square&logo=gmail"></a>
  <a href="https://github.com/Arif-miad"><img src="https://img.shields.io/badge/GitHub-%40ArifMiah-lightgrey?style=flat-square&logo=github"></a>
  <a href="https://www.linkedin.com/in/arif-miah-8751bb217/"><img src="https://img.shields.io/badge/LinkedIn-Arif%20Miah-blue?style=flat-square&logo=linkedin"></a>

 
  
  <br>
  <img src="https://img.shields.io/badge/Phone-%2B8801998246254-green?style=flat-square&logo=whatsapp">
  
</p>


# Global Plastic Waste Analysis 2023 🌍

This project provides a comprehensive analysis of global plastic waste production and management for the year 2023, spanning 165 countries. The dataset presents insights into plastic waste handling, production volumes, recycling efficiency, and environmental risk assessment across different nations.

## 📄 Dataset Overview

The dataset offers an extensive look into plastic waste management, featuring:

- **Country-wise Plastic Waste Production**: Plastic waste production volumes (in million metric tons) for each country.
- **Main Sources of Plastic Waste**: Identification of primary sources contributing to plastic waste in each country.
- **National Recycling Rates**: Recycling efficiency rates (%) on a national level.
- **Per Capita Waste Production**: Waste generation per person (kg/person).
- **Coastal Waste Risk Assessment**: Evaluation of environmental risk for coastal regions impacted by plastic waste.

> **Note**: The data values are approximations derived from historical trends, AI-based large language models (LLM), economic indicators, and waste management patterns up to 2023. Actual figures may vary.

## 📊 Analysis Techniques

This project leverages machine learning models to provide deeper insights into the data, specifically applying the following classifiers:
- **RandomForestClassifier**: Used for analyzing various categorical and numerical features within the dataset.
- **CatBoostClassifier**: Applied for enhanced performance with categorical data, improving model interpretability.
- **World Map Visualizations**: Geographic plots are created to visually represent country-wise plastic waste production, recycling rates, and coastal waste risk.

## 🛠️ Installation and Requirements

To replicate the analysis, ensure you have the following libraries installed:

```bash
pip install pandas numpy scikit-learn catboost matplotlib geopandas
```

## 📂 Project Structure

- `data/`: Contains the dataset files.
- `notebooks/`: Jupyter notebooks with step-by-step analysis and model implementation.
- `src/`: Source files for data processing and model training.
- `visualizations/`: Contains world map visualizations and other graphical outputs.

## 🔍 Analysis Workflow

1. **Data Preprocessing**: Handle missing values, normalize the data, and encode categorical variables.
2. **Exploratory Data Analysis**: Generate statistical summaries and visualize country-wise plastic waste, recycling rates, and per capita waste production.
3. **Machine Learning Models**:
   - Apply `RandomForestClassifier` to predict recycling efficiency.
   - Use `CatBoostClassifier` for improved accuracy with categorical features.
4. **World Map Visualizations**: Use `geopandas` to create visual maps representing plastic waste production and coastal waste risk globally.
```python
plt.figure(figsize=(10,6))

index_values = [high_risk, low_risk, medium_risk, very_high_risk]
index_labels = ['High Risk', 'Low Risk', 'Medium Risk', 'Very High Risk']

plt.pie(index_values, labels = index_labels, autopct='%2.2f%%')

plt.title('Overall Coastal Risk Distribution', fontsize=20)

plt.show()
```
![overall coastal risk distribution](https://github.com/Arif-miad/Global-Plastic-Waste-Analysis/blob/main/p7.png)

```python
import geopandas as gpd
​
world = gpd.read_file(gpd.datasets.get_path('naturalearth_lowres'))
​
world = world.merge(df, left_on='name', right_on='Country', how='left')
​
fig, ax = plt.subplots(1, 1, figsize=(15, 10))
world.boundary.plot(ax=ax)
​
world.plot(column='Per_Capita_Waste_KG', ax=ax, legend=True, cmap='viridis',
           legend_kwds={'label': "Per_Capita_Waste_KG",
                        'orientation': "horizontal"})
​
plt.title('World Distribution of Per_Capita_Waste_KG', fontsize=16)
plt.show()
```
![world distribution of per_capita_waste_kg](https://github.com/Arif-miad/Global-Plastic-Waste-Analysis/blob/main/p6.png)

```python
import geopandas as gpd

world = gpd.read_file(gpd.datasets.get_path('naturalearth_lowres'))

world = world.merge(df, left_on='name', right_on='Country', how='left')

fig, ax = plt.subplots(1, 1, figsize=(15, 10))
world.boundary.plot(ax=ax)

world.plot(column='Recycling_Rate', ax=ax, legend=True, cmap='viridis',
           legend_kwds={'label': "Recycling_Rate",
                        'orientation': "horizontal"})

plt.title('World Distribution of Recycling_Rate', fontsize=16)
plt.show()
```
![world distribution of recyling _rate](https://github.com/Arif-miad/Global-Plastic-Waste-Analysis/blob/main/p5.png)


## 🚀 Getting Started

1. Clone this repository:
   ```bash
   git clone https://github.com/username/global-plastic-waste-analysis.git
   cd global-plastic-waste-analysis
   ```

2. Load and preprocess the dataset:
   - Open a Jupyter notebook or Python script and follow the steps in `notebooks/data_analysis.ipynb`.

3. Train and Evaluate Models:
   - Execute the code in `notebooks/model_training.ipynb` to train the `RandomForestClassifier` and `CatBoostClassifier`.

## 📈 Results

- Country-wise maps and graphs showcasing plastic waste production, recycling rates, and risk assessments.
- Model performance metrics (accuracy, F1-score, etc.) for both classifiers, highlighting feature importance and predictive insights.

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## 🤝 Contributions

Contributions are welcome! Please submit a pull request or open an issue for feedback or suggestions.

## 📬 Contact

For any inquiries, please reach out via [LinkedIn](https://www.linkedin.com/in/arif-miah-8751bb217/).

---



