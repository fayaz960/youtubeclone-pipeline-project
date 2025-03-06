version: '3.8'
services:
  postgres:
    image: postgres:latest
    environment:
      POSTGRES_USER: myuser
      POSTGRES_PASSWORD: mypassword
      POSTGRES_DB: youtubeclone
    ports:
      - "5432:5432"

  backend:
    image: 974522/youtubeclone-backend:latest
    environment:
      JWT_SECRET: pewdiepie
      JWT_EXPIRE: 30d
      DATABASE_URL: postgres://myuser:mypassword@postgres:5432/youtubeclone
    ports:
      - "5000:5000"
    depends_on:
      - postgres

  frontend:
    image: 974522/youtubeclone-frontend:latest
    environment:
      REACT_APP_BACKEND_URL: http://localhost:5000/api/v1/
      REACT_APP_CLOUDINARY_ENDPOINT: https://api.cloudinary.com/v1_1/dggcvdpqj
    ports:
      - "80:80"
    depends_on:
      - backend
