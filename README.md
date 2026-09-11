# Rent Affordability Calculator

# Problem
Renters have no reliable way to know if what they're being asked to pay is actually reasonable for the area they live in. Rent prices are set by landlords and management companies with access to market data that renters never see, leaving people either overpaying without realizing it or unsure whether a listing is actually a fair deal. Existing rental sites only show what landlords are currently asking, not what's affordable based on real income data for that area.
# Users
Renters, especially people moving to a new city or apartment hunting for the first time (e.g., a college student about to graduate), and anyone comparing multiple apartments or cities and wanting an objective, data-backed answer instead of guesswork.
# Solution
A web-based rent affordability calculator that pulls real median rent and median household income data by zip code from public government sources (HUD and the US Census Bureau). A user enters a zip code and their rent, and the tool compares it against that area's actual median rent and income using the standard affordability guideline (rent should not exceed 30% of gross income). The result tells the user whether their rent is reasonable, high, or low for their specific area, with a visualization showing where it falls relative to the local distribution.
# Features
Zip code + rent input form
Affordability verdict (reasonable / high / low) based on the 30% income guideline
Median rent and median income lookup by zip code
Visualization of entered rent against the local rent distribution
Side-by-side comparison across multiple zip codes
# Technology
Python — core language, chosen over a JS full stack because this project is data-cleaning and analysis heavy
pandas — cleaning and normalizing HUD/Census datasets
Flask — lightweight backend and web interface
PostgreSQL — relational database, a better fit than a document store since the data is tabular (zip code, income, rent) and relies on aggregate queries
requests — pulling data from public APIs (Census ACS)
# Data Sources
HUD Fair Market Rents
US Census Bureau ACS API
Setup
bash
# Clone the repo
git clone <repo-url>
cd rent-affordability-calculator

# Set up a virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up PostgreSQL database
createdb rent_calculator

# Run the data import script (cleans and loads HUD/Census data)
python scripts/import_data.py

# Run the Flask app
flask run
Current Plan
This project is being built across two sprints:
Sprint 1 (Weeks 1–7): Data foundation — clean and import HUD/Census data into PostgreSQL, build the core Flask API, implement the affordability calculation, and cover it with unit tests.
Sprint 2 (Weeks 8–14): Frontend, visualization, zip code comparison feature, error handling, polish, and deployment.
Full milestone breakdown and progress tracking is on the Canvas Individual Project page (replace with your actual Canvas link).
Links
Canvas Individual Project page: (add link here)
