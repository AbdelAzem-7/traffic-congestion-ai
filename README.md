# Traffic Congestion Detection AI

An AI model that detects traffic congestion and predicts wait times using sensor data from Google Sheets.

## What This Project Does

This model reads real-time sensor data (distance sensors and PIR sensors) from a Google Sheet and:
* Predicts whether vehicles in each lane should MOVE or WAIT
* Estimates wait time in seconds
* Automatically prioritizes emergency vehicles

## How It Works

The model uses a neural network with:
* 7 input features (distance measurements, PIR states, ambulance presence)
* 2 hidden layers (32 neurons → 16 neurons)
* 2 outputs: Move/No-move + Wait time prediction

## Files in This Repository

| File | Description |
|------|-------------|
| traffic_model.ipynb | Main Jupyter notebook with the complete AI model code |

## Technologies Used

* TensorFlow / Keras for the neural network
* Google Sheets API for live data
* Pandas & NumPy for data processing
* Scikit-learn for evaluation metrics

## How to Run This Project

1. Open the notebook in Google Colab
2. Authenticate with Google Sheets (requires access to the "IntelligentRoad" sheet)
3. Run all cells to train and evaluate the model

## Model Performance

Based on 10 trials of real-world testing:

| Metric | Value | Details |
|--------|-------|---------|
| **Move/No-move Accuracy** | **93.5%** | Average across 10 trials (range: 89.5% - 96%) |
| **System Response Time** | **0.18 seconds** | Average (range: 0.1 - 0.3 seconds) |
| **Emergency Vehicle Priority Success Rate** | **97.5%** | Average across 10 trials (range: 94.2% - 100%) |

### Detailed Results

**System Time Response:**
* Sensor detection time: Real-time with ±0.01 sec precision
* AI response time: Real-time with ±0.01 sec precision  
* Total system response: 0.1 - 0.3 seconds (average 0.18s)

**AI Prediction Accuracy per Trial:**
| Trial | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|-------|---|---|---|---|---|---|---|---|---|---|
| Accuracy % | 89.5% | 91% | 94.75% | 92.5% | 94.5% | 93% | 95.5% | 94.5% | 96% | 93.5% |

**Emergency Vehicle (Ambulance) Prioritization per Trial:**
| Trial | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|-------|---|---|---|---|---|---|---|---|---|---|
| Priority % | 94.2% | 93.75% | 95.83% | 97.82% | 97.72% | 98.07% | 100% | 98.5% | 98.33% | 100% |

## Author

Malak Mohammed Abdelazem Mohammed Saad
malak1729admissions@gmail.com
