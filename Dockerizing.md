## 7. Dockerizing
Sample ```Dockerfile```:
```
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["python", "app.py"]
```
---
build and run:
```
docker build -t password_manager_app .
docker run -p 5000:5000 password_manager_app
```
---
## 8. Deployment Notes

- Consider using a managed database like PostgreSQL for production.
- Set FLASK_SECRET_KEY securely in your environment.
- Disable debug mode (debug=False) in production.
- Use Render or similar platforms for easy Docker deployments.

