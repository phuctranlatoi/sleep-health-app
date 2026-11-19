# Sleep Health App – Technical Architecture

## 1. Project Overview

A Flutter-based mobile application that helps users track sleep patterns, blood oxygen levels, and personal health trends.

This project is currently in the planning and initial development stage. Devin will help implement, test, and maintain the system.

## 2. Technology Stack

- Mobile: Flutter and Dart
- Backend: Python FastAPI
- Database: PostgreSQL
- Health Integration: Apple HealthKit and Android Health Connect
- CI/CD: GitHub Actions
- Testing: Flutter Test and Pytest

## 3. Database Schema

### users
- id: UUID (primary key)
- created_at: TIMESTAMP
- timezone: VARCHAR(64)

### sleep_sessions
- id: UUID (primary key)
- user_id: UUID (foreign key)
- start_time: TIMESTAMP
- end_time: TIMESTAMP
- source: VARCHAR(100)

### sleep_stages
- id: UUID (primary key)
- session_id: UUID (foreign key)
- stage_type: VARCHAR(30)
- start_time: TIMESTAMP
- end_time: TIMESTAMP

Stage types include awake, light, deep and REM, depending on device support.

### oxygen_readings
- id: UUID (primary key)
- user_id: UUID (foreign key)
- spo2_value: FLOAT
- recorded_at: TIMESTAMP
- device_source: VARCHAR(100)

### lab_results
- id: UUID (primary key)
- user_id: UUID (foreign key)
- measurement_type: VARCHAR(50)
- measurement_value: FLOAT
- unit: VARCHAR(20)
- recorded_at: TIMESTAMP

## 4. Planned REST API

**POST /api/v1/health/sync**

Import authorized health records from supported devices.

**GET /api/v1/sleep/sessions**

Retrieve the user's sleep history.

**GET /api/v1/sleep/analysis**

Return sleep duration, oxygen trends, and available sleep-stage correlations.

**GET /api/v1/oxygen/trends**

Retrieve historical SpO2 readings.

**POST /api/v1/lab-results**

Store manually entered laboratory results, including blood CO2 measurements.

## 5. Data Processing Pipeline

1. Request the user's permission to access supported health data.
2. Import sleep, heart rate and SpO2 records.
3. Normalize timestamps to UTC while retaining timezone context.
4. Validate records and remove duplicates.
5. Handle missing or overlapping sensor readings.
6. Match SpO2 measurements with sleep-stage intervals.
7. Identify unusual patterns using configurable analysis rules.
8. Display trends through a Flutter dashboard.

The application will not provide medical diagnoses.

## 6. Devin Bot Workflow

**Bot Name:** SleepHealth Developer

Devin will:

1. Inspect the repository and identify the next development task.
2. Create a dedicated Git branch.
3. Implement the Flutter application and FastAPI services.
4. Build the planned database models and endpoints.
5. Add automated tests using synthetic health data.
6. Run Flutter analyze, Flutter tests and Pytest.
7. Fix failures before creating a pull request.
8. Update documentation and summarize implementation changes.

The developer will review changes before merging.

## 7. First Development Milestone

Build a working Flutter prototype with mock sleep and SpO2 records, a FastAPI backend, PostgreSQL models, and a dashboard that visualizes historical trends.

Then incrementally integrate supported HealthKit and Health Connect data sources with appropriate permissions and privacy controls.

## 8. Project Links

GitHub: https://github.com/phuctranlatoi/sleep-health-app

X Project Post: https://x.com/lokethewoke/status/2123427205317378184

## 9. Current Status

Architecture proposed. Implementation and external integrations are pending.

The purpose of using Devin is to turn this architecture into a tested, maintainable application.
