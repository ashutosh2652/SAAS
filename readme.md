# SaaS Django Project

This is a Django-based SaaS starter project with user authentication, subscription management, Stripe integration, and a modern Tailwind CSS-powered frontend. It is organized for modular development and easy deployment.

## Features

- **User Authentication**: Registration, login, social login (GitHub via `django-allauth`).
- **Subscription Management**: Plans, pricing, Stripe integration, user subscriptions.
- **Admin Dashboard**: Manage users, subscriptions, and payments.
- **Checkout System**: Stripe-based checkout flow.
- **Profile Management**: User profiles and settings.
- **Landing Page**: Customizable marketing landing page.
- **Vendor Static Files**: Automated download and management of third-party static assets.
- **Tailwind CSS**: Modern CSS framework for rapid UI development.
- **Scheduled Tasks**: Management commands for syncing Stripe subscriptions and clearing dangling subscriptions.
- **Helpers**: Utility modules for billing, dates, numbers, and file downloads.

## Project Structure

- `src/`
  - `auth/` – User authentication and social login.
  - `cfehome/` – Main Django project settings, URLs, and views.
  - `checkouts/` – Stripe checkout and payment logic.
  - `commando/` – Custom management commands (e.g., vendor static file pull).
  - `customers/` – Customer models and logic.
  - `dashboard/` – Admin dashboard views and models.
  - `helpers/` – Utility functions for billing, dates, downloads, etc.
  - `landing/` – Landing page models and views.
  - `profiles/` – User profile management.
  - `staticfiles/` – Static assets (Tailwind CSS, images, themes).
  - `subscriptions/` – Subscription plans, pricing, Stripe integration.
  - `templates/` – HTML templates for all pages.
  - `visits/` – Tracking user visits and analytics.

## Setup

1. **Clone the repository**

   ```sh
   git clone <your-repo-url>
   cd SAAS-MAIN
   ```

2. **Install Python dependencies**

   ```sh
   python -m pip install --upgrade pip
   python -m pip install -r requirements.txt
   ```

3. **Install Node.js dependencies (for Tailwind CSS)**

   ```sh
   npm install
   ```

4. **Build Tailwind CSS**

   ```sh
   npm run build
   ```

5. **Apply Django migrations**

   ```sh
   cd src
   python manage.py migrate
   ```

6. **Collect static files**

   ```sh
   python manage.py vendor_pull
   python manage.py collectstatic --noinput
   ```

7. **Run the development server**
   ```sh
   python manage.py runserver
   ```

## Usage

- Access the site at `http://localhost:8000/`
- Admin panel at `/admin/`
- Register and log in as a user
- Subscribe to plans and manage your profile

## Development

- **Tailwind CSS**: Edit `src/staticfiles/base_tailwind/tailwind-input.css` and rebuild with `npm run build`.
- **Custom Commands**: Use management commands like `vendor_pull` and `sync_user_subs` for maintenance.
- **Tests**: Run tests with:
  ```sh
  python manage.py test
  ```

## Environment Variables

Copy `.env.sample` to `.env` and fill in required secrets (e.g., Django secret key, Stripe keys).

## License

See [LICENSE](LICENSE) for details.

---

**Folders and files referenced:**

- [src/manage.py](src/manage.py)
- [src/cfehome/settings.py](src/cfehome/settings.py)
- [src/auth/](src/auth/)
- [src/checkouts/](src/checkouts/)
- [src/commando/management/commands/vendor_pull.py](src/commando/management/commands/vendor_pull.py)
- [src/customers/](src/customers/)
- [src/dashboard/](src/dashboard/)
- [src/helpers/](src/helpers/)
- [src/landing/](src/landing/)
- [src/profiles/](src/profiles/)
- [src/staticfiles/](src/staticfiles/)
- [src/subscriptions/](src/subscriptions/)
- [src/templates/](src/templates/)
- [src/visits/](src/visits/)
- [requirements.txt](requirements.txt)
- [package.json](package.json)
- [.env.sample](.env.sample
