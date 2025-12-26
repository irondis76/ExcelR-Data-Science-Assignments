# Exploratory Data Analysis — Findings

## Dataset Summary
- **Records after cleaning:** 2,093  
- **Features:** 14 fetal heart-rate–related variables  
- **Target:** NSP (1=Normal, 2=Suspect, 3=Pathological)  
- **Data quality:** No missing values; class label cleanup performed  
- **Class imbalance:** Normal 77.8%, Suspect 14.0%, Pathological 8.2%

## Key Statistical Observations
- **Baseline FHR (LB):** Mean ~133 bpm; slight right skew  
- **Variability Measures:** MSTV mean 1.36, MLTV mean 8.31 → wide variation across cases  
- **Decelerations:** Generally low values; several features strongly right-skewed  
- **Overall trend:** Most distributions right-skewed, especially accelerations and fetal movements

## Correlation Highlights
- **Most correlated with NSP:**  
  1. ASTV (r ≈ 0.44)  
  2. ALTV (r ≈ 0.38)  
  3. DP (r ≈ 0.32)  
  4. LB (r ≈ 0.14)  
- **Insight:** Higher abnormal variability and prolonged decelerations → higher likelihood of pathological outcomes  
- **Feature relationships:** Variability measures are moderately correlated with each other, reflecting related physiological signals

## Patterns by Class
- **Normal (NSP=1):** Higher MSTV & MLTV, lower ASTV & ALTV, LB concentrated around 130–135 bpm  
- **Suspect (NSP=2):** Intermediate values between normal and pathological cases  
- **Pathological (NSP=3):** Lowest variability, highest abnormal variability measures, slightly higher spread in LB

## Visualization Takeaways
- **Histograms:** LB nearly normal; others skewed  
- **Box/Violin plots:** Variability measures separate classes well  
- **Scatter/Pair plots:** MSTV–MLTV relationship visually distinguishes NSP groups

---

## Findings and Conclusion
1. **Abnormal variability measures (ASTV, ALTV)** are the strongest indicators of fetal health classification and should guide modeling focus.  
2. **Clear separation of classes** in multiple features suggests that predictive models can capture meaningful patterns.  
3. **Strong class imbalance** means modeling must account for minority classes to accurately detect pathological cases.  
4. **Most informative features:** ASTV, ALTV, DP, LB, and FM due to their consistent relationship with NSP outcomes.  
5. **Modeling direction:** use variability-focused features, apply imbalance-handling methods, and prioritize recall for pathological cases where clinical risk is highest.
