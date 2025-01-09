# LectureRadar 🎯

A Telegram bot that helps you discover and attend scientific lectures and events in Moscow. Never miss an interesting lecture again!

## Features 🌟

### Core Functionality
- **Event Aggregation**: Automatically collects information about scientific lectures and events from various sources in Moscow
- **Smart Notifications**: Receive personalized notifications about upcoming events based on your interests
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

### Usage

1. Start the bot
```bash
python main.py
```

2. In Telegram:
- Search for @LectureRadarBot
- Start a conversation with the bot
- Follow the setup instructions to configure your preferences

## Configuration ⚙️

### Environment Variables
```
TELEGRAM_BOT_TOKEN=your_bot_token
DATABASE_URL=your_database_url
```

### User Settings
- Configure your interests through the `/settings` command
- Set your location using `/location`
- Adjust notification preferences with `/notifications`

## Contributing 🤝

We welcome contributions! Here's how you can help:

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