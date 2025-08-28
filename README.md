# MediAssist 🏥

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-00a393.svg)](https://fastapi.tiangolo.com)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-FF6B6B.svg)](https://streamlit.io)
[![Docker](https://img.shields.io/badge/docker-%230db7ed.svg)](https://www.docker.com/)

> **AI-powered medical document analysis and patient management system with synthetic patient generation capabilities.**

MediAssist is a comprehensive healthcare technology platform that combines artificial intelligence with medical data analysis to provide healthcare professionals with powerful tools for patient care, medical research, and system validation.

## 🌟 Features

### 🩺 Core Medical Features
- **Medical Document Analysis**: Upload and analyze medical reports with AI-powered insights
- **Symptom Analysis**: Get risk assessments and recommendations based on reported symptoms
- **Drug Information Search**: Query FDA database for medication details, warnings, and interactions
- **Patient Risk Assessment**: AI-driven risk prediction with visual gauges and metrics
- **Medical Chatbot**: Interactive assistant for medical queries and guidance

### 🧬 Synthea Integration
- **Synthetic Patient Generation**: Create realistic patient data for testing and validation
- **FHIR-Compliant Data**: Generate healthcare data following industry standards
- **Customizable Parameters**: Control patient demographics, conditions, and medical history
- **Medical Report Generation**: Create comprehensive patient reports for testing
- **Risk Modeling**: Test AI models with diverse patient populations

### 🔐 Security & Authentication
- **JWT-Based Authentication**: Secure token-based user authentication
- **Role-Based Access Control**: Different access levels for users
- **Password Encryption**: Bcrypt hashing for secure password storage
- **CORS Protection**: Secure cross-origin resource sharing

### 💻 Technical Features
- **RESTful API**: Comprehensive FastAPI backend with automatic documentation
- **Interactive Dashboard**: Modern Streamlit web interface
- **Docker Containerization**: Easy deployment with Docker Compose
- **Database Integration**: SQLite for simplicity, easily extensible to PostgreSQL
- **File Storage**: MinIO integration for secure document storage
- **Caching**: Redis for improved performance

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Streamlit     │    │    FastAPI      │    │   External APIs │
│   Dashboard     │◄──►│      API        │◄──►│   (FDA, etc.)   │
│   (Frontend)    │    │   (Backend)     │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│     Redis       │    │     SQLite      │    │     MinIO       │
│   (Caching)     │    │   (Database)    │    │ (File Storage)  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## 🚀 Quick Start

### Prerequisites

- **Docker & Docker Compose** (recommended)
- **Python 3.11+** (for local development)
- **Git** for version control

### 🐳 Running with Docker (Recommended)

1. **Clone the repository:**
```bash
git clone https://github.com/Vibhor2702/mediassist.git
cd mediassist
```

2. **Start all services:**
```bash
docker-compose up -d --build
```

3. **Access the application:**
   - 🌐 **Dashboard**: http://localhost:8501
   - 📚 **API Documentation**: http://localhost:8000/docs
   - 🗄️ **MinIO Console**: http://localhost:9001
   - 📊 **Redis**: localhost:6379

4. **Default Login Credentials:**
   - **Email**: `admin@mediassist.dev`
   - **Password**: `admin123`

### 🛠️ Local Development Setup

1. **Create and activate virtual environment:**
```bash
python -m venv .venv

# On Windows
.venv\Scripts\activate

# On macOS/Linux
source .venv/bin/activate
```

2. **Install API dependencies:**
```bash
cd services/api
pip install -r requirements.txt
```

3. **Install Dashboard dependencies:**
```bash
cd ../web/dashboard
pip install -r requirements.txt
```

4. **Run the API (Terminal 1):**
```bash
cd services/api
python main.py
```

5. **Run the Dashboard (Terminal 2):**
```bash
cd web/dashboard
streamlit run app.py
```

## 📁 Project Structure

```
mediassist/
├── 📄 README.md                   # Project documentation
├── 📄 LICENSE                     # MIT License
├── 📄 .gitignore                  # Git ignore rules
├── 📄 .env.example                # Environment variables template
├── 📄 docker-compose.yml          # Docker orchestration
├── 📄 CONTRIBUTING.md             # Contribution guidelines
│
├── 🐍 services/
│   └── api/                       # FastAPI Backend
│       ├── 📄 main.py             # Main application file
│       ├── 📄 requirements.txt    # Python dependencies
│       └── 🐳 Dockerfile          # API container config
│
└── 🌐 web/
    └── dashboard/                 # Streamlit Frontend
        ├── 📄 app.py              # Dashboard application
        ├── 📄 requirements.txt    # Dashboard dependencies
        └── 🐳 Dockerfile          # Dashboard container config
```

## 🔌 API Endpoints

### 🔐 Authentication
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/auth/login` | User authentication |
| `GET` | `/auth/me` | Get current user info |

### 🩺 Medical Services
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/medical/symptoms/analyze` | Analyze symptoms and get risk assessment |
| `POST` | `/medical/drugs/search` | Search FDA drug database |
| `GET` | `/reports` | Get user's medical reports |

### 🧬 Synthea Integration
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/synthea/info` | Get Synthea service information |
| `POST` | `/synthea/generate` | Generate synthetic patients |
| `GET` | `/synthea/download/{patient_id}/report` | Download patient report |

### 🔧 System
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/health` | System health check |
| `GET` | `/docs` | Interactive API documentation |

## 🎯 Use Cases

### 🏥 Healthcare Providers
- **Patient Risk Assessment**: Analyze symptoms and get risk predictions
- **Drug Information**: Quick access to FDA medication database
- **Medical Documentation**: Secure storage and analysis of medical reports
- **Clinical Decision Support**: AI-powered recommendations

### 🔬 Medical Researchers
- **Synthetic Data Generation**: Create realistic patient datasets for research
- **Algorithm Validation**: Test medical AI models with diverse populations
- **FHIR Data Compliance**: Generate standards-compliant healthcare data
- **Population Health Studies**: Analyze trends with synthetic populations

### 🎓 Medical Education
- **Case Study Generation**: Create diverse patient scenarios for training
- **Medical Informatics**: Learn healthcare technology integration
- **AI in Healthcare**: Understand machine learning applications in medicine
- **System Integration**: Practice with real healthcare IT workflows

### 🏢 Healthcare Technology Companies
- **Product Testing**: Validate healthcare software with realistic data
- **Integration Testing**: Test APIs and systems with synthetic patients
- **Compliance Validation**: Ensure HIPAA and regulatory compliance
- **Prototype Development**: Build and test new healthcare solutions

## 🛡️ Security

### Authentication & Authorization
- **JWT Tokens**: Secure stateless authentication
- **Password Hashing**: Bcrypt with salt for password security
- **Session Management**: Token-based session handling
- **Role-Based Access**: Different permissions for user types

### Data Protection
- **CORS Configuration**: Controlled cross-origin requests
- **Input Validation**: Pydantic models for request validation
- **SQL Injection Prevention**: SQLAlchemy ORM with parameterized queries
- **File Upload Security**: Controlled file types and sizes

### Privacy Compliance
- **Synthetic Data**: No real patient information in testing
- **Data Encryption**: Secure storage of sensitive information
- **Audit Logging**: Track user actions and system events
- **HIPAA Considerations**: Privacy-first design patterns

## 🔧 Configuration

### Environment Variables

Create a `.env` file based on `.env.example`:

```bash
# Database Configuration
DATABASE_URL=sqlite:///./mediassist.db

# Security
SECRET_KEY=your-super-secret-jwt-key-change-in-production
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30

# Service URLs
API_BASE_URL=http://localhost:8000

# MinIO Configuration
MINIO_ENDPOINT=localhost:9000
MINIO_ACCESS_KEY=minioadmin
MINIO_SECRET_KEY=minioadmin123
MINIO_BUCKET=mediassist

# Redis Configuration
REDIS_URL=redis://localhost:6379/0

# Application Settings
APP_NAME=MediAssist
APP_VERSION=1.0.0
DEBUG=false
```

### Docker Compose Services

| Service | Port | Description |
|---------|------|-------------|
| `api` | 8000 | FastAPI backend service |
| `dashboard` | 8501 | Streamlit web interface |
| `redis` | 6379 | Caching and session storage |
| `minio` | 9000, 9001 | Object storage for files |

## 📊 Monitoring & Health Checks

- **API Health**: `/health` endpoint for service monitoring
- **Container Health**: Docker health checks for all services
- **Database Monitoring**: SQLite connection and query performance
- **External API Status**: FDA API availability checks

## 🧪 Testing

### Manual Testing
1. **Authentication**: Login with test credentials
2. **Symptom Analysis**: Test with various symptom combinations
3. **Drug Search**: Query common medications
4. **Synthea Generation**: Create synthetic patients
5. **File Upload**: Test medical document processing

### Automated Testing (Future Enhancement)
```bash
# Unit tests
pytest services/api/tests/

# Integration tests
pytest tests/integration/

# Performance tests
locust -f tests/performance/locustfile.py
```

## 🚀 Deployment

### Production Deployment

1. **Update Environment Variables**:
   ```bash
   # Use strong passwords and keys
   SECRET_KEY=your-production-secret-key-here
   DATABASE_URL=postgresql://user:pass@host:port/dbname
   ```

2. **Use Production Database**:
   ```yaml
   # docker-compose.prod.yml
   services:
     postgres:
       image: postgres:15
       environment:
         POSTGRES_DB: mediassist
         POSTGRES_USER: ${DB_USER}
         POSTGRES_PASSWORD: ${DB_PASSWORD}
   ```

3. **Set Up Reverse Proxy**:
   ```nginx
   # nginx.conf
   server {
       listen 80;
       server_name yourdomain.com;
       
       location /api/ {
           proxy_pass http://api:8000/;
       }
       
       location / {
           proxy_pass http://dashboard:8501/;
       }
   }
   ```

### Cloud Deployment Options

- **AWS**: ECS with Application Load Balancer
- **Google Cloud**: Cloud Run with Cloud SQL
- **Azure**: Container Instances with Azure Database
- **DigitalOcean**: App Platform with Managed Databases
- **Heroku**: Container deployment with add-ons

## 🤝 Contributing

We welcome contributions from the community! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Workflow

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Make your changes**: Follow coding standards and add tests
4. **Commit your changes**: `git commit -m 'Add amazing feature'`
5. **Push to the branch**: `git push origin feature/amazing-feature`
6. **Open a Pull Request**: Describe your changes and improvements

### Code Style

- **Python**: Follow PEP 8 guidelines
- **Type Hints**: Use type annotations for better code clarity
- **Docstrings**: Document functions and classes
- **Testing**: Add tests for new features
- **Security**: Follow security best practices

## 📈 Roadmap

### Version 2.0 (Planned)
- [ ] **Machine Learning Models**: Custom trained medical AI models
- [ ] **Advanced OCR**: Extract text from medical images and PDFs
- [ ] **HL7 FHIR Integration**: Full FHIR server compatibility
- [ ] **Multi-language Support**: International healthcare standards
- [ ] **Mobile App**: React Native companion app

### Version 1.5 (Next Release)
- [ ] **PostgreSQL Support**: Production-grade database option
- [ ] **Advanced Analytics**: Medical trend analysis and reporting
- [ ] **API Rate Limiting**: Enhanced security and performance
- [ ] **Audit Logging**: Comprehensive user action tracking
- [ ] **Email Notifications**: Alert system for critical findings

## 🐛 Known Issues

- **Large File Upload**: Files over 50MB may timeout (use MinIO directly)
- **FDA API Rate Limits**: May throttle under heavy usage
- **Synthea Performance**: Generation of 10+ patients may be slow

## 💡 FAQ

**Q: Can this be used in a real medical setting?**
A: This is a proof-of-concept for educational purposes. For production medical use, additional validation, compliance testing, and regulatory approval would be required.

**Q: Is patient data secure?**
A: Yes, the system uses encryption and follows security best practices. However, for HIPAA compliance, additional security measures may be needed.

**Q: Can I add my own medical AI models?**
A: Yes, the architecture is designed to be extensible. You can add custom models to the FastAPI backend.

**Q: How do I scale this for high traffic?**
A: Use a production database (PostgreSQL), implement Redis clustering, add load balancers, and consider microservices architecture.

## 📞 Support

- **GitHub Issues**: [Report bugs or request features](https://github.com/Vibhor2702/mediassist/issues)
- **Discussions**: [Community discussions and Q&A](https://github.com/Vibhor2702/mediassist/discussions)
- **Documentation**: [API documentation](http://localhost:8000/docs) (when running locally)

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Synthea**: Synthetic patient data generation
- **FDA OpenFDA**: Drug information API
- **FastAPI**: Modern Python web framework
- **Streamlit**: Rapid web app development
- **Docker**: Containerization platform
- **SQLAlchemy**: Python SQL toolkit

## ⚠️ Disclaimer

**Important**: This application is designed for educational, research, and development purposes only. It should not be used for actual medical diagnosis, treatment decisions, or patient care without proper validation, testing, and regulatory approval. Always consult qualified healthcare professionals for medical advice and decisions.

---

<div align="center">

**Built with ❤️ for the healthcare community**

[🌟 Star this project](https://github.com/Vibhor2702/mediassist) | [🐛 Report Bug](https://github.com/Vibhor2702/mediassist/issues) | [✨ Request Feature](https://github.com/Vibhor2702/mediassist/issues)

</div>
