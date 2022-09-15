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
# Migration django database & start
ENTRYPOINT [ "./docker-entrypoint.sh" ]
