
## Installing Django in a virtual enviroment
```python
python3 -m venv venv_project
source venv_project/bin/activate
pip install django
```

## Check view name from template
*request.resolver_match.url_name*

## How to reuse logging defined in a django project settings
```python
# Django enviroment
import os, sys
PROJECT_PATH = os.path.join(os.path.dirname(os.path.abspath(__name__)),'../../')
sys.path.append(PROJECT_PATH)
os.environ.setdefault('DJANGO_SETTINGS_MODULE','project.settings')
django.setup()

# Logging
import logging
log = logging.getLogger('logger_name') # Defined in settings
```
