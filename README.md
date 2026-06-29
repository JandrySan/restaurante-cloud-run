# Landing page restaurante - Cloud Run

## Ejecutar localmente

```bash
docker build -t restaurante-landing .
docker run -p 8080:8080 restaurante-landing
```

Luego abre:

```text
http://localhost:8080
```

## Desplegar en Cloud Run

Reemplaza `TU_PROJECT_ID` por el ID de tu proyecto de Google Cloud.

```bash
gcloud config set project TU_PROJECT_ID
gcloud builds submit --tag gcr.io/TU_PROJECT_ID/restaurante-landing
gcloud run deploy restaurante-landing \
  --image gcr.io/TU_PROJECT_ID/restaurante-landing \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated \
  --port 8080
```
