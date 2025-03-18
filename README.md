# **AI Chatbot with Weather & Calculation Tools**  

## **Overview**  
This chatbot integrates weather information, mathematical calculations, and simulated web search functionalities. It supports different reasoning modes, including basic interactions, Chain-of-Thought (CoT), and the ReAct (Reasoning + Acting) approach.  

## **Features**  
- **Weather Queries**: Fetch current weather and forecasts for any location.  
- **Mathematical Evaluations**: Solve basic and complex expressions.  
- **Web Search Simulation**: Provide predefined responses to common topics.  
- **Agent Modes**:  
  - **Basic**: Simple weather assistant.  
  - **Chain of Thought (CoT)**: Step-by-step problem-solving.  
  - **ReAct**: Uses reasoning to decide the best tool(s) for the query.  

## **Setup & Installation**  
1. Clone the repository.  
2. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```  
3. Create a `.env` file and add your API keys:  
   ```env
   API_KEY=your_groq_api_key
   LLM_MODEL=your_llm_model_name
   WEATHER_API_KEY=your_weather_api_key
   ```  
4. Run the chatbot:  
   ```bash
   python chatbot.py
   ```  

## **Usage**  
When prompted, choose an agent type:  
- **1** → Basic  
- **2** → Chain of Thought  
- **3** → ReAct  

Then, enter queries like:  
- *"What's the weather in Paris?"*  
- *"Solve (5 + 3) * 2"*  
- *"Will it rain in Tokyo in the next 3 days?"*  

## **License**  
This project is open-source. Feel free to modify and improve it! 
