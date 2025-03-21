# DLL_Delivery_service

# Delivery Service: USA to Uzbekistan

Welcome to the Delivery Service app! This project helps users efficiently manage deliveries from the USA to Uzbekistan.
Only frontend is shared, backend is hidden due to some very very important reasons.

## Features
- **Order Management**: Users can create, track, and manage their deliveries.
- **Package Tracking**: Real-time updates on shipment status.
- **Secure Authentication**: Login and register securely.
- **Payment Integration**: Pay for shipments using secure methods.
- **Admin Dashboard**: Manage shipments, users, and settings.

## Tech Stack
- **Backend**: FastAPI (Python), PostgreSQL, Redis (for caching and queue management)
- **Frontend**: Vue 3 (with Vite), Axios
- **Authentication**: JWT-based authentication
- **Queue System**: RabbitMQ (for handling order processing efficiently)
- **Deployment**: Docker, Nginx

## Installation

### Prerequisites
- Python 3.9+
- Node.js 16+
- PostgreSQL
- Redis
- Docker (optional for containerized deployment)

### Backend Setup
```bash
git clone https://github.com/yourusername/delivery-app.git
cd delivery-app/backend

python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate

pip install -r requirements.txt

alembic upgrade head

uvicorn app.main:app --reload
```

### Frontend Setup
```bash
cd frontend

npm install

npm run dev
```

## Usage
- Register or log in.
- Create a delivery order.
- Track the package status in real-time.
- Manage orders in the admin panel.

## API Documentation
API documentation is available at [`http://localhost:8000/docs`](http://localhost:8000/docs) (Swagger UI).

## Deployment
To deploy using Docker:
```bash
docker-compose up --build -d
```

## Contribution
Feel free to submit issues and pull requests to improve the project!

## License
This project is licensed under the **MIT License**.

---

### Contact
For any inquiries, reach out to `your-email@example.com`.


