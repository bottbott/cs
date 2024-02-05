---
lang: en
title: Virtual Environments
viewport: width=device-width, initial-scale=1.0
---
- `python3 -m venv name_of_venv` Creates the virtual environment. 

- `source my_project/venv/bin/activate` - Set up the virtual environment if it already exists

- `pip freeze > requirements.txt` Output a version list that can be used to set up an environment

- `pip install -r requirements.txt file` Set up a new environment based on the requirements file.

- `deactivate` Turns off the venv.

- `python3 -m venv venv  --system-site-packages` Includes system packages in main environment in your new virtual environment.

- `pip list --local` - Shows just the packages that were installed. Not what was brought over

Don't put your project files into the venv. 

Don't commit your venv files.


