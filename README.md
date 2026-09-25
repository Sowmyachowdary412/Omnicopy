# OmniCopy

A lightweight FastAPI service for managing marketing campaigns in a SQLite database.

## Overview

This project provides a basic CRUD API for campaigns, including:

- creating the database and tables automatically on startup
- listing all campaigns
- fetching a single campaign by ID
- updating campaign details
- deleting campaigns

## Tech Stack

- Python 3
- FastAPI
- SQLModel
- SQLite

## Project Structure

```text
.
├── main.py
├── requirements.txt
├── database.db
├── .gitignore
└── README.md
```

## Features

- FastAPI application with automatic database initialization
- SQLite persistence using SQLModel
- Campaign model with:
  - campaign_id
  - name
  - due_date
  - created_at
- Seed data for demo campaigns at startup

## Getting Started

### 1. Create and activate a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the API

```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

The app will be available at:

```text
http://localhost:8000
```

If deployed behind a proxy, the app is configured with `root_path="/api/v1"`.

## API Endpoints

### Root

```http
GET /
```

Returns a basic health/message response.

### Campaigns

```http
GET /campaigns
```

Returns all campaigns.

```http
GET /campaigns/{id}
```

Returns a single campaign by ID.

```http
PUT /campaigns/{id}
```

Updates a campaign.

```http
DELETE /campaigns/{id}
```

Deletes a campaign.

## Example Payload

```json
{
  "name": "Spring Campaign",
  "due_date": "2026-10-15T00:00:00Z"
}
```

## Notes

- The database file is created automatically as `database.db`.
- Demo campaign records are seeded at application startup if the database is empty.

## License

This project is provided as-is for development and learning purposes.
