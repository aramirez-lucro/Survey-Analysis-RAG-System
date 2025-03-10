# AI-Powered Survey Insights

## Project Description
AI-Powered Survey Insights is a web application that leverages advanced AI models to process and analyze user queries related to two survey datasets using Retrieval-Augmented Generation (RAG). This tool provides actionable insights from:

- **Dataset 1:** Sustainability Research Results
- **Dataset 2:** Christmas Research Results

The project consists of:

- **Backend:** A FastAPI-based service that processes user queries and interacts with the OpenAI API.
- **Frontend:** A simple HTML/CSS/JavaScript interface served using Nginx.
- **Dockerized Deployment:** Both backend and frontend are containerized for easy deployment using Docker and Docker Compose.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation and Setup](#installation-and-setup)
- [Usage Instructions](#usage-instructions)
- [API Documentation](#api-documentation)
- [Docker Instructions](#docker-instructions)
- [Deployment](#deployment)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Features

- **Interactive Query Interface:** Users can ask questions about the survey datasets in natural language.
- **AI-Generated Insights:** Retrieves precise answers using OpenAI’s models.
- **Dataset Comparison:** Compare insights between Sustainability and Christmas survey datasets.
- **User-Friendly Interface:** Clean, intuitive UI for easy interaction.
- **Dockerized Setup:** Simple container-based deployment with Docker Compose.

## Prerequisites

- **Docker:** Install Docker.
- **Docker Compose:** Comes bundled with Docker Desktop.
- **OpenAI API Key:** Obtain an API key from OpenAI.

## Installation and Setup

1. **Clone the Repository:**

	```sh
	git clone https://github.com/elcaiseri/Survey-Analysis-RAG-System.git
	cd Survey-Analysis-RAG-System
	```

2. **Set Up Environment Variables:**

	Create a `.env` file in the project root:

	```plaintext
	OPENAI_API_KEY=your-openai-api-key
	APP_TOKEN=your-app-token
	BACKEND_URL=http://localhost:8000
	FRONTEND_URL=http://localhost:5500
	```

	*Note: Replace the placeholders with actual values. Do not commit this file to version control.*

3. **Prepare the Data:**

	Run the exploratory data analysis script to prepare the datasets:

	```sh
	python eda.py
	```

4. **Build and Run the Containers:**

	Use Docker Compose to build and start the services:

	```sh
	docker-compose up --build
	```

	This will build both the frontend and backend containers and start them.

## Usage Instructions

1. **Access the Application:**

	Open your browser and go to `http://localhost:5500`.

2. **Interact with the Application:**

	- Enter a query in the input field (e.g., “How important is sustainability to consumers?”).
	- Select the relevant dataset from the dropdown (Sustainability or Christmas).
	- Click **Get Insights** to submit your query.

3. **View Results:**

	- The AI-generated response will be displayed below the form.
	- If there’s an error, it will be shown in the error message section.

## API Documentation

The backend exposes a POST endpoint for querying datasets.

- **Endpoint:** `/query`
- **Method:** POST
- **Description:** Processes a user query and returns AI-generated insights.

**Request Body Example:**

```json
{
  "query": "How important is sustainability to consumers?",
  "dataset": "sustainability"
}
```

**Response Example:**

```json
{
  "answer": "Sustainability is highly important to consumers, with 75% preferring eco-friendly products."
}
```

**Error Handling:**

- If the request fails, the API returns an appropriate HTTP status code and an error message.

## Docker Instructions

### Building and Running the Containers

1. **Build the Docker Containers:**

	```sh
	docker-compose build
	```

2. **Start the Containers:**

	```sh
	docker-compose up
	```

3. **Run in Detached Mode (Optional):**

	```sh
	docker-compose up -d
	```

### Stopping the Containers

```sh
docker-compose down
```

### Rebuilding After Code Changes

If you make changes to the code, rebuild the containers:

```sh
docker-compose up --build
```

## Deployment

To deploy the application to a production environment, consider using one of these services:

- **AWS Elastic Beanstalk**
- **Google Cloud Run**
- **Azure App Service**
- **Heroku**

### Deployment Checklist:

- Securely manage environment variables (e.g., using AWS Secrets Manager).
- Configure CORS policies to allow frontend-backend communication.
- Use HTTPS in production to ensure secure data transmission.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

## Acknowledgements

- **OpenAI:** For providing the API and language models.
- **FastAPI:** For the robust and lightweight web framework.
- **Docker:** For containerization and simplified deployment.
- **Nginx:** For serving static files efficiently.
- **Community Resources:** Tutorials and documentation that helped shape this project.

Feel free to contribute to this project by opening issues or submitting pull requests. If you have any questions, contact us at iqasem4444@gmail.com.
