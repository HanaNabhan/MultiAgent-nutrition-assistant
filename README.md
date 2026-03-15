# AI NutriCoach: Multi-Agent Nutritional Intelligence
AI NutriCoach is an advanced nutritional analysis platform that leverages Multi-Agent Systems (MAS) to transform food imagery into actionable dietary insights. By orchestrating specialized AI agents, the system automates the pipeline from computer vision-based ingredient detection to personalized recipe generation and metabolic estimation.

## Overview
Unlike standard calorie trackers, AI NutriCoach utilizes a Vision-Language Model (VLM) backbone to "see" and "reason" about food. It doesn't just identify objects; it understands culinary contexts, dietary constraints, and nutritional density through a collaborative workflow of independent AI agents.

## System Architecture
The project is built on the CrewAI framework, employing a modular "Manager-Worker" architecture. Each task is handled by a specialized agent with a specific "role," "goal," and "backstory."

### The Multi-Agent Workflow
#### Detection Agent:
Utilizes WatsonX vision capabilities to extract a granular list of ingredients from raw image data.

#### Filtering Agent: 
Cross-references detected ingredients against a user’s specific dietary profile (e.g., Keto, Vegan, Celiac-friendly).

#### Nutritional Analyst: 
Performs high-fidelity estimation of macronutrients (Proteins, Fats, Carbs) and micronutrients.

#### Culinary Strategist: 
Synthesizes the output to generate optimized recipe suggestions that align with the user's health goals.

## Tech Stack
Orchestration: CrewAI (Sequential and Hierarchical workflows).

LLM/VLM: IBM WatsonX (Granular control over enterprise-grade AI models).

Interface: Gradio for a responsive, web-based UX.

Environment: Python-dotenv for secure API management.

## Project Structure
MultiAgent-nutrition-assistant/  
├── src/  
|   ├── config/  
│       ├── agents.yaml       # Defines Agent roles, goals, and LLM parameters  
│       └── tasks.yaml        # Logic for Task delegation and expected outputs  
│   ├── crew.py           # The "Brain" - Logic for agent collaboration  
│   ├── tools.py          # Custom Python tools for image processing/filtering  
│   └── main.py           # Entry point for CLI and Workflow execution  
└── app.py                # Gradio UI deployment script  
