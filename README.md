# FastAPI + MongoDB Minimal Setup

# Create virtual environment
python -m venv venv

# Activate venv (Windows Git Bash / Linux / Mac)
source venv/Scripts/activate 2>/dev/null || source venv/bin/activate

# Upgrade pip
python -m pip install --upgrade pip

# Install required packages
pip install fastapi uvicorn motor python-dotenv pydantic

# Create folders
mkdir -p app/routes

# Create files
touch app/main.py app/database.py app/schemas.py app/routes/user_routes.py
touch .env .gitignore requirements.txt README.md

# Freeze dependencies
pip freeze > requirements.txt

# Write .gitignore
cat <<EOF > .gitignore
venv/
__pycache__/
.env
EOF

# Write SHORT README
cat <<EOF > README.md
# FastAPI + MongoDB CRUD

Practice project to learn **FastAPI**, **MongoDB**, and **CRUD APIs**.

## Tech
- FastAPI
- Uvicorn
- MongoDB (Motor)
- Python 3.10+

## Run

uvicorn app.main:app --reload


## Docs
- http://127.0.0.1:8000/docs

Author: Yash Shedge
EOF

echo "Minimal setup completed"
