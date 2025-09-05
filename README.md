# Synnsia – AI Music Generation SaaS

## Overview

Synnsia is a SaaS application that generates professional-quality music using AI. Users can create unique tracks in seconds, fine-tune compositions, and export them in multiple formats ready for commercial or personal use. The tool leverages state-of-the-art AI models for music composition, arrangement, and mastering. Synnsia includes user authentication, a credit-based usage system, Stripe integration, and scalable serverless processing.

Technologies used: **Next.js 15, React, TypeScript, Tailwind CSS, ShadCN UI, Auth.js, Python, FastAPI, Stripe, Modal, Inngest, AWS S3**, and more.

### Key Features

- 🎶 AI-powered music generation in multiple genres and moods  
- 🔊 Adjustable tempo, instruments, and style for personalized tracks  
- 📝 Automatic track transcription and notation export (MIDI/Sheet Music)  
- 💽 High-quality audio rendering with GPU acceleration  
- 🧠 LLM-powered style guidance and suggestions with Gemini 2.5 Pro  
- 📊 Queue system with Inngest for efficient request handling  
- 💳 Credit-based usage system  
- 💰 Stripe integration for purchasing credit packs  
- 👤 Secure user authentication  
- 📱 Responsive web interface built with Next.js and Tailwind CSS  
- 🎛️ Dashboard for generating, previewing, and downloading tracks  
- ⏱️ Serverless background processing with Modal  
- 🌐 FastAPI endpoints for AI music generation  
- 🎨 Modern UI using ShadCN components

## Setup

### Clone the Repository

```bash
git clone --recurse-submodules https://github.com/YourUsername/synnsia.git
```

### Install Python

Install **Python 3.12** and create a virtual environment: [Python Download](https://www.python.org/downloads/)

### Backend

Navigate to the backend folder:

```bash
cd synnsia-backend
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Modal setup:

```bash
modal setup
```

Run on Modal:

```bash
modal run main.py
```

Deploy backend:

```bash
modal deploy main.py
```

### Frontend

Navigate to the frontend folder:

```bash
cd synnsia-frontend
npm install
```

Run locally:

```bash
npm run dev
```

### Queue

Run the local development queue with Inngest:

```bash
cd synnsia-frontend
npm run inngest-dev
```

## AWS Setup

**S3 Bucket CORS Policy:**

```json
[
    {
        "AllowedHeaders": ["Content-Type", "Content-Length", "Authorization"],
        "AllowedMethods": ["PUT"],
        "AllowedOrigins": ["*"],
        "ExposeHeaders": ["ETag"],
        "MaxAgeSeconds": 3600
    }
]
```

**IAM Policy for S3 Access:**

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": ["s3:ListBucket"],
            "Resource": "[S3 ARN here]"
        },
        {
            "Effect": "Allow",
            "Action": ["s3:GetObject", "s3:PutObject"],
            "Resource": "[S3 ARN here]/*"
        }
    ]
}
```

## LLM for Style Guidance

Create a Gemini API key for AI music style suggestions:  
[Gemini API Quickstart](https://ai.google.dev/gemini-api/docs/quickstart?lang=python)

## Example Tracks for Testing

- [Epic Cinematic Orchestral](https://www.youtube.com/watch?v=example1)  
- [Lo-fi Chill Beats](https://www.youtube.com/watch?v=example2)
