# CloudMart

A simple static e-commerce demo website with a blue and white theme, featuring a chat widget powered by OpenAI. Built with Flask for easy deployment on AWS LightSail using Docker.

## Features
- Blue and white modern e-commerce UI
- Three demo products
- Floating chat widget (bottom right) powered by OpenAI (GPT-3.5-turbo)
- Fast, simple, and ready for container deployment

## Setup

1. **Clone the repository**
2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
3. **Set your OpenAI API key**
   - Create a `.env` file or set the environment variable:
     ```bash
     export OPENAI_API_KEY=your_openai_api_key
     ```
4. **Run the app**
   ```bash
   flask run --host=0.0.0.0 --port=5000
   ```
   Or for production:
   ```bash
   gunicorn -b 0.0.0.0:5000 app:app
   ```

## Docker Deployment

1. **Build the Docker image**
   ```bash
   docker build -t cloudmart .
   ```
2. **Run the container**
   ```bash
   docker run -d -p 5000:5000 -e OPENAI_API_KEY=your_openai_api_key cloudmart
   ```

## Deploying on AWS LightSail
- Launch a container service
- Push your Docker image or use the Dockerfile provided
- Set the `OPENAI_API_KEY` environment variable in the service settings
- Expose port 5000

## Customization
- Edit `templates/index.html` and `static/style.css` for UI changes
- Update product images in `static/`

## License
MIT 