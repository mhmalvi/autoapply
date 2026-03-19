# AutoApply

An automated job search and application tool that streamlines the job hunting process across multiple platforms. AutoApply uses browser automation to search for jobs, extract listings, and submit applications on LinkedIn, Indeed, and Glassdoor.

## Features

- **Multi-Platform Support** — Automated job search across LinkedIn, Indeed, and Glassdoor
- **Browser Automation** — Undetected Chrome driver for reliable web interaction
- **Configurable Search** — YAML-based configuration for job titles, locations, and platform-specific settings
- **Anti-Detection** — Uses `undetected-chromedriver` to bypass bot detection mechanisms
- **Structured Logging** — Detailed logging with Loguru for monitoring and debugging
- **Test Coverage** — Comprehensive test suite with pytest for all platform integrations
- **Modular Architecture** — Plugin-style platform system with a common base class

## Tech Stack

| Component | Technology |
|-----------|------------|
| Language | Python 3.10+ |
| Browser Automation | Selenium, undetected-chromedriver |
| HTML Parsing | BeautifulSoup4 |
| Testing | pytest, pytest-cov |
| Logging | Loguru |
| Configuration | PyYAML, python-dotenv |

## Supported Platforms

| Platform | Search | Extract | Apply |
|----------|--------|---------|-------|
| LinkedIn | Yes | Yes | Yes |
| Indeed | Yes | Yes | Yes |
| Glassdoor | Yes | Yes | Yes |

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/mhmalvi/autoapply.git
cd autoapply
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # Linux/macOS
venv\Scripts\activate      # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Settings

Edit `config/config.yaml` with your job search preferences:

```yaml
search:
  job_title: "Software Engineer"
  location: "Remote"
  platforms:
    - linkedin
    - indeed
    - glassdoor
```

Create a `.env` file with your platform credentials:

```env
LINKEDIN_EMAIL=your_email
LINKEDIN_PASSWORD=your_password
```

### 5. Run the Application

```bash
python src/main.py
```

## Project Structure

```
autoapply/
├── config/
│   └── config.yaml           # Search and platform configuration
├── src/
│   ├── main.py               # Application entry point
│   ├── platforms/
│   │   ├── base.py           # Abstract base class for platforms
│   │   ├── linkedin.py       # LinkedIn automation
│   │   ├── indeed.py         # Indeed automation
│   │   └── glassdoor.py      # Glassdoor automation
│   └── utils/
│       ├── config_loader.py  # YAML configuration parser
│       └── logger.py         # Logging setup
├── tests/
│   ├── conftest.py           # Test fixtures
│   ├── test_linkedin.py
│   ├── test_indeed.py
│   ├── test_glassdoor.py
│   └── test_config.py
├── requirements.txt
└── .gitignore
```

## Running Tests

```bash
pytest --cov=src tests/
```

## License

This project is open source and available under the [MIT License](LICENSE).
