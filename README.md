# OpenSignal

OpenSignal is a lightweight, open-source framework for capturing, structuring, and exposing public communication signals from decentralised and user-operated platforms.

The project focuses on standardising ingestion and access to publicly available data from systems such as ActivityPub and Telegram, enabling downstream tools to analyse communication patterns without relying on centralised platforms.

---

## Scope

OpenSignal provides:

- Connectors for ingesting public data from decentralised communication platforms
- A minimal, structured schema for representing communication signals
- A simple API layer for querying and exporting data
- A modular architecture designed for extension

OpenSignal does NOT provide:

- Analytics, dashboards, or interpretation layers
- Private data collection or surveillance tooling
- Any platform-specific lock-in

---

## Architecture

OpenSignal is composed of three layers:

1. Ingestion Layer  
   Collects public data via platform-specific connectors

2. Storage Layer  
   Normalises and stores signals using a unified schema

3. API Layer  
   Exposes structured data for external use

---

## Data Model (Draft)

Signal:
- id (string)
- source_type (activitypub | telegram)
- source_id (string)
- timestamp (datetime)
- content (text)
- metadata (json)

Entity:
- id (string)
- type (user | channel)
- external_id (string)

Relationship:
- source_entity_id
- target_entity_id
- type (posted_in | authored_by)

---

## Repository Structure

/connectors/  
Platform-specific ingestion modules  

/schema/  
Data model definitions  

/api/  
API endpoints and data access  

---

## Technical Direction

- Language: Python (initial implementation)
- Storage: PostgreSQL
- API: FastAPI
- Deployment: containerised (Docker)

---

## Objectives

- Provide a simple, reusable ingestion layer for decentralised communication data
- Enable interoperability between platforms
- Support open analysis without centralised control

---

## Status

Initial specification and repository setup.
