# 🏖️ VacAIgent: Streamlit-Integrated AI Crew for Trip Planning


## Introduction

Tripgent leverages the CrewAI framework to automate and enhance the trip planning experience, integrating a user-friendly Streamlit interface. This project demonstrates how autonomous AI agents can collaborate and execute complex tasks efficiently, now with an added layer of interactivity and accessibility through Streamlit.

**Check out the video below for code walkthrough** 👇


## CrewAI Framework

CrewAI simplifies the orchestration of role-playing AI agents. In VacAIgent, these agents collaboratively decide on cities and craft a complete itinerary for your trip based on specified preferences, all accessible via a streamlined Streamlit user interface.

## Streamlit Interface

git clone https://github.com/analyticsrepo01/trip_planner_agent

cd trip_planner_agent
streamlit run streamlit_app.py

## Using Local Models with Ollama

For enhanced privacy and customization, you can integrate local models like Ollama:

### Setting Up Ollama

- **Installation**: Follow Ollama's guide for installation.
- **Configuration**: Customize the model as per your requirements.

### Integrating Ollama with CrewAI

Pass the Ollama model to agents in the CrewAI framework:

```python
from langchain.llms import Ollama

ollama_model = Ollama(model="agent")

class TripAgents:
    # ... existing methods

    def local_expert(self):
        return Agent(
            role='Local Expert',
            tools=[SearchTools.search_internet, BrowserTools.scrape_and_summarize_website],
            llm=ollama_model,
            verbose=True
        )

```

## Benefits of Local Models

- **Privacy**: Process sensitive data in-house.
- **Customization**: Tailor models to fit specific needs.
- **Performance**: Potentially faster responses with on-premises models.

## License

VacAIgent is open-sourced under the MIT License.
