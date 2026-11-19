# Sleep Health App

A student-led health monitoring project designed to help users understand their sleep quality and blood oxygen trends.

## Tech Stack

- Mobile: Flutter, Dart
- Backend: Python, FastAPI
- Database: PostgreSQL
- Health Data: Apple HealthKit and Android Health Connect
- Testing: Flutter Test, Pytest, GitHub Actions
- AI Development Assistant: Devin Bots (planned)

## Core Features

- Sleep duration and sleep stage tracking
- Heart rate and SpO2 monitoring
- Manual CO2 lab result entry
- Sleep and oxygen trend visualization
- Timestamp normalization and sensor data validation
- Detection of unusual oxygen patterns during sleep
- Privacy-focused health data management

## Architecture

Flutter Mobile App → HealthKit / Health Connect → FastAPI Backend → PostgreSQL → Data Analysis → Dashboard

## First Task for Devin

Build the initial Flutter application and FastAPI backend.

1. Set up the Flutter project structure.
2. Implement health data permissions using the Flutter `health` package.
3. Import available sleep stage and SpO2 records.
4. Design PostgreSQL tables for sleep sessions, sleep stages and oxygen readings.
5. Normalize timestamps and handle duplicate or missing sensor data.
6. Implement an initial oxygen trend analysis service using configurable thresholds.
7. Build a responsive health dashboard.
8. Write unit tests using synthetic health data.
9. Configure GitHub Actions for automated testing.
10. Create a pull request with implementation details and test results.

## Development Workflow

Devin will work on separate Git branches, implement assigned tasks, run tests, and open pull requests for developer review.

The project is currently in its planning and initial setup stage. Features described here are planned, not yet implemented.

## Goal

Build a practical, privacy-conscious health app that helps users understand their personal sleep patterns. Any alerts will be informational rather than medical diagnoses.

Developed as an independent student project.
