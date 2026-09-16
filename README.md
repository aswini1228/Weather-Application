AI Weather Assistant

AI Weather Assistant is an AI-powered conversational weather application that provides real-time weather information for cities around the world.

The application combines Large Language Models (LLMs), Function Calling, Natural Language Processing, and the Open-Meteo Weather API to understand user queries and retrieve accurate, real-time weather information through a simple conversational interface.

Live Demonstration

Live Application:
[http://localhost:8501/ ]
<img width="742" height="369" alt="APPLICATION1" src="https://github.com/user-attachments/assets/9192dd02-10fa-4075-99af-38a2dc985224" />
<img width="562" height="285" alt="APPLICATION2" src="https://github.com/user-attachments/assets/24acb5e4-c5f9-4d9b-a354-0fb29d548878" />


Project Overview

Traditional weather applications often require users to manually search for a location and navigate through multiple options.

This project provides a more natural approach. Users can simply ask questions such as:

«"What's the weather like in Chennai?"»

The AI assistant understands the user's request, identifies the required city, invokes the appropriate weather function, retrieves real-time data from the Open-Meteo API, and generates a natural-language response.

Key Features

- Conversational AI Interface for natural-language weather queries
- LLM Function Calling for intelligent tool selection
- Real-Time Weather Data retrieved from Open-Meteo APIs
- Automatic City Identification from user queries
- Temperature, humidity, and wind-speed information
- Interactive chat interface built with Streamlit
- Geographical location detection using Open-Meteo Geocoding API
- Secure Hugging Face token management
- Environment-variable based configuration
- API and network error handling
- Support for cities across different countries

Technologies Used

Technology| Purpose
Python| Core application development
Streamlit| Interactive web interface
Hugging Face| LLM integration
Qwen2.5-72B-Instruct| Natural-language understanding and response generation
Open-Meteo| Real-time weather data
Open-Meteo Geocoding API| City and coordinate identification
Requests| HTTP/API communication
python-dotenv| Environment variable management
Git & GitHub| Version control and project management

AI Model

The application uses:

Qwen/Qwen2.5-72B-Instruct

The model is integrated using the Hugging Face InferenceClient.

The LLM is responsible for understanding the user's natural-language request and determining when the "get_weather()" function needs to be executed.

This enables the application to connect conversational AI with an external real-time data source.

How It Works

The application follows a simple AI-powered workflow:

                    User Query
                        |
                        v
              Natural Language Input
                        |
                        v
              Hugging Face LLM
                        |
                        v
                Function Calling
                        |
                        v
              get_weather(city)
                        |
                        v
        Open-Meteo Geocoding API
                        |
                        v
              Latitude & Longitude
                        |
                        v
          Open-Meteo Weather API
                        |
                        v
             Current Weather Data
                        |
                        v
                LLM Processing
                        |
                        v
             Natural-Language Reply
                        |
                        v
              Streamlit Interface

Function Calling

Function Calling is one of the core concepts demonstrated in this project.

The LLM is provided with a custom weather tool:

get_weather(city)

When the user asks a weather-related question, the model determines whether the weather function should be called.

Example

User:
What's the weather in Chennai?

        ↓

LLM:
get_weather("Chennai")

        ↓

Geocoding API:
Find Chennai coordinates

        ↓

Weather API:
Retrieve current weather

        ↓

LLM:
Generate response

        ↓

Assistant:
Chennai is currently 30°C with 72% humidity
and a wind speed of 14 km/h.

This demonstrates how an LLM can interact with external APIs through tool/function calling.

API Integration

Open-Meteo Geocoding API

The Geocoding API converts a city name into geographical coordinates.

https://geocoding-api.open-meteo.com/v1/search

The application uses the returned:

- City name
- Country
- Latitude
- Longitude

to identify the required location.

Open-Meteo Forecast API

The Forecast API retrieves current weather information using the latitude and longitude.

https://api.open-meteo.com/v1/forecast

The application retrieves:

- Temperature
- Relative humidity
- Wind speed

Example Queries

Users can interact with the assistant using natural language.

What's the weather in Chennai?

Tell me the temperature in Mumbai.

What is the humidity in Delhi?

How windy is it in Bengaluru?

Give me the current weather in London.

What's the weather like in New York?

The assistant automatically identifies the city and retrieves the relevant weather information.

Example Output

Location: Chennai, India

Temperature: 30 °C
Humidity: 72%
Wind Speed: 14 km/h

Project Structure

AI-Weather-Application/
│
├── Weather app.py
├── Weather requirements.txt
├── README.md
├── .gitignore
└── .env

Environment Configuration

The Hugging Face API token is stored locally using an environment variable.

Create a ".env" file:

HF_TOKEN=your_huggingface_token

The application loads the token securely using:

from dotenv import load_dotenv
import os

load_dotenv()

HF_TOKEN = os.getenv("HF_TOKEN")

".gitignore"

The ".env" file must never be committed to GitHub.

.env
__pycache__/
*.pyc
.venv/
venv/

Installation

Clone the Repository

git clone https://github.com/YOUR-USERNAME/AI-Weather-Application.git

Navigate into the project:

cd AI-Weather-Application

Install Dependencies

py -m pip install -r "Weather requirements.txt"

Main dependencies:

streamlit
requests
python-dotenv
huggingface-hub

Run the Application

Start the Streamlit application:

py -m streamlit run "Weather app.py"

The application will run locally at:

http://localhost:8501

Open the address in a web browser to interact with the application.

Error Handling

The application includes basic error handling for:

- Invalid city names
- City search failures
- Weather API failures
- Network connection errors
- Missing Hugging Face API tokens
- Unexpected application errors

This helps provide a smoother user experience when external services are unavailable or invalid input is provided.

Security

Security practices implemented in the project include:

- API credentials are stored using environment variables
- Sensitive tokens are not hard-coded
- ".env" is excluded through ".gitignore"
- API credentials should never be uploaded to public repositories

Never expose Hugging Face access tokens or other private credentials in source code.

Screenshots

Application Interface

"AI Weather Assistant" (screenshot1.png)

Weather Information

"Weather Response" (screenshot2.png)

Future Enhancements

The project can be further enhanced with:

- Multi-day weather forecasts
- Feels-like temperature
- Rain probability
- Weather condition descriptions
- Sunrise and sunset information
- Weather trend visualization
- Interactive weather maps
- Severe weather alerts
- Automatic user-location weather
- Multi-language conversational support
- Voice-based weather queries
- Improved mobile responsiveness

Learning Outcomes

This project provided practical experience in:

- Python application development
- REST API integration
- Large Language Model integration
- LLM Function Calling
- Natural Language Processing
- JSON data handling
- Prompt-based AI interaction
- Environment variable management
- Streamlit application development
- API error handling
- Git and GitHub workflow
- AI-powered application development

Project Highlights

This project demonstrates the practical integration of AI with real-time external data.

Instead of using an LLM only for generating text, the application allows the model to understand user intent, select an appropriate function, retrieve live information through an API, and generate a meaningful conversational response.

This makes the project a practical example of building an AI agent-style application using LLM Function Calling and APIs.

Author
ASWINI.S

B.Sc. Computer Science with Artificial Intelligence

Areas of Interest

- Artificial Intelligence
- Machine Learning
- Python
- Data Analytics
- AI Application Development
- Space Technology

License

This project is developed for educational and learning purposes.
