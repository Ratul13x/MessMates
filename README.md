# MessMates

MessMates is a Flask-based mess management web application that helps users track meal requests, deposits, shared mess costs, and admin operations for a hostel or mess system.

## Features

- User registration and login
- Mess-based user grouping using a `mess_code`
- Meal selection for breakfast, lunch, and dinner
- User deposit tracking
- Profile page with monthly cost and due calculations
- Admin dashboard for managing bazaar entries and shared costs
- REST-style API endpoints for users, admins, and meal requests

## Tech Stack

- Python
- Flask
- Flask-SQLAlchemy
- SQLite
- HTML, CSS, Jinja templates

## Project Structure

```text
MessMates/
├── app.py              # Main Flask application and routes
├── models.py           # Database models
├── forms.py            # Form definitions (if used)
├── config.py           # App configuration
├── requirements.txt    # Python dependencies
├── instance/           # SQLite instance data
├── static/             # Static assets (CSS/JS/images)
├── templates/          # HTML templates for pages
├── __pycache__/        # Python cache files
└── messmates.db        # SQLite database created at runtime
```

## App Pages

- `/login` — Login page
- `/register` — New user registration
- `/home` — Meal submission and deposit page
- `/profile` — User financial summary and meal stats
- `/admin` — Admin panel for mess operations
- `/logout` — Log out the current user

## Database Models

### UserModel
- `id`
- `username`
- `email`
- `password`
- `mess_code`
- `is_admin`
- `deposit`
- `balance`

### MealRequest
- `id`
- `user_id`
- `date`
- `breakfast`
- `lunch`
- `dinner`

### BazaarEntry
- `id`
- `date`
- `total_bazaar`
- `shared_cost`
- `remarks`
- `mess_code`

## Setup Instructions

1. Clone the repository:

```bash
git clone https://github.com/Ratul13x/MessMates.git
cd MessMates
```

2. Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate   # On Linux/macOS
venv\Scripts\activate      # On Windows
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Run the application:

```bash
python app.py
```

The app will start in debug mode and be available at:

```text
http://127.0.0.1:5000/
```

## Notes

- The app uses SQLite by default.
- The project is designed for a hostel or mess management workflow where a group of users share costs based on a common `mess_code`.
- Admin users can record bazaar expenses and automatically distribute shared costs among members of the same mess.

## License

This project does not currently include a license file. If you intend to share or distribute it publicly, consider adding an appropriate open-source license.

## Contributing

Pull requests and improvements are welcome. If you plan to extend the project, consider adding:

- better validation and error handling
- stronger security for admin routes
- database migration support for production use
- frontend enhancements for a more polished UI

## Author

Ratul13x
