#  Energy Consumption Forecasting App
This project forecasts energy consumption in **three distinct zones** using time series modeling. It supports both **10-minute** and **hourly** prediction intervals, enabling granular insights into regional energy demand.
##  Overview
The application leverages historical input data to predict future energy usage across three zones. It uses a trained deep learning model (`model.keras`) and preprocessing scalers to normalize inputs and outputs. The app is containerized with Docker and designed for deployment on platforms like Render.
##  Features

- Forecast energy consumption for Zone A, Zone B, and Zone C
- Supports both 10-minute and hourly prediction intervals
- Scalable backend powered by FastAPI (or Flask)
- Dockerized for easy deployment
- RESTful API endpoints for integration
- Preprocessing with saved scalers (`x_scaler.pkt`, `y_scaler.pkt`)
- Optional Jupyter notebook (`forecast.ipynb`) for experimentation

## Deployment
The application was deployed using [Render](https://render.com/) at:
**Live URL**: [https://energy-consumption-forecasting-euwq.onrender.com](https://energy-consumption-forecasting-euwq.onrender.com)

### API Testing
The `/predict` endpoint was tested using [Postman](https://www.postman.com/) with a `POST` request to:


#### Sample JSON Payload

json
{
  "input_data": [
    [6.559, 73.8, 0.083, 0.051, 0.119, 34055.69620, 16128.87538, 20240.96386],
    [6.414, 74.5, 0.083, 0.070, 0.085, 29814.68354, 19375.07599, 20131.08434],
    [6.313, 74.5, 0.080, 0.062, 0.100, 29128.10127, 19006.68693, 19668.43373],
    [6.121, 75.0, 0.083, 0.091, 0.096, 28228.86076, 18361.09422, 18899.27711],
    [5.921, 75.7, 0.081, 0.048, 0.085, 27335.69620, 17872.34043, 18442.40964],
    [5.780, 76.5, 0.080, 0.082, 0.094, 26581.89873, 17539.01215, 18048.79518],
    [5.750, 77.0, 0.083, 0.065, 0.080, 25930.69620, 17209.27051, 17764.09638],
    [5.690, 77.7, 0.081, 0.086, 0.091, 25290.12658, 16901.39817, 17445.78313],
    [5.600, 78.4, 0.080, 0.061, 0.077, 24729.49367, 16662.29482, 17182.65060],
    [5.450, 79.6, 0.083, 0.054, 0.068, 24224.17721, 16457.34340, 16899.27711]
  ],
  "window_size": 10,
  "n_features": 8
}
This payload represents a 10-step time window with 8 features per step. The model returns predicted energy consumption values for Zone A, Zone B, and Zone C.

## Sample Response
{
  "predictions": [
    [
      24485.77898039471,
      16534.77305121688,
      16684.36364400194
    ]
  ]
}

This response represents the predicted energy consumption for Zone A, Zone B, and Zone C, respectively.



