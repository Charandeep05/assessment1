Invoice Management System:
This project is a full-stack invoice management system built using Django REST Framework for the backend and React for the frontend. The system allows creating, updating, deleting, and viewing invoices with multiple line items.
Features:

Backend (Django REST Framework):
RESTful API with CRUD functionality for invoices.
Single endpoint for managing invoices and their line items (/api/invoices/).
Pagination for retrieving invoices.
Auto-computation of line totals and total invoice amount.
Field validation and error handling.

Frontend (React):
Responsive user interface for managing invoices.
Features include:
Invoice list view with pagination.
Form for creating and editing invoices.
Delete invoice functionality.
Basic search and filter options.
Uses modern React (hooks, functional components).
State management using Context API or Redux.

Tech Stack:
Backend: Python, Django REST Framework
Frontend: React (Functional Components, Hooks)
Database: SQLite (default Django database, replaceable with PostgreSQL)
Others: Axios, React Router

Setup Instructions:
Prerequisites:
Ensure the following are installed:

Python 3.8+
Node.js 14+
Git

Backend Setup

Clone the repository:
git clone <https://github.com/Charandeep05/assessment1>
cd invoice_management

Create and activate a virtual environment:
python -m venv env
source env/bin/activate  # On Windows, use `env\Scripts\activate`

Install dependencies:
pip install -r requirements.txt

Apply migrations and run the server:
python manage.py makemigrations
python manage.py migrate
python manage.py runserver

The backend server will run at http://127.0.0.1:8000.

Frontend Setup

Navigate to the frontend folder:
cd invoice-frontend

Install dependencies:
npm install

Start the development server:
npm start

The frontend will be available at http://localhost:3000.

API Endpoints
Base URL: /api/invoices/
GET: Retrieve a paginated list of invoices.
POST: Create a new invoice with details.
PUT: Update an existing invoice (provide id in the payload).
DELETE: Delete an invoice by ID.

Example Payload

import api from './api'; // Make sure this is the correct path to your api.js file

const invoiceData = {
  invoice_number: "INV001",
  customer_name: "John Doe",
  date: "2024-11-12",
  details: [
    {
      description: "Product A",
      quantity: 2,
      unit_price: 50.00
    },
    {
      description: "Product B",
      quantity: 1,
      unit_price: 75.00
    }
  ]
};

api.post('/invoices/', invoiceData)
  .then(response => {
    console.log('Invoice created:', response.data);
  })
  .catch(error => {
    console.error('Error creating invoice:', error);
  });
Deployment Instructions

Backend Deployment

Use Heroku for deploying the Django backend.

Add a Procfile in the backend folder:
web: gunicorn invoice_management.wsgi

Push the code to Heroku and ensure environment variables (like DATABASE_URL) are set.

Frontend Deployment

Use Vercel or Netlify for deploying the React frontend.

Build the project:
npm run build

Deploy the build directory using the chosen platform.

Bonus Features:

Unit tests for backend and frontend components.
Docker setup for containerized development.
Live deployment URLs (Heroku for backend and Vercel for frontend).

Evaluation Criteria:

Clean and maintainable code.
Fully functional CRUD operations.
Responsive and intuitive UI.
Proper error handling and validation










