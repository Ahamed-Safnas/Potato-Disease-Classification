# 🥔 Potato Disease Classification

A full-stack deep learning application that classifies potato plant diseases from leaf images using a trained neural network model. Built with FastAPI backend and React frontend, containerized with Docker.

## 🌟 Features

- **Image Classification**: Upload potato leaf images to detect Early Blight, Late Blight, or Healthy plants
- **Real-time Predictions**: Fast inference using a pre-trained Keras/TensorFlow model
- **Responsive UI**: Material-UI based React frontend with drag-and-drop upload
- **RESTful API**: FastAPI backend with CORS support
- **Dockerized**: Complete containerization for easy deployment
- **Confidence Scores**: Returns prediction confidence percentages

## 🏗️ Architecture

```
Potato-disease/
├── api/                 # FastAPI Backend
│   ├── models/         # Keras model files
│   ├── main.py         # FastAPI application
│   ├── requirements.txt # Python dependencies
│   └── Dockerfile      # Backend container setup
├── frontend/           # React Frontend
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── Dockerfile      # Frontend container setup
└── docker-compose.yml  # Multi-container orchestration
```

## 🚀 Quick Start

### Prerequisites
- Docker and Docker Compose
- Git

### Installation & Running

1. **Clone the repository**
   ```bash
   git clone https://github.com/Ahamed-Safnas/Potato-Disease-Classification.git
   cd Potato-Disease-Classification
   ```

2. **Start with Docker Compose**
   ```bash
   docker-compose up -d --build
   ```

3. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8000
   - API Documentation: http://localhost:8000/docs

## 📖 API Endpoints

### `GET /ping`
Health check endpoint
```bash
curl http://localhost:8000/ping
```

### `POST /predict`
Upload potato leaf image for classification
```bash
curl -X POST -F "file=@path_to_image.jpg" http://localhost:8000/predict
```

**Response:**
```json
{
  "class": "Early Blight",
  "confidence": 0.9567
}
```

## 🛠️ Manual Development Setup

### Backend Setup
```bash
cd api
python -m venv venv
source venv/bin/activate  # Linux/Mac
# OR
venv\Scripts\activate     # Windows
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

### Frontend Setup
```bash
cd frontend
npm install
npm start
```

## 🐳 Docker Commands

**Build and run specific services:**
```bash
docker-compose build backend
docker-compose up frontend
```

**View logs:**
```bash
docker-compose logs
docker-compose logs -f backend
```

**Stop services:**
```bash
docker-compose down
```

## 📊 Model Information

- **Framework**: TensorFlow/Keras
- **Classes**: Early Blight, Late Blight, Healthy
- **Input**: Potato leaf images
- **Output**: Classification with confidence score

## 🎯 Usage

1. Open the web application at http://localhost:3000
2. Drag and drop a potato leaf image or click to browse
3. View the classification results with confidence percentage
4. Use the clear button to analyze another image

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Potato leaf dataset providers
- TensorFlow and FastAPI communities
- Material-UI React components

## 🆘 Support

For support, please open an issue in the GitHub repository or contact the maintainers.

---

**Note**: Ensure you have adequate hardware resources (especially RAM) for running the deep learning model inference.
