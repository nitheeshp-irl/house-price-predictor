# House Price Predictor - Project Structure

## Directory Organization

### Core Application Structure
```
house-price-predictor/
├── src/                    # Main application source code
│   ├── api/               # FastAPI backend service
│   ├── data/              # Data processing pipeline
│   ├── features/          # Feature engineering modules
│   └── models/            # Model training and evaluation
├── streamlit_app/         # Frontend web application
├── configs/               # YAML configuration files
├── data/                  # Dataset storage (raw/processed)
├── models/                # Trained model artifacts
└── notebooks/             # Jupyter exploration notebooks
```

### Infrastructure & Deployment
```
├── deployment/            # Deployment configurations
│   ├── mlflow/           # MLflow tracking server setup
│   └── kubernetes/       # K8s deployment manifests
├── .github/workflows/    # CI/CD pipeline definitions
├── Dockerfile.api        # Backend containerization
└── docker-compose.yml    # Multi-service orchestration
```

## Core Components & Relationships

### Data Pipeline Flow
1. **Raw Data** (`data/raw/`) → **Data Processing** (`src/data/`) → **Processed Data** (`data/processed/`)
2. **Feature Engineering** (`src/features/`) → **Featured Data** → **Model Training** (`src/models/`)
3. **Trained Models** (`models/trained/`) → **API Inference** (`src/api/`) → **Web Interface** (`streamlit_app/`)

### Service Architecture
- **Backend API**: FastAPI service with inference endpoints and data validation schemas
- **Frontend UI**: Streamlit application consuming backend API for predictions
- **ML Pipeline**: Sequential processing from raw data to trained model artifacts
- **Experiment Tracking**: MLflow server for model versioning and metrics logging

### Configuration Management
- **Model Config** (`configs/model_config.yaml`): RandomForest parameters, feature sets, performance metrics
- **Environment Setup**: Requirements files for different components (main, API, Streamlit)
- **Container Config**: Dockerfiles and compose files for service orchestration

## Architectural Patterns

### Modular Design
- **Separation of Concerns**: Distinct modules for data, features, models, and API
- **Pipeline Architecture**: Sequential data processing with clear input/output contracts
- **Service-Oriented**: Decoupled frontend and backend with API communication

### MLOps Integration
- **Experiment Tracking**: MLflow integration throughout training pipeline
- **Model Versioning**: Systematic model artifact storage and retrieval
- **CI/CD Pipeline**: Automated testing, building, and deployment workflow
- **Containerization**: Docker-based deployment for consistency across environments

### Development Workflow
- **Notebook Exploration**: Jupyter notebooks for data analysis and experimentation
- **Script Automation**: Python scripts for production pipeline execution
- **Configuration-Driven**: YAML-based configuration for model parameters and settings