# CV Generator with AI

A pet project that generates and tailors resumes to specific job descriptions using Claude (Anthropic API).
You paste your raw career data, provide a job posting, and get a polished CV back.

## Tech stack

| Layer    | Technology                               |
|----------|------------------------------------------|
| Backend  | NestJS, TypeScript, @nestjs/config       |
| AI       | Claude via @anthropic-ai/sdk             |
| Frontend | Angular 17+ standalone, Signals *(planned)* |

## Running the backend

```bash
cd server
npm install
cp .env.example .env   # then paste your Anthropic API key into .env
npm run start:dev      # http://localhost:3000
```

## API

### GET /api/health

```bash
curl http://localhost:3000/api/health
```

### POST /api/generate

```bash
curl -X POST http://localhost:3000/api/generate \
  -H "Content-Type: application/json" \
  -d '{"rawData": "Your CV data and job description here"}'
```

Response:

```json
{ "result": "Claude-generated CV text" }
```

## Roadmap

| Feature                               | Status   |
|---------------------------------------|----------|
| NestJS backend with `/api/health`     | Done     |
| `/api/generate` endpoint (Claude API) | Done     |
| Input validation (`class-validator`)  | Planned  |
| Angular frontend (standalone/signals) | Planned  |
| PDF export                            | Planned  |
| Claude tool use for structured output | Planned  |
| Auth / rate limiting                  | Planned  |

## Prompt Engineering

> Section will be filled in as prompts stabilize.
> Will cover: system prompt design, how rawData is structured, prompt iterations.

## Architecture & decisions

> Section will be filled in over time.
> Will cover: module structure, why NestJS over Express, AI integration patterns.
