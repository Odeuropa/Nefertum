FROM python:3.11-slim as builder

WORKDIR /app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN python -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

COPY requirements.txt .
RUN pip install --upgrade pip
RUN pip install -r requirements.txt


FROM python:3.11-slim

COPY --from=builder /opt/venv /opt/venv

WORKDIR /app

ENV PATH="/opt/venv/bin:$PATH"

COPY . app
CMD python app/matrixes/clearMatrixes.py && python app/scripts/fetcher.py && python app/scripts/addCountsLabels.py && python app/scripts/generateAttributesQuestions.py
CMD env FLASK_APP=app/app.py
CMD ["env","FLASK_APP=app/app.py", "flask", "run", "-h", "0.0.0.0", "-p", "5000"]