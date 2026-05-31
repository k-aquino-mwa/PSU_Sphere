Project Structure
.
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── .dockerignore
└── for_client/
    └── docker-compose.yml

Build and Run (Development)
1. Build Image
docker build -t my-django-app:latest .
2. Run Container
docker-compose up -d
3. Access App
Open browser:
http://localhost:8000

Push to Docker Hub
1. Login
docker login
2. Tag Image
docker tag my-django-app:latest <yourusername>/django-app:latest
3. Push Image
docker push <yourusername>/django-app:latest

Run on Another Machine
1. Pull Image
docker pull <yourusername>/django-app:latest
2. Run Using Docker Compose
docker-compose up -d

First-Time Setup
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --noinput

Updating the Application
Development Machine
docker-compose build
docker tag my-django-app:latest <yourusername>/django-app:v1.1
docker push <yourusername>/django-app:v1.1
Client Machine
docker-compose pull
docker-compose down
docker-compose up -d

