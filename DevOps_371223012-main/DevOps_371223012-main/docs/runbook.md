# Runbook

## Start locally

```bash
npm install
npm run dev
```

## Check that it works

Open http://localhost:9000 in your browser.

You should see the application's home page without errors.

## Run the tests

```bash
npm test
```

## When something breaks

1. Check that dependencies are installed:
   ```bash
   npm install
   ```

2. Check that required environment variables and `.env` files are present.

3. Check terminal logs and run the test suite:
   ```bash
   npm test
   ```

Run with Docker

Build the Docker image from the project root:

bash
docker build -t notes-api:0.3.0 .


Start the container:

bash
docker run --rm -d --name notes-api -p 8000:8000 notes-api:0.3.0


Check the health endpoint by opening http://localhost:8000/health or the forwarded port 8000 URL in GitHub Codespaces.

View the application logs:

bash
docker logs notes-api


Stop the container when finished:

bash
docker stop notes-api


The container runs as a non-root user and includes a health check for the /health endpoint.