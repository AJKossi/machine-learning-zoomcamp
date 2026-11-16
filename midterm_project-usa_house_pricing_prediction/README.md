# USA House Price Prediction

## 1. Project Description
A Machine Learning project that predicts residential house prices in the United States based on property characteristics.

## 2. Business Problem and Objectives
House prices depend on several factors, including location, property size, construction quality, and available facilities.

**Objectives:**
- Analyze and prepare housing data.
- Identify important price predictors.
- Train and evaluate regression models.
- Develop an API for house price predictions.
- Containerize and deploy the application.

## 3. Dataset Description and Source
**Dataset:** Ames Housing – Advanced Regression Techniques.

**Source:** [Kaggle – House Prices Competition](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data)

- Training records: 1,460
- Testing records: 1,459
- Features: 79 explanatory variables
- Target: `SalePrice`
- Currency: USD
- Location: Ames, Iowa, USA

## 4. Technologies Used
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn, XGBoost
- Jupyter Notebook
- FastAPI
- Joblib
- Docker

## 5. Installation Instructions

Clone the repository:

```bash
git clone <repository-url>
cd usa-house-price-prediction
```

Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Download the Kaggle dataset and place its files in `data/raw/`.

## 6. Train the Model

Run the training script:

```bash
python src/train.py
```

The trained model will be saved in the `models/` directory.

## 7. Launch the API

Start the FastAPI service:

```bash
uvicorn src.predict:app --reload
```

API documentation:

http://localhost:8000/docs

## 8. API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | API information |
| GET | `/health` | Health check |
| POST | `/predict` | Predict house price |

Example request:

```json
{
  "OverallQual": 7,
  "GrLivArea": 1800,
  "TotalBsmtSF": 900,
  "FullBath": 2,
  "BedroomAbvGr": 3,
  "YearBuilt": 2005,
  "GarageCars": 2,
  "LotArea": 8500
}
```

Example response:

```json
{
  "predicted_price": 285000,
  "currency": "USD"
}
```

*The request fields are illustrative; the final API schema will depend on the trained model's preprocessing pipeline.*

## 9. Docker Instructions

Build the Docker image:

```bash
docker build -t house-price-api .
```

Run the container:

```bash
docker run -p 8000:8000 house-price-api
```

## 10. Deployment and Demonstration

- Deployment URL: To be added.
- API documentation: To be added.
- Demonstration video: To be added.

---

**Project Status:** In Development

**Machine Learning Task:** Supervised Regression