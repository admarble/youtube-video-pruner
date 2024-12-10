# Video Pruner

A self-hosted web application that allows users to analyze YouTube videos, automatically identify and remove filler content, and create condensed versions for efficient information consumption.

## Setup

1. Clone the repository:
```bash
git clone https://github.com/admarble/youtube-video-pruner.git
cd youtube-video-pruner
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Copy `.env.example` to `.env` and fill in your credentials:
```bash
cp .env.example .env
```

5. Run the application:
```bash
uvicorn src.main:app --reload
```

## API Usage

### Download a video
```bash
curl -X POST http://localhost:8000/videos/ \
  -H "Content-Type: application/json" \
  -d '{"url": "https://youtube.com/watch?v=...", "quality": "720p", "user_id": "user123"}'
```

### Check video status
```bash
curl http://localhost:8000/videos/{video_id}
```

## Development

- Run tests: `pytest`
- Format code: `black src tests`
- Check types: `mypy src`