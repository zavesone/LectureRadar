Here's the complete README content with all the improvements, including the mermaid diagram. The content is formatted and ready to paste:

# LectureRadar 🎯

A Telegram bot that helps you discover and attend scientific events (lectures, schools, workshops) in Moscow. Never miss an interesting lecture again!

## Project Vision 🚀

LectureRadar aims to create a centralized platform for discovering academic and scientific events in Moscow, making it easier for knowledge enthusiasts to:
- Find relevant lectures and workshops from multiple sources
- Get personalized event recommendations
- Connect with fellow learners
- Access a unified calendar of academic events

## Development Status ⚡

This project is currently in active development. We are working on:
- Core data collection infrastructure
- Event parsing and classification
- Bot interface development
- Calendar integration

## System Architecture 📐

```mermaid
flowchart TD
subgraph Data_Collection["Data Collection"]
        V2["Post Filter"]
        V1["VK Parser"]
        V3["Event Extractor VK"]
        T2["Message Filter"]
        T1["Telegram Parser"]
        T3["Event Extractor TG"]
        W2["Content Filter"]
        W1["Web Scraper"]
        W3["Event Extractor Web"]
    end
    subgraph NLP_Processing["NLP Processing"]
        N2["Event Reminders"]
        N1["Notification Manager"]
        N3["New Event Alerts"]
        N4["Custom Notifications"]
        N5["Event Type Classifier"]
        E1["Event Validator"]
    end
subgraph Data_Storage["Data Storage"]
        DB1["PostgreSQL Events"]
        DB2["Redis Cache"]
        DB3["User Data"]
        DB4["User Settings"]
    end
subgraph API_Service["API Service"]
        A1["FastAPI Server"]
        A2["Event API"]
        A3["User API"]
        A4["Settings API"]
        A5["API Gateway"]
    end
subgraph Bot_Framework["Bot Framework"]
        B2["Command Router"]
        B1["Telegram Bot"]
        B3["Action Handler"]
    end
subgraph Calendar_Interface["Calendar Interface"]
        C1["Calendar View"]
        C2["Day View"]
        C3["Week View"]
        C4["Month View"]
    end
subgraph Filter_System["Filter System"]
        F1["Filter Manager"]
        F2["Type Filters"]
        F3["Date Filters"]
        F4["Location Filters"]
    end
subgraph User_Settings["User Settings"]
        S1["Settings Manager"]
        S2["Notifications"]
        S3["Display Preferences"]
        S4["Filter Presets"]
    end

    V1 --> V2
    V2 --> V3
    T1 --> T2
    T2 --> T3
    W1 --> W2
    W2 --> W3
    V3 & T3 & W3 --> N1
    N1 --> N2
    N2 --> N3 & N4 & N5
    N3 & N4 & N5 --> E1
    E1 --> DB1
    DB1 --> DB2 & DB3 & DB4
    DB2 & DB3 & DB4 --> A1
    A1 --> A2 & A3 & A4
    A2 & A3 & A4 --> A5
    A5 --> B1
    B1 --> B2
    B2 --> B3
    B3 --> C1 & F1 & S1
    C1 --> C2 & C3 & C4
    F1 --> F2 & F3 & F4
    S1 --> S2 & S3 & S4
```

*Note: This is a preliminary system architecture that may evolve as the project develops.*

## Features 🌟

### Core Features
- **Multi-Source Event Aggregation**: Automatically collects events from VK, Telegram, and educational websites
- **Smart Filtering**: Uses NLP to classify and categorize events
- **Interactive Calendar**: Customizable calendar interface for event management
- **Personalized Notifications**: Get alerts based on your interests and preferences

### Upcoming Features
- Location-based event suggestions
- Event rating and recommendations
- Community features and event companion matching
- Integration with popular calendar apps

## Tech Stack 💻

- **Backend**: Python, FastAPI
- **Database**: PostgreSQL, Redis
- **NLP**: spaCy/NLTK
- **Bot Framework**: python-telegram-bot
- **Frontend**: Telegram Bot API

## Getting Started 🏃‍♂️

### Prerequisites
- Python 3.8+
- PostgreSQL
- Redis
- Telegram Bot Token

### Quick Start
1. Clone the repository
```bash
git clone https://github.com/zavesone/LectureRadar.git
cd LectureRadar
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Set up environment variables
```bash
cp .env.example .env
# Edit .env with your configuration
```

## Contributing 🤝

We welcome contributions! If you're interested in:
- Backend development
- NLP and data processing
- Bot interface design
- Documentation and testing

See our [Contributing Guidelines](CONTRIBUTING.md) for more details.

## Documentation 📚

- [API Documentation](docs/API.md)
- [Development Setup](docs/DEVELOPMENT.md)
- [Bot Commands](docs/COMMANDS.md)

## Contact 📧

- GitHub Issues: For bug reports and feature requests
- Telegram: @lectureradar_admin
- Email: [coming soon]

## License 📝

This project is under development. License details will be added soon.
