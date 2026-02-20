# Restaurant Menu Complexity & Ratings: Causal Inference Analysis

## Executive Summary

This project investigates whether menu complexity causally affects restaurant ratings using propensity score matching on Yelp data.

**Key Finding**: Complex menus INCREASE ratings by 0.1417 stars

- **Statistical Significance**: YES (p < 0.05)
- **Effect Size**: 0.130 (small)
- **Sample**: 8,724 matched restaurant pairs

## Project Structure
```
yelp_causal_inference_project/
|
+-- data/
|   +-- raw/                          # Original Yelp dataset files
|   +-- processed/                    # Cleaned and feature-engineered data
|   +-- validation/                   # Manual validation samples
|
+-- notebooks/
|   +-- 01_data_loading_and_exploration.ipynb
|   +-- 02_feature_engineering_menu_complexity.ipynb
|   +-- 03_exploratory_data_analysis.ipynb
|   +-- 04_causal_inference_analysis.ipynb
|   +-- 05_results_and_conclusions.ipynb
|
+-- outputs/
|   +-- figures/                      # All visualizations
|   +-- tables/                       # Results tables
|
+-- requirements.txt
+-- README.md
```

## Methodology

### 1. Data Collection
- **Source**: Yelp Open Dataset (Academic)
- **Initial Sample**: 17,625 restaurants
- **Final Sample**: 8,724 matched pairs

### 2. Treatment Variable
**Menu Complexity** - Binary variable based on composite score:
- Category diversity
- Review text signals
- Price range proxy
- Cuisine-specific patterns
- Business attributes

### 3. Outcome Variable
**Restaurant Rating** - Yelp stars (1-5 scale)

### 4. Confounders Controlled
- Cuisine type
- Price range
- Geographic location (city)
- Restaurant popularity (review count)

### 5. Causal Method
**Propensity Score Matching (PSM)**
- 1:1 nearest neighbor matching
- Common support enforced
- Covariate balance achieved: PARTIAL

## Key Results

### Main Finding
- **ATE**: +0.1417 stars
- **95% CI**: [0.1188, 0.1647]
- **P-value**: 0.0000

### Confounding Correction
- Naive estimate: +0.1867 stars
- Causal estimate: +0.1417 stars
- Correction: 0.0450 stars

### Robustness
- Covariate balance achieved: PARTIAL
- Consistent across alternative methods: YES
- Sensitivity analysis completed: YES

## Business Implications

**Recommendation: Embrace Menu Variety**

Diverse menu offerings drive higher ratings. Restaurants benefit from providing more options to customers.

## Technologies Used

- **Python 3.10+**
- **Analysis**: pandas, numpy, scipy
- **Visualization**: matplotlib, seaborn
- **Machine Learning**: scikit-learn
- **Statistical Methods**: Propensity score matching

## How to Reproduce

1. **Clone the repository**
```bash
git clone [your-repo-url]
cd yelp_causal_inference_project
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Download Yelp dataset**
- Visit https://www.yelp.com/dataset
- Download and extract to `data/raw/`

4. **Run notebooks in order**
- Start with `01_data_loading_and_exploration.ipynb`
- Progress through notebooks 02-05

## Limitations

1. **Causal assumptions**: Conditional independence may not hold
2. **Measurement**: Menu complexity is a proxy, not exact counts
3. **External validity**: Limited to Yelp restaurants in specific cities
4. **Cross-sectional**: Cannot observe menu changes over time

## Future Work

- Longitudinal analysis tracking menu changes
- Mechanism investigation (why complexity affects ratings)
- Experimental validation with restaurant partners
- Analysis of revenue and repeat visit outcomes

## Author

[Your Name]
[Your Contact/LinkedIn]

## License

This project is for educational and portfolio purposes.

## Acknowledgments

- Yelp for providing the open dataset
- [Any other acknowledgments]

---

*Last Updated: January 2026*
