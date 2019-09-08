# Pull base image for python
FROM python:3.7.4-alpine

# Set up working directory
WORKDIR /usr/src/backend

# Configure environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Install pyscopg2
RUN apk update \
    && apk add --virtual build-deps gcc python3-dev musl-dev \
    && apk add postgresql-dev \
    && pip install psycopg2 \
    && apk del build-deps

# Install dependencies
RUN pip install --upgrade pip
RUN pip install pipenv
COPY ./Pipfile /usr/src/backend/Pipfile
RUN pipenv install --skip-lock --system --dev

# Copy entrypoint.sh
COPY ./entrypoint.sh /usr/src/backend/entrypoint.sh

# Copy directory project
COPY . /usr/src/backend/

# Run entrypoint.sh
ENTRYPOINT ["/usr/src/backend/entrypoint.sh"]


