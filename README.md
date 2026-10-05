# 📊 Tech Job Salary & Experience Predictor (2025-2026)

![AI Domain](https://img.shields.io/badge/Domain-Artificial%20Intelligence-blue?style=for-the-badge&logo=openai)
![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/ML-XGBoost%20%7C%20Random%20Forest-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)

Ushbu loyihada AI mehnat bozoridagi mutaxassislar maoshini va ularning tajriba darajasini aniqlovchi **Kaskadli Machine Learning (Cascaded ML Pipeline)** arxitekturasi ishlab chiqilgan.

## 🛠️ Loyiha Arxitekturasi va Ishlash Mantig'i

Tizim ma'lumotlar o'rtasidagi bog'liqlikni saqlash va ma'lumotlar sizib chiqishini (*data leakage*) oldini olish uchun kaskadli zanjir asosida ishlaydi:

```
[ Foydalanuvchi ma'lumotlari: Ko'nikmalar, davlat, soha, tajriba yillari ]
                           │
                           ▼
        ┌──────────────────────────────────────┐
        │  1-BOSQICH: XGBoost Regressor        │ ──► Maoshni bashorat qilish ($)
        └──────────────────────────────────────┘
                           │
                           ├─► [ Bashorat qilingan maosh ] ──┐
                           │                                 ▼
        ┌──────────────────────────────────────┐
        │ 2-BOSQICH: Random Forest Classifier  │ ──► Darajani aniqlash (Junior/Middle vs Senior/Lead)
        └──────────────────────────────────────┘
```

1. **XGBoost Regressor (1-Bosqich):** Nomzodning ko'nikmalari, davlati, shahar va kompaniya xajmi kabi xususiyatlar asosida bozor qiymatidagi yillik maoshni (`annual_salary_usd`) hisoblaydi.
2. **Random Forest Classifier (2-Bosqich):** Bashorat qilingan maoshni qo'shimcha belgi sifatida qabul qilib, nomzodning tajribasini `Junior/Middle` yoki `Senior/Lead` guruhlariga ajratadi.

## 📈 Model Metriklari va Natijalari

* **Maosh Bashorati (XGBoost Regressor):**
  * **R² Score:** `0.81` (Maosh o'zgaruvchanligining 81% qismini aniq tushuntiradi)
  * **MAE (O'rtacha mutloq xatolik):** `$21,078.71`
* **Tajriba Darajasini Tasniflash (Random Forest Classifier):**
  * **Umumiy aniqlik (Accuracy):** `73.67%`
  * **F1-Score (Junior/Middle):** `0.75`
  * **F1-Score (Senior/Lead):** `0.72`

## 📂 Loyiha Tarkibi
* `ai_jobs_market_predictor.ipynb` - To'liq tahlil va model noutbuki.
* `ai_jobs_market_2025_2026.csv` - Modelni o'qitishda foydalanilgan dataset fayli.
* `README.md` - Loyiha haqida batafsil ma'lumot.

## 🚀 Ishga tushirish

Ushbu loyihani mahalliy kompyuteringizda ishga tushirish uchun:
```bash
git clone https://github.com/Yasmina1602/Tech-Job-Salary-Predictor.git
cd Tech-Job-Salary-Predictor
pip install pandas numpy scikit-learn xgboost imbalanced-learn matplotlib seaborn
```
