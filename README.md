**Sasaki charonda Habitat Suitability Viewer:** https://tana-ris.github.io/SC-habitat/

<img width="1919" height="910" alt="image" src="https://github.com/user-attachments/assets/7b31f1a7-f2ba-473c-a583-b8c38292ba44" />

# SC-habitat
Machine-learning and XAI framework for habitat suitability of *Sasakia charonda*, with a lightweight Leaflet web map viewer.

## Paper (under review)
**What Factors Determine *Sasakia charonda* Habitat?**  
Yuya Tanaka*, Takafumi Sato**, Shintaro Goto*** (submitted)

**One-sentence summary:**  
We integrate ML and SHAP to assess habitat suitability in Namegawa Town, identifying overwintering microclimate, host tree maturity, and forest-floor cover as the primary axes; Random Forest performs best (AUC ≈ 0.720) and practical thresholds emerge around ~5 cm litter depth, ~40 cm DBH, and ~40% ground vegetation cover.

---

## Repository structure (minimal)

```
SC-habitat/
├─ viewer/                  # Leaflet map (raster + GeoPackage overlays)
│  └─ index.html
├─ data/                    # Not tracked: *.gpkg, Elevation.tif, waterfall/*.png
└─ README.md
```

---


## Methods (very brief)

- **Models compared (12):** RF, ET, GBDT/HGB, XGBoost, LightGBM, CatBoost, AdaBoost, KNN, SVM, LR, NB, etc.  
- **Best model:** Random Forest (AUC ≈ 0.720).  
- **Cross-validation:** Outer **Stratified Group K-fold** (spatial groups) + inner **Stratified K-fold** with ~30 trials for hyperparameter tuning.  
- **Imbalance handling:** **SMOTE** on **training folds only**.  
- **Explainability:** **SHAP** (global / univariate / local). Thresholds near **LDepth ≥ ~5 cm**, **DBH ≥ ~40 cm**, **VegCover ≥ ~40%**.


## Citation

Tanaka, Y., Sato, T., & Goto, S. (2025). *What Factors Determine Sasakia charonda Habitat?* (under review).

---

## License

- **Code:** MIT  
- **Text/Docs:** CC BY 4.0  
- **Data:** Follow original providers’ terms.
