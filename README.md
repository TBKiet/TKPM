# Science Video AI

An AI-powered platform for generating educational science videos. The platform uses various AI services to generate scripts, synthesize voice narration, create visuals, and assemble complete educational videos.

## Architecture

The project follows a microservices architecture with the following components:

- **Script Generation**: Generates educational scripts using AI
- **Voice Synthesis**: Converts scripts to natural-sounding voice narration
- **Visual Generation**: Creates relevant visuals and animations
- **Video Assembly**: Combines audio and visuals into final videos
- **Export Distribution**: Handles video export and distribution
- **User Interface**: Web interface for interacting with the platform

## Getting Started

### Prerequisites

- Python 3.8+
- Node.js 16+
- Docker (optional)
- Google Cloud credentials
- Gemini API key

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/science-video-ai.git
cd science-video-ai
```

2. Set up environment variables:
- Copy `.env.example` to `.env` in each service directory
- Fill in the required API keys and credentials

3. Set up Google Cloud credentials:
- Place your Google Cloud service account key in `secrets/google-credentials.json`
- See `secrets/README.md` for detailed instructions

4. Install dependencies for each service:
```bash
# For each Python service
cd services/service-name
python -m venv venv
source venv/bin/activate  # or `venv\Scripts\activate` on Windows
pip install -r requirements.txt

# For the user interface
cd services/user-interface
npm install
```

## Development

Each service can be run independently in development mode. See the README.md in each service directory for specific instructions.

## Deployment

Each service includes a Dockerfile for containerized deployment. See the deployment documentation in each service for detailed instructions.

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- OpenAI for GPT models
- Google Cloud for Text-to-Speech
- Gemini for advanced AI capabilities
