# Weather Advisor
A Python application that combines weather data access with conversational AI capabilities. Ask natural language questions about weather and get intelligent responses with beautiful visualizations.

## Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [AI Integration](#ai-integration)
- [Requirements](#requirements)
- [Troubleshooting](#troubleshooting)

## Features
- **Natural Language Processing**: Ask weather questions in plain English
- **Global Weather Data**: Get weather information for any location worldwide
- **Interactive Visualizations**: Temperature trends and precipitation forecasts
- **AI-Powered Responses**: Conversational replies using advanced AI models
- **Dual Interface**: Both direct lookup and natural language modes
- **Robust Error Handling**: Graceful handling of API failures and edge cases

## Installation
### Prerequisites
- Python 3.7 or higher
- Google Colab account (recommended) or Jupyter Notebook
- Internet connection for weather data and AI services

### Required Packages
The application will automatically install required packages:
```bash
!pip install fetch-my-weather
!pip install hands-on-ai
!pip install pyinputplus
```

### Environment Setup
Clone the repository:
```bash
git clone https://github.com/YOUR-USERNAME/weather-advisor.git
cd weather-advisor
```

Set up API credentials:
```python
import os
os.environ['HANDS_ON_AI_SERVER'] = 'http://ollama.serveur.au'
os.environ['HANDS_ON_AI_MODEL'] = 'granite3.2'
os.environ['HANDS_ON_AI_API_KEY'] = 'your-api-key-here'
```

## Quick Start
### Option 1: Google Colab (Recommended)
1. Open the `weather-advisor.ipynb` notebook in Google Colab
2. Run the setup cell to install dependencies
3. Enter your API key when prompted
4. Run all cells to start the application
5. Follow the interactive menu prompts

### Option 2: Local Jupyter
1. Install Jupyter: `pip install jupyter`
2. Start Jupyter: `jupyter notebook`
3. Open `weather-advisor.ipynb`
4. Run all cells and follow prompts

### Option 3: Python Script
```python
# Import the main function
from weather_advisor import main_menu

# Start the application
main_menu()
```

## Usage
### Interactive Menu
When you start the application, you'll see:
```
Welcome to the Weather Advisor!

--- Main Menu ---
What would you like to do?
1. Get weather by location (Direct)
2. Ask a weather question (Natural Language)
3. Exit
```

### Mode 1: Direct Weather Lookup
- Enter a city name (e.g., "London", "New York", "Tokyo")
- Choose number of forecast days (1-5)
- View current conditions and forecast
- Optional: Generate visualizations

### Mode 2: Natural Language Questions
Ask questions like:
- "What's the temperature in London tomorrow?"
- "Will it rain in Paris this weekend?"
- "How's the weather in Tokyo today?"
- "What's the humidity in Sydney on Friday?"

The AI will:
- Parse your question to extract location, time, and weather attribute
- Fetch relevant weather data
- Generate a natural, conversational response
- Offer optional visualizations

### Example Interaction
```
Ask your weather question: What's the temperature in London tomorrow?

Parsed Question: {'location': 'London', 'time_period_keyword': 'tomorrow', 
                 'days_offset': 1, 'attribute': 'temperature'}

Fetching weather forecast for London (including tomorrow's forecast)...

--- Weather Advisor Says ---
Tomorrow in London, you can expect a high of 19°C and a low of 6°C. 
It should be partly cloudy conditions. The current temperature today 
is 14°C, so tomorrow will be slightly warmer overall!

Would you like to see visualisations for London? (yes/no): yes
```

## Project Structure
```
weather-advisor/
├── README.md                          # This file
├── weather-advisor.ipynb              # Main Jupyter notebook
├── ai-conversations/                  # AI conversation documentation
│   ├── conversation1.txt              # Implementation options exploration
│   ├── conversation2.txt              # Weather data development
│   ├── conversation3.txt              # Natural language processing
│   ├── conversation4.txt              # Visualization creation
│   └── conversation5.txt              # Code refinement
└── requirements.txt                   # Python dependencies (optional)
```

## AI Integration
This project uses the `hands-on-ai` package with the `granite3.2` model for:
- **Natural Language Understanding**: Parsing user questions
- **Conversational Responses**: Generating human-like weather explanations
- **Context Awareness**: Providing relevant, personalized information

### AI Features
- **Fallback Handling**: If AI is unavailable, template responses ensure functionality
- **Intentional Prompting**: Strategic prompts for better AI responses
- **Context Building**: Rich context including current conditions and forecasts

## Requirements
### Core Dependencies
- `fetch-my-weather` - Weather data retrieval
- `hands-on-ai` - AI conversation capabilities
- `pyinputplus` - Enhanced user input handling
- `matplotlib` - Data visualization
- `datetime` - Date/time processing
- `re` - Regular expressions for text parsing

### System Requirements
- **Memory**: 512MB+ available RAM
- **Network**: Stable internet connection
- **Browser**: Modern web browser for Colab/Jupyter

## Troubleshooting
### Common Issues
1. **API Key Error**
   - **Error**: Authentication failed
   - **Solution**: Ensure your `HANDS_ON_AI_API_KEY` is set correctly
2. **Weather Data Not Found**
   - **Error**: No data returned from weather service
   - **Solution**: Check location spelling, try major city names
3. **Visualization Not Appearing**
   - **Error**: Charts not displaying in Jupyter
   - **Solution**: Run `%matplotlib inline` in a cell before visualizations
4. **Input Prompts Hanging**
   - **Error**: Input field not appearing after visualization
   - **Solution**: Interrupt cell (Ctrl+C) then continue - this is a known Jupyter issue

### Debug Mode
Add debug output to troubleshoot:
```python
# Enable debug output
import logging
logging.basicConfig(level=logging.DEBUG)

# Check data flow
print(f"Weather data: {weather_data}")
print(f"Parsed question: {parsed_question}")
```

### Performance Tips
- Restart kernel if memory usage gets high
- Clear output regularly in long sessions
- Use smaller forecast windows (1-3 days) for faster responses

## Contributing
This is an academic project, but suggestions are welcome:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request with detailed description

## License
This project is created for educational purposes as part of a university assignment.

## Author
Sihao Wang - University Assignment Project  
Contact: wangsihao74@gmail.com  
GitHub: @23165063

## Next Steps
- Run the application following the Quick Start guide
- Test different question types to explore AI capabilities
- Generate visualizations for various locations
- Review conversation files to understand development process
- Experiment with edge cases to see error handling

Happy weather forecasting!