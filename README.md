
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
import logging.handlers
log = logging.getLogger('logger_name') # Defined in settings
# Logfile name
TIMESTAMP = datetime.datetime.today().strftime('%Y%m%d')
LOG_TO_FILE = True
FILANEME_WITHOUT_EXTENSION = Path(__file__).with_suffix('').stem
LOG_FILENAME = os.path.join("logfiles",TIMESTAMP+"_"+FILANEME_WITHOUT_EXTENSION+".log")
print(LOG_FILENAME)

# Logging configuration
LOG_FORMAT = '{asctime} [{levelname:5s}] [{name}] {filename:s}:{lineno:d} {message:s}'
LOG_DATE_FORMAT = '%Y-%m-%d %H:%m'

if LOG_TO_FILE:
	logging.basicConfig(
		filename=LOG_FILENAME,
		format=LOG_FORMAT,
		style="{",
		datefmt=LOG_DATE_FORMAT,
		level=logging.DEBUG
	)
else:
	logging.basicConfig(
		format=LOG_FORMAT,
		style="{",
		datefmt=LOG_DATE_FORMAT,
		level=logging.DEBUG
	)

```
