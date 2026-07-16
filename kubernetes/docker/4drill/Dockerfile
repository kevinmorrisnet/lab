FROM python:3.11-alpine
WORKDIR /app
COPY app.py /app
RUN pip install flask
ENV FLASK_ENV=production
EXPOSE 5000
CMD ["python", "app.py"]

