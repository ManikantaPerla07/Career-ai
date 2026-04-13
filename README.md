# AI Career Guidance System

AI Career Guidance System is a full-stack machine learning web application that recommends top career paths based on aptitude and performance inputs.

Live app:
https://career-ai-wefq.onrender.com

Repository:
https://github.com/ManikantaPerla07/Career-ai

## Highlights

- End-to-end ML-powered career recommendation workflow
- Top 5 career predictions with confidence scores
- 8 aptitude dimensions and 8 performance indicators
- Flask backend serving both API and frontend pages
- Ready for one-service cloud deployment

## How It Works

1. User completes aptitude and performance assessment.
2. Backend performs feature engineering.
3. Gradient Boosting model predicts probabilities across careers.
4. Application returns ranked top predictions.

## Model Summary

- Algorithm: Gradient Boosting Classifier
- Input design: 25 total features
- Output: Ranked top 5 careers with confidence percentages
- Detailed report: backend/model_summary_report.txt

## Tech Stack

- Python, Flask, Flask-CORS
- scikit-learn, NumPy, pandas, joblib
- HTML, Tailwind CSS, JavaScript
- Gunicorn for production serving

## Project Structure

    career-ai/
    ├── assets/
    │   ├── css/
    │   └── js/
    ├── backend/
    │   ├── app.py
    │   ├── career_prediction_model.joblib
    │   ├── feature_order.json
    │   ├── label_encoder.joblib
    │   ├── model_summary_report.txt
    │   └── requirements.txt
    ├── about.html
    ├── contact.html
    ├── features.html
    ├── index.html
    ├── test.html
    ├── Procfile
    ├── render.yaml
    └── requirements.txt

## API Endpoints

- GET /health
- GET /careers
- POST /predict

Sample predict payload:

    {
      "aptitudes": {
        "linguistic": 12,
        "musical": 10,
        "bodily": 11,
        "logical_mathematical": 15,
        "spatial_visualization": 14,
        "interpersonal": 13,
        "intrapersonal": 12,
        "naturalist": 11
      },
      "performance": {
        "project_performance": "AVG",
        "practical_skills": "AVG",
        "research_interest": "AVG",
        "communication_skills": "AVG",
        "leadership_qualities": "AVG",
        "teamwork": "AVG",
        "time_management": "AVG",
        "self_learning": "AVG"
      }
    }

## Run Locally

1. Clone the repository

       git clone https://github.com/ManikantaPerla07/Career-ai
       cd Career-ai

2. Create and activate virtual environment

       python -m venv .venv
       .venv\Scripts\activate

3. Install dependencies

       pip install -r requirements.txt

4. Start the app

       python backend/app.py

5. Open in browser

       http://127.0.0.1:5000

## Deployment

This project is configured for Render as a single web service where backend and frontend are served together.

- Build command: pip install -r requirements.txt
- Start command: gunicorn backend.app:app
- Python version is pinned in render.yaml

## Troubleshooting

- If deploy fails with dependency issues, ensure backend/requirements.txt and requirements.txt are in sync.
- If static files do not load, verify assets are available under /assets.
- If model load fails, confirm all joblib/json artifacts are committed in backend.

## Roadmap

- Explainable AI outputs for recommendations
- User accounts and saved assessment history
- Improved analytics dashboard
- Enhanced mobile UX

## Author

Manikanta Perla

Email: careerai.help@gmail.com

## License

This project is intended for educational and academic use.

Your app will be accessible at: https://your-app-name.onrender.com
