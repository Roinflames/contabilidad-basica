FROM python:3.12-slim
WORKDIR /code
ENV PYTHONDONTWRITEBYTECODE=1 PYTHONUNBUFFERED=1
COPY Pipfile* ./
RUN pip install pipenv && pipenv install --system --deploy --ignore-pipfile
COPY . .
CMD ["gunicorn", "src.config.wsgi:application", "--bind", "0.0.0.0:${PORT:-8000}"]
