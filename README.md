# Game Meta Assistant

An AI-powered web application that provides expert strategies, tips, and guidance for classic Super Nintendo and SEGA games. Built with Google Gemini API integration to deliver intelligent, context-aware responses about game mechanics, strategies, and builds.

## Description

The Game Meta Assistant is an interactive web application designed to help gamers improve their skills and understanding of classic retro games. By leveraging Google's Gemini AI model with integrated search capabilities, the application acts as a knowledgeable gaming companion that can answer questions about strategies, character builds, level walkthroughs, and advanced techniques for iconic games like Super Mario, Donkey Kong, and Sonic.

The application features a interface where users can select their game of interest, input their API key, and ask specific questions. The AI processes these queries with game-specific context and returns concise, actionable advice formatted in Markdown for easy readability. The system is designed to provide accurate, up-to-date information by utilizing Google Search integration, ensuring responses reflect current game knowledge and community strategies.

## Live Demo

https://luizaugustoliveira.github.io/assistente-de-meta/

<img width="623" height="373" alt="init" src="https://github.com/user-attachments/assets/ff6ab301-27a5-4d81-81c1-a0b46590137a" />

<img width="621" height="962" alt="super-mario" src="https://github.com/user-attachments/assets/d6183878-ec0e-44c7-9aae-36c5b6e2f9b7" />

<img width="648" height="1077" alt="donkey-kong" src="https://github.com/user-attachments/assets/aef06cc5-1075-4ae9-8d90-4e0c6afb83fd" />

## Main Application Flow

```mermaid
graph TD
    A[User Opens Application] --> B[Display Main Interface]
    B --> C[User Inputs API Key]
    B --> D[User Selects Game]
    B --> E[User Types Question]
    
    C --> F[Form Validation]
    D --> F
    E --> F
    
    F --> G{All Fields Valid?}
    G -->|No| H[Show Alert Message]
    H --> B
    
    G -->|Yes| I[User Clicks Ask Button]
    I --> J[Disable Button]
    J --> K[Show Loading State]
    K --> L[Build AI Prompt]
    
    L --> M[Construct Gemini Request]
    M --> N[Game Context]
    M --> O[User Question]
    M --> P[System Rules]
    M --> Q[Current Date]
    
    N --> R[Add Google Search Tool]
    O --> R
    P --> R
    Q --> R
    
    R --> S[Send POST Request to Gemini API]
    S --> T{API Response Success?}
    
    T -->|Error| U[Log Error to Console]
    U --> V[Re-enable Button]
    V --> W[Remove Loading State]
    
    T -->|Success| X[Extract AI Response Text]
    X --> Y[Convert Markdown to HTML]
    Y --> Z[Display Response in UI]
    Z --> AA[Show Response Container]
    AA --> V
    
    W --> AB[Ready for Next Question]
    AB --> B
    
    style A fill:#2c3e50,color:#fff
    style I fill:#3498db,color:#fff
    style S fill:#e74c3c,color:#fff
    style X fill:#27ae60,color:#fff
    style Y fill:#f39c12,color:#fff
    style Z fill:#9b59b6,color:#fff
```

## Features

- Ask questions about strategies, builds, and tips for games like Mario, Donkey Kong, and Sonic
- AI-generated responses powered by Google Gemini 2.5 Flash
- Responsive and intuitive user interface
- Automatic conversion of Markdown responses to HTML
- Form validation with visual feedback
- Loading states for better user experience
- Google Search integration for up-to-date game information
- Context-aware responses specific to each game
- Character limit enforcement for concise answers

## Technologies Used

- **HTML5**: Semantic structure and form elements
- **CSS3**: Modern styling and responsive design
- **JavaScript (ES6+)**: Async/await, fetch API, DOM manipulation
- **Showdown.js**: Markdown to HTML conversion library
- **Google Gemini API**: AI language model with search capabilities
- **Gemini 2.5 Flash**: Latest model for fast, accurate responses

## Project Structure

```
assistente-de-meta/
├── index.html          # Main HTML structure
├── style.css           # Styling and responsive design
├── script.js           # Application logic and API integration
├── assets/             # Images and demo screenshots
│   ├── demo.png
│   └── init.png
└── README.md          # Documentation
```

## How to Run Locally

1. Clone the repository:
```bash
git clone https://github.com/luizaugustoliveira/assistente-de-meta.git
```

2. Navigate to the project directory:
```bash
cd assistente-de-meta
```

3. Use the Live Server extension in Visual Studio Code or any local server:

4. Create a Google Cloud project:
   - Visit: https://cloud.google.com/

5. Get your Gemini API key:
   - Visit: https://ai.google.dev/gemini-api/docs
   - Enable the Gemini API for your project
   - Create an API key in the credentials section

6. Open the application in your browser and enter your API key

## How to Use

1. Open the application in your web browser
2. Enter your Google Gemini API key in the password field
3. Select a game from the dropdown menu (Mario, Donkey Kong, or Sonic)
4. Type your question about strategies, builds, or tips
5. Click the "Ask" button
6. Wait for the AI to generate a response
7. Read the formatted answer displayed below the form

## API Integration Details

The application uses the Google Gemini API with the following configuration:

- **Model**: gemini-2.5-flash
- **Endpoint**: `https://generativelanguage.googleapis.com/v1beta/models/`
- **Method**: POST request with JSON payload
- **Tools**: Google Search integration for real-time information
- **Response Format**: Markdown text (max 500 characters)

## AI Prompt Engineering

The application uses a structured prompt system:

- **Specialty**: Defines the AI as a game-specific meta assistant
- **Task**: Instructs the AI to answer based on game knowledge
- **Rules**: 
  - Only answer if confident about the information
  - Reject off-topic questions
  - Consider current date for patch-specific advice
  - Research current game patches
- **Response Format**: Direct, concise, Markdown-formatted answers

## Supported Games

- **Mario**: Classic Super Nintendo platformer
- **Donkey Kong**: Iconic arcade and SNES titles
- **Sonic**: SEGA's legendary speedrunning platformer

## Security Considerations

- API keys are entered by users and not stored
- API keys are sent securely via HTTPS
- No server-side storage of user data
- Client-side only application

## Author

**Luiz Augusto Oliveira**
