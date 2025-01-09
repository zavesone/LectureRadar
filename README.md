# LectureRadar 🎯

A Telegram bot that helps you discover and attend scientific lectures and events in Moscow. The bot aggregates information about scientific events (lectures, schools, workshops) from various sources (VK, Telegram, websites) and presents them in a customizable calendar interface.

## Project Vision 🚀

LectureRadar aims to create a centralized platform for discovering academic and scientific events in Moscow, making it easier for knowledge enthusiasts to:
- Find relevant lectures and workshops
- Get personalized event recommendations
- Connect with fellow learners
- Never miss important educational opportunities

## System Architecture 📐

Below is the preliminary system architecture diagram. This design may evolve as the project develops:

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

    V1 -- Posts --> V2
    V2 -- Event Data --> V3
    T1 -- Messages --> T2
    T2 -- Event Data --> T3
    W1 -- HTML --> W2
    W2 -- Event Data --> W3
    N1 --> N2
    N2 -- Parallel --> N3 & N4 & N5
    V3 --> N1
    T3 --> N1
    W3 --> N1
    N3 --> E1
    N4 --> E1
    N5 --> E1
    E1 --> DB1
    DB1 -- Cache --> DB2
    DB1 -- Users --> DB3
    DB1 -- Settings --> DB4
    DB2 --> A1
    DB3 --> A1
    DB4 --> A1
    A1 -- REST --> A2 & A3 & A4
    A2 --> A5
    A3 --> A5
    A4 --> A5
    B1 -- Commands --> B2
    B2 -- Actions --> B3
    A5 --> B1
    B3 --> C1 & F1 & S1
    C1 -- Display --> C2 & C3 & C4
    F1 -- Setup --> F2 & F3 & F4
    S1 -- Configure --> S2 & S3 & S4
    S2 --> N1
    N1 -- Schedule --> N2 & N3 & N4
```

## Features 🌟

### Core Functionality
- **Multi-Source Event Aggregation**: Automatically collects scientific events from:
  - VK public pages
  - Telegram channels
  - Educational websites
- **Smart Notifications**: Receive personalized notifications about upcoming events based on your interests
- **Interactive Calendar**: View and manage events in a convenient calendar interface
- **Location-Based Updates**: Get informed about events happening near you

### Social Features
- **Meetup Organization**: Create and join meetups with other lecture enthusiasts
- **Random Coffee Matching**: Find lecture companions through our random matching system
- **Community Building**: Connect with like-minded individuals interested in scientific lectures

### Personalization
- **Interest-Based Filtering**: Set your preferred topics and receive relevant event notifications
- **Custom Schedule**: Configure notification timing based on your availability
- **Event History**: Keep track of lectures you've attended and save ones for later

## Getting Started 🚀

### Prerequisites
- Python 3.8+
- Telegram account
- API keys (details in setup section)

### Installation

1. Clone the repository
```bash
git clone https://github.com/zavesone/LectureRadar.git
cd LectureRadar
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Configure environment variables
```bash
cp .env.example .env
# Edit .env with your API keys and configuration
```

## Contributing 🤝

We welcome contributions! Whether you're interested in:
- Backend development (Python, FastAPI)
- NLP and data processing
- Frontend and UI/UX design
- Documentation and testing

Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License 📝

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact 📮

Project Link: [https://github.com/zavesone/LectureRadar](https://github.com/zavesone/LectureRadar)

## Acknowledgments 🙏

- Thanks to all the educational institutions in Moscow for providing event information
- Contributors and community members
- Libraries and tools used in this project