# AWS Docker Environment Variables Demo

A simple Docker application that demonstrates how to use AWS environment variables inside a Docker container. This project is useful for deploying applications to AWS services such as EC2, ECS, or Elastic Beanstalk.

---

## 📌 Features

- Dockerized application
- Uses AWS environment variables
- Easy configuration using `.env`
- Ready for deployment on AWS
- Simple and beginner-friendly

---

## 📁 Project Structure

```
aws-docker-app/
│
├── app.py
├── requirements.txt
├── Dockerfile
├── .dockerignore
├── .env
├── docker-compose.yml
└── README.md
```

---

## 🛠 Prerequisites

- Docker
- Docker Compose (Optional)
- AWS Account
- AWS CLI (Optional)

---

## ⚙ Environment Variables

Create a `.env` file in the project root.

```env
AWS_ACCESS_KEY_ID=YOUR_ACCESS_KEY
AWS_SECRET_ACCESS_KEY=YOUR_SECRET_KEY
AWS_DEFAULT_REGION=ap-south-1
AWS_BUCKET_NAME=my-bucket
```

> **Note:** Never commit your AWS credentials to GitHub.

---

## 🐳 Build Docker Image

```bash
docker build -t aws-docker-app .
```

---

## ▶ Run Docker Container

Using environment variables:

```bash
docker run --env-file .env -p 5000:5000 aws-docker-app
```

Or pass variables directly:

```bash
docker run \
-e AWS_ACCESS_KEY_ID=YOUR_ACCESS_KEY \
-e AWS_SECRET_ACCESS_KEY=YOUR_SECRET_KEY \
-e AWS_DEFAULT_REGION=ap-south-1 \
-p 5000:5000 aws-docker-app
```

---

## 🐳 Using Docker Compose

```bash
docker-compose up --build
```

Example `docker-compose.yml`

```yaml
version: '3.8'

services:
  app:
    build: .
    ports:
      - "5000:5000"
    env_file:
      - .env
```

---

## ☁ Deploy to AWS

This project can be deployed on:

- Amazon EC2
- Amazon ECS
- AWS Elastic Beanstalk
- AWS App Runner

---

## 🔒 Security Best Practices

- Never store AWS credentials in source code.
- Use IAM Roles whenever possible.
- Add `.env` to `.gitignore`.
- Rotate AWS credentials regularly.

---

## 🧪 Verify Environment Variables

Example (Python):

```python
import os

print(os.getenv("AWS_DEFAULT_REGION"))
print(os.getenv("AWS_BUCKET_NAME"))
```

---

## 📦 Useful Docker Commands

Build image

```bash
docker build -t aws-docker-app .
```

List images

```bash
docker images
```

Run container

```bash
docker run --env-file .env aws-docker-app
```

Stop container

```bash
docker stop <container_id>
```

Remove container
bash
docker rm <container_id>

## 📄 License

This project is available under the MIT License.

---

## 👨‍💻 Author

**Aaquib**
