# Tech Stack Manual

## 1. Run Questions

### 1a. Config Files

| Config File | Location | Config Value | What it's for | How it's used |
|---|---|---|---|---|
|.setupsh | /scripts | |Setting up | It checks if Docker is installed, checks docker status |
| docker-compose.yml | root | | | |
| Makefile | root | | |

### 1b. How to Start It

make setup setup a fresh machine to run the lms
make build after setup, to run on a machine with the installs done.

### 1c. Where to Access It

| Service | Port | URL |
|---|---|---|
| Database | 5433 | |
| API | 8000  |
| Client | 3000 | |

### 1d. Service Dependencies

| Service | Depends On | Why |
|---|---|---|
| API | Database | The API needs to connect to the database to read/write data |
| Client | API | It has nothing to display without data |
| | | |

### 1e. Main Entry Points

| Service | Startup File | Routes / URL Config File |
|---|---|---|
| | | |
| | | |
| | | |

---

## 2. Services

| Service Name | Tech Stack (including version) | Purpose |
|---|---|---|
| | | |

---

## 3. System Overview
