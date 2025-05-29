# House Price Prediction Web Application

![Flask](https://img.shields.io/badge/Flask-3.0.2-important)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.4.0-success)

A Flask-based web application that predicts housing prices using machine learning. The application includes both a web interface for interactive predictions and a REST API endpoint for programmatic access.

## Features
- Interactive web interface for real-time predictions
- REST API endpoint for integration with other applications
- Input data preprocessing using a pre-trained scaler
- Regression model serving with Scikit-Learn
- Simple and intuitive user interface

## Prerequisites
- Python 3.7+
- Required Packages
  ```bash
  Flask==3.0.2
  numpy==1.26.4
  pandas==2.2.0
  scikit-learn==1.4.0
```

## Installation
1. Clone the repository:

```bash
git clone https://github.com/yourusername/house-price-prediction.git
cd house-price-prediction
Create a virtual environment:
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate    # Windows
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```
---
## 📁 Project Structure
```
project-root/
├── app.py                  # Main application code
├── regmodel.pkl            # Pre-trained regression model
├── scaling.pkl             # Pre-fitted scaler
├── templates/
│   └── home.html           # Frontend template
├── requirements.txt        # Dependencies list
└── README.md
```
---
## 🧠 Running the Application

```bash
python app.py
```
The app will run at http://localhost:5000

**Web Interface**
1. Visit http://localhost:5000
2. Enter feature values in the form
3. Click "Predict" to see results

**API Endpoint**
Send POST requests to http://localhost:5000/predict_api with JSON input:
```json
{
  "data": {
    "feature1": value1,
    "feature2": value2,
    ...
  }
}
```
Example using curl:
```bash
curl -X POST http://localhost:5000/predict_api \
  -H "Content-Type: application/json" \
  -d '{"data": {"CRIM": 0.027, "ZN": 0.0, "INDUS": 7.07, "CHAS": 0, "NOX": 0.469, "RM": 7.185, "AGE": 61.1, "DIS": 4.967, "RAD": 2, "TAX": 242, "PTRATIO": 17.8, "B": 392.83, "LSTAT": 4.03}}'
```
Example Response:
```json
21.897
```

## Configuration
- Ensure regmodel.pkl and scaling.pkl are in the project root

- The app runs in debug mode by default (for development only)

- For production:

    - Set debug=False in app.run()

    - Use a production WSGI server (e.g., Gunicorn)

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
