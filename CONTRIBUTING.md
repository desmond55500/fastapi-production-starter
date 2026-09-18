# Contributing

Thanks for taking a look at the project.

## Local workflow

1. Create a virtual environment.
2. Install `requirements.txt`.
3. Copy `.env.example` to `.env`.
4. Run the test suite with `pytest -q`.
5. Start the API with `uvicorn app.main:app --reload`.

## Pull requests

Keep changes focused, add or update tests for behavior changes, and avoid committing generated files, secrets, local databases, or personal data.
