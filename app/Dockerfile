FROM python:3.7
# Recommended settings 
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
# Install components
RUN python -m pip install --upgrade pip
COPY requirements.txt requirements.txt
RUN python -m pip install -r requirements.txt
# Copy project
COPY . .
# Upload database schema to PSQL and start web
CMD "bash" "-c" "python3 manage.py makemigrations \
&& python3 manage.py migrate \
&& python3 manage.py collectstatic \
&& python3 manage.py runserver 0.0.0.0:8000"