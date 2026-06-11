FROM python:3.12

WORKDIR /app
RUN pip install gunicorn==25.3.0
COPY requirements.txt .
RUN pip install -r /app/requirements.txt --no-cache-dir
COPY . .


RUN apt update && apt -y install zip
RUN echo "hello" > file.txt
RUN zip arch.zip file.txt

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
