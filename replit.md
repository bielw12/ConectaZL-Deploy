# Conecta ZL - Portal de Notícias

## Project Overview
Community news portal developed in Django for São Paulo's East Zone (Zona Leste). Allows local journalists to publish content and enables community interaction through comments and likes.

## Recent Changes
- **2025-11-25**: Configured for Replit environment
  - Installed Python 3.11 and all dependencies
  - Configured workflow to run Django development server on port 5000
  - Set up environment variables (SECRET_KEY, DEBUG, ALLOWED_HOSTS)
  - Ran database migrations
  - Configured deployment with Gunicorn for production
  - Added .pythonlibs and .cache to .gitignore

## Project Architecture
- **Framework**: Django 5.2.8
- **Frontend**: HTML5, CSS3, JavaScript with TailwindCSS via CDN
- **Database**: SQLite (development), PostgreSQL support available
- **Key Features**:
  - User roles: Readers, Journalists, Administrators
  - Article creation with rich text editor (Summernote)
  - Geolocation with interactive maps (Folium)
  - Comment system with moderation
  - Tags and categorization (django-taggit)
  - REST API (Django REST Framework)

## Configuration
### Environment Variables (shared)
- `SECRET_KEY`: Django secret key for security
- `DEBUG`: Set to True for development
- `ALLOWED_HOSTS`: Comma-separated list of allowed hosts

### Workflow
- **Django Server**: Runs the development server
  - Command: `python3.11 manage.py runserver 0.0.0.0:5000`
  - Port: 5000 (webview)
  - Note: Must use python3.11 explicitly due to Replit environment

### Deployment
- **Type**: Autoscale
- **Server**: Gunicorn
- **Command**: `gunicorn --bind=0.0.0.0:5000 --reuse-port portal_noticias.wsgi:application`

## Apps Structure
- **users/**: User authentication and profiles with role-based permissions
- **articles/**: News articles with approval workflow, likes, and views tracking
- **comments/**: Comment system with moderation
- **api/**: REST API endpoints
- **portal_noticias/**: Main project configuration

## User Preferences
None specified yet.

## Important Notes
- The project uses Python 3.11 specifically - do not upgrade to Python 3.12 as it causes numpy compatibility issues
- Static files are served from `/static/` directory
- Media uploads go to `/media/` directory
- CSRF trusted origins include *.replit.dev and *.replit.app domains
- X-Frame-Options set to ALLOWALL for iframe support
