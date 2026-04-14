Great call. Paste this as your full README.md for Career-ai:

# CareerAI - AI Career Guidance System

[![Live Demo](https://img.shields.io/badge/Live-Demo-blue.svg)](https://career-ai-wefq.onrender.com/)  
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)  
![Backend](https://img.shields.io/badge/Backend-Flask-black)  
![Deployment](https://img.shields.io/badge/Deploy-Render-46E3B7)

CareerAI is a full-stack machine learning web app that recommends top career paths from aptitude and performance inputs.  
It uses a trained Gradient Boosting model and serves both API endpoints and frontend pages from one Flask service.

Live app: https://career-ai-wefq.onrender.com/  
Repository: https://github.com/ManikantaPerla07/Career-ai

## Table of Contents

- Overview
- Feature Highlights
- Resume Highlights
- Architecture
- How It Works
- Tech Stack
- Project Structure
- API Reference
- Input Schema
- Run Locally
- Deploy on Render
- Troubleshooting
- FAQ
- Roadmap
- Author
- License

## Overview

CareerAI helps students and early professionals explore suitable career paths based on structured self-assessment data.

The system:
- Accepts aptitude and performance features
- Builds a model-aligned feature vector
- Predicts probability distribution across career classes
- Returns top 5 ranked recommendations with confidence scores

## Feature Highlights

- End-to-end ML recommendation workflow
- Top 5 career predictions with confidence percentages
- 8 aptitude dimensions + 8 performance indicators
- Feature engineering aligned with training pipeline
- Flask API with clean JSON responses
- Frontend and API served by a single backend service
- Render-ready deployment configuration

## Resume Highlights

- Built and deployed a production-style ML recommendation platform using Flask and scikit-learn
- Designed feature engineering pipeline with 25 model-aligned inputs
- Implemented top 5 probabilistic career ranking endpoint
- Delivered one-service architecture serving frontend pages and backend API
- Added operational readiness for cloud deployment and troubleshooting

Resume one-liner:

Developed and deployed a full-stack AI Career Guidance platform using Flask and Gradient Boosting to generate top-5 career recommendations with confidence scores from aptitude and performance inputs.

## Architecture

High-level flow:

1. User submits assessment from web UI  
2. Flask backend validates payload and engineers features  
3. Gradient Boosting classifier predicts class probabilities  
4. API returns ranked top 5 careers with confidence  
5. Same backend serves HTML pages and static assets

## How It Works

Input blocks:
- Aptitudes: numeric values for 8 dimensions
- Performance: categorical values for 8 indicators

Feature engineering:
- Raw aptitude values
- Raw performance encodings
- Total aptitude score
- Aptitude diversity
- Intelligence, creativity, social, physical indices
- Performance score and high-performer flag
- Optional cluster value

Output:
- Top 5 careers
- Rank and confidence percentage for each recommendation

## Tech Stack

Backend:
- Python
- Flask
- Flask-CORS
- Gunicorn

Machine Learning:
- scikit-learn
- NumPy
- pandas
- joblib

Frontend:
- HTML5
- Tailwind CSS
- JavaScript

Deployment:
- Render (single web service)

## Project Structure

    Career-ai/
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
    ├── requirements.txt
    └── README.md

## API Reference

### GET /api

Returns API metadata and endpoint summary.

### GET /health

Returns health status and model availability.

Example response:

    {
      "status": "OK",
      "model_loaded": true,
      "features_expected": 25
    }

### GET /careers

Returns all supported career labels and total count.

### POST /predict

Returns top 5 ranked predictions.

Sample request:

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
      },
      "cluster": 0
    }

Sample response:

    {
      "status": "success",
      "top_predictions": [
        {
          "rank": 1,
          "career": "Economist",
          "confidence": 31.11
        }
      ]
    }

## Input Schema

Aptitude keys:
- linguistic
- musical
- bodily
- logical_mathematical
- spatial_visualization
- interpersonal
- intrapersonal
- naturalist

Performance keys:
- project_performance
- practical_skills
- research_interest
- communication_skills
- leadership_qualities
- teamwork
- time_management
- self_learning

Allowed performance values:
- POOR
- AVG
- BEST

## Run Locally

1. Clone the repo

    git clone https://github.com/ManikantaPerla07/Career-ai
    cd Career-ai

2. Create and activate virtual environment (Windows)

    python -m venv .venv
    .venv\Scripts\activate

3. Install dependencies

    pip install -r requirements.txt

4. Start the app

    python backend/app.py

5. Open in browser

    http://127.0.0.1:5000

## Deploy on Render

This project is configured for single-service deployment.

Recommended settings:
- Environment: Python
- Build Command: pip install -r requirements.txt
- Start Command: gunicorn backend.app:app
- Config file: render.yaml

## Troubleshooting

If model fails to load:
- Ensure all artifact files exist in backend folder
- Confirm file names are unchanged
- Check logs for missing joblib or JSON files

If prediction fails with feature mismatch:
- Verify all required aptitude and performance keys are present
- Ensure performance values are POOR, AVG, or BEST
- Confirm backend feature engineering order was not modified

If static files do not load:
- Confirm assets exist under assets directory
- Verify route path is /assets/...
- Ensure app is running from repository root context

If deploy fails:
- Confirm root requirements.txt includes backend dependencies
- Re-check Render start command and Python environment

## FAQ

### Why top 5 predictions instead of one?
Model probabilities are more useful when presented as ranked options, not a single forced label.

### Is this suitable for final career decisions?
No. This is a guidance tool for educational use and should be combined with mentoring and real-world evaluation.

### Why do confidence scores not add to 100?
Only top-ranked classes are returned, not all possible career classes.

## Roadmap

- Explainability layer for recommendation rationale
- User accounts and saved history
- Enhanced analytics dashboard
- Better mobile UX
- Assessment personalization

## Author

Manikanta Perla  
Email: careerai.help@gmail.com

## License

This project is intended for educational and academic use.

---

If you want, I can also give you matching professional content for CONTRIBUTING.md and CHANGELOG.md in the same style so the whole repo looks consistent.
