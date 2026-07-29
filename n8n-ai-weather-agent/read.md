
# 🌤️ AI Weather Assistant with n8n

This project is an AI-powered weather assistant built using n8n.

## Features

- Get real-time weather for any city.
- Uses OpenWeather API for live weather data.
- Uses Google Gemini AI to generate simple weather summaries.
- Parent and Child Workflow architecture.
- Easy to customize.

## Tech Stack

- n8n
- Google Gemini
- OpenWeather API

## Workflow

User Query
↓
Parent Workflow
↓
Child Workflow
↓
OpenWeather API
↓
Google Gemini
↓
Simple English Weather Report

## Example

Input:
```
What's the weather in Lahore?
```

Output:
```
The current weather in Lahore, Pakistan is clear with a temperature of 34°C. It feels like 36°C with moderate humidity. It's a warm day, so stay hydrated and wear light clothing.
```

## Setup

1. Clone the repository.
2. Import the workflows into n8n.
3. Add your OpenWeather API key.
4. Add your Google Gemini API key.
5. Run the workflow.

## License

MIT
