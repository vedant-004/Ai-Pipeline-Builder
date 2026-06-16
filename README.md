AI Pipeline Builder
This is a full-stack, no-code AI workflow orchestrator. It allows users to design complex, multi-step AI pipelines by dragging and dropping blocks onto a canvas and wiring them together.

I built this as part of a technical challenge to demonstrate how to create modular, scalable workflow tools.

What’s under the hood?
Frontend: Built with React and React Flow. I used Zustand to manage the state of the canvas and created a custom node abstraction system. This means adding new functionality (like a Timer or Database node) takes minutes, not hours, because all the shared logic lives in a single BaseNode component.

Dynamic Logic: The "Text" node in this app is pretty smart—it parses your input for variables like {{ user_input }} using Regex and automatically creates connection ports on the fly.

Backend: Powered by Python and FastAPI.

Graph Validation: I implemented a custom Directed Acyclic Graph (DAG) validator using a Depth-First Search algorithm. It analyzes the pipeline before it runs to make sure there are no infinite loops that could crash the system.

Why I built it this way
I wanted the UI to feel like a premium tool, so I went with a clean, dark-mode design using custom CSS. I didn't want to rely on heavy UI libraries, so everything you see is built from scratch to ensure the code stays lightweight and fast.

Getting started
If you want to run this locally:

Backend:

cd backend

pip install -r requirements.txt (or install FastAPI/Pydantic)

uvicorn main:app --reload --port 8001

Frontend:

cd frontend

npm install

npm start
