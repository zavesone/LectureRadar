# LectureRadar

A Telegram bot that helps you discover and attend scientific events (lectures, schools, workshops) in Moscow by aggregating information from various sources (VK, Telegram, websites) and presenting them in a customizable calendar interface.

## System Architecture 

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

## Features

### Data Collection
- VK public pages parser
- Telegram channels parser
- Website scraper
- Content filtering and validation

### Event Processing
- NLP-based event classification
- Smart notification system
- Event validation and enrichment
- Custom reminder system

### User Interface
- Interactive calendar views
- Flexible filtering system
- Customizable notifications
- User preference management

## Tech Stack

- Backend: Python, FastAPI
- Database: PostgreSQL, Redis
- NLP: spaCy/NLTK
- Bot Framework: python-telegram-bot
- Frontend: Telegram Bot API

## Getting Started

[Installation and setup instructions will be added]

## Contributing

We welcome contributions! Whether you're interested in:
- Backend development
- NLP and data processing
- Bot interface design
- Documentation and testing

Please reach out if you'd like to contribute.

## License

This project is under development. License details will be added soon.
