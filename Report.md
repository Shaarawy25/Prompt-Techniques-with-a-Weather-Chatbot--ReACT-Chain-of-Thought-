# **AI Chatbot Implementation Report**

## **1. Implementation Overview**
This project implements an AI chatbot that integrates weather forecasting, mathematical calculations, and a simulated web search function. The chatbot supports three reasoning strategies:

- **Basic Agent**: Provides direct responses using predefined tools.
- **Chain of Thought (CoT) Agent**: Breaks down complex queries into smaller steps before providing an answer.
- **ReAct (Reasoning + Acting) Agent**: Uses iterative reasoning and tool interactions to enhance response quality.

The chatbot leverages Groq’s API for LLM processing, WeatherAPI for real-time weather data, and Python’s `eval()` function for basic mathematical evaluations.

## **2. Example Conversations**

### **Basic Agent**
**User:** What’s the weather like in London?
**Chatbot:** It’s currently 15°C (59°F) and partly cloudy in London, with a light breeze at 10 km/h.

### **Chain of Thought Agent**
**User:** If it’s 10°C in New York and 25°C in Los Angeles, what’s the temperature difference?
**Chatbot:** First, I will retrieve the weather data for both cities. The temperatures are 10°C and 25°C, respectively. The difference is 25 - 10 = 15°C.

### **ReAct Agent**
**User:** Is it warmer in Tokyo or Sydney right now?
**Chatbot:** Let me check the current weather in both cities.
*Thought: I need to retrieve weather data for both locations.*
*Action: Call get_current_weather for Tokyo and Sydney.*
*Observation: Tokyo is 18°C, Sydney is 22°C.*
**Final Answer:** Sydney is currently warmer at 22°C compared to Tokyo’s 18°C.

## **3. Analysis of Reasoning Strategies**

| Agent Type       | Strengths | Weaknesses |
|-----------------|-----------|------------|
| **Basic Agent** | Quick and efficient for simple queries | Cannot break down complex requests |
| **Chain of Thought** | Handles multi-step reasoning better | Slightly slower due to extra steps |
| **ReAct Agent** | Most dynamic and flexible approach, adapts to queries effectively | Computationally expensive, may overcomplicate simple tasks |

The **Basic Agent** is effective for straightforward information retrieval but struggles with multi-step reasoning. The **CoT Agent** significantly improves response accuracy for mathematical operations or multi-variable weather queries. The **ReAct Agent** is the most advanced, dynamically adjusting its approach to complex queries, though it may introduce unnecessary reasoning for simple questions.

## **4. Challenges Encountered & Solutions**

### **1. Handling API Errors**
- **Challenge:** The chatbot occasionally returned errors when the WeatherAPI service was unavailable.
- **Solution:** Implemented error handling to return a user-friendly message when API responses fail.

### **2. Balancing Performance & Accuracy**
- **Challenge:** The ReAct agent sometimes performed unnecessary steps, making it slower.
- **Solution:** Optimized its logic to prioritize direct answers when queries were simple.

### **3. Managing User Queries with Ambiguities**
- **Challenge:** Users sometimes provided vague inputs like "Tell me about the weather."
- **Solution:** Implemented a clarification step where the bot asks, "Which location would you like the weather for?"

## **5. Conclusion**
This chatbot effectively showcases different AI reasoning strategies, each with its strengths and trade-offs. While the Basic Agent is useful for quick responses, the Chain of Thought and ReAct Agents offer deeper reasoning capabilities, improving response quality for complex queries. Future improvements could include a more sophisticated web search capability and a more adaptive reasoning approach to balance efficiency and depth dynamically.

