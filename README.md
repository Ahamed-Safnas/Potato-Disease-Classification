# Potato Disease Classification

A machine learning project for classifying potato leaf diseases using deep learning and FastAPI for serving predictions.

## Project Structure

```
ahamed-safnas-potato-disease-classification/
├── api/
│   ├── main.py              # FastAPI application
│   └── requirements.txt     # API dependencies
├── training/
│   ├── PlantVillage/        # Dataset directory
│   │   ├── Potato___Early_blight/
│   │   ├── Potato___healthy/
│   │   └── Potato___Late_blight/
│   └── training.ipynb       # Jupyter notebook for model training
└── saved_models/
    └── 1.keras              # Trained model file
```

## Features

- **Image Classification**: Classifies potato leaves into three categories:
  - Early Blight
  - Late Blight  
  - Healthy
- **RESTful API**: FastAPI-based endpoint for predictions
- **Easy Integration**: Simple HTTP interface for integration with other applications

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Ahamed-Safnas/Potato-Disease-Classification.git
cd ahamed-safnas-potato-disease-classification
```

2. Install API dependencies:
```bash
cd api
pip install -r requirements.txt
```

## Usage

### Running the API

1. Start the FastAPI server:
```bash
cd api
python main.py
```

The API will be available at `http://localhost:8002`

### API Endpoints

#### Health Check
```bash
GET /ping
```
Response:
```json
{"message": "Hello, I am alive!"}
```

#### Prediction
```bash
POST /predict
```
- **Content-Type**: `multipart/form-data`
- **Body**: Image file upload

Example using curl:
```bash
curl -X POST -F "file=@path_to_image.jpg" http://localhost:8002/predict
```

Response:
```json
{
    "class": "Healthy",
    "confidence": 0.95
}
```

### Model Training

The training process is documented in the Jupyter notebook located at `training/training.ipynb`. The notebook includes:

- Data preprocessing and augmentation
- Model architecture definition
- Training process
- Evaluation metrics
- Model saving

## Dependencies

### API Dependencies
- fastapi
- uvicorn
- tensorflow
- pillow
- numpy
- python-multipart

### Training Dependencies
- tensorflow/keras
- jupyter
- matplotlib
- numpy
- pillow

## Dataset

The model is trained on the PlantVillage dataset, specifically using potato leaf images categorized into:
- Potato___Early_blight
- Potato___healthy  
- Potato___Late_blight

## Model

The trained model is saved in Keras format (`1.keras`) and loaded by the API for making predictions.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test the API endpoints
5. Submit a pull request

## License

This project is for educational purposes. Please ensure proper attribution when using the code or model.

## Support

For questions or issues regarding this project, please open an issue in the repository.
