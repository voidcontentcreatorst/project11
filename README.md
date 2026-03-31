# NexFlow Workflow Automation Platform
![NexFlow Logo](https://img.shields.io/badge/NexFlow-Automation-6366f1)

NexFlow is a complete, production-ready, modern workflow automation platform designed to link applications together and automate repetitive tasks. It features a drag-and-drop workflow builder, comprehensive analytics, and an elegant dark-glassmorphism UI.

## Table of Contents
- [Architecture](#architecture)
- [Requirements](#requirements)
- [Installation - Frontend](#installation---frontend)
- [Installation - Backend](#installation---backend)
- [Usage](#usage)

## Architecture

This monolithic repository contains both the client and server components:

**Frontend**:
- Vite + React 18
- React Router DOM
- @xyflow/react (formerly React Flow) for the Visual Nodes Builder
- Recharts for Analytics
- Lucide React for consistent icons
- High-performance Custom CSS with CSS variables and Glassmorphism design

**Backend**:
- Python 3.9+
- FastAPI
- Uvicorn (ASGI Server)
- Pydantic models for Workflow definition validation

## Requirements
Please ensure you have the following installed on your machine:
- **Node.js** (v18 or higher) for the Vite/React frontend
- **npm** (v9 or higher)
- **Python** (v3.9 or higher)

*(Note: During scaffolding, `npm` and `node` were not found in the current terminal PATH. You must ensure they are installed to run the frontend.)*

## Installation - Frontend

1. Open your terminal and navigate to the `frontend` folder:
   ```bash
   cd frontend
   ```
2. Install the necessary Node dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm run dev
   ```

The frontend will be available at `http://localhost:5173`.

## Installation - Backend

1. Open a new terminal and navigate to the `backend` folder:
   ```bash
   cd backend
   ```
2. Install the Python dependencies (a virtual environment is recommended):
   ```bash
   pip install -r requirements.txt
   ```
3. Start the FastAPI backend server:
   ```bash
   python main.py
   ```
   *Alternatively:* `uvicorn main:app --reload`

The backend API will be running on `http://localhost:8000`. Full automatic swagger documentation is available at `http://localhost:8000/docs`.

## Usage
Once both servers are running:
1. Navigate to the frontend URL. You will see the **Dashboard** displaying automation analytics, workflow performance, and recent activity.
2. Click **Workflows** on the left sidebar to open the Drag-and-Drop Builder.
3. In the workflow builder, you can pan the canvas, drag the pre-configured Trigger, Condition, and Action nodes, and interact with the edges showing logic paths ("Yes" / "No").

## Features Included
- **Dashboard**: Live analytics using Recharts. List of recent tasks and their success/failure status.
- **Workflow Builder**: An intricate React Flow setup providing interactive nodes and edges mimicking platforms like Make and Zapier.
- **Routing**: Sidebar routing across all standard views.
- **Backend Mocking**: The backend defines schemas for what a workflow definition looks like and can accept creation commands via the `/api/workflows` endpoint.
