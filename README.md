Role Name
=========

This Ansible role can be used for confuring sentry service with Postgresql as database and Redis for buffering.

Requirements
------------

This role works fine on ubuntu machines and for other RHEL machines, it may need some tweaking. 

Role Variables
--------------
sentry_enabled: yes                          # Enables this role.
sentry_user: sentry                          # System user for running Sentry.
sentry_home: /home/sentry                    # Home directory for the above mentioned user. 
sentry_setup_dir: /var/www/sentry            # Setup directory for Sentry.

# This role assumes you're using postgresql, redis on localhost for Sentry
sentry_dbname: sentry                        # Database name for sentry. 
sentry_dbuser: sentry                        # User to be created on that Database. 
sentry_dbuser_password: password             # Password for the above database user. 

sentry_admin: admin                          # User to login to the sentry GUI.
sentry_admin_email: admin@evernym.us         # Email for the above mentioned user.
sentry_admin_password: password              # Password for the above mentioned user. 

# Required packages(Will be installed via apt)
required_packages: [ 'python-dev', 'python-pip', 'libpq-dev', 'python-setuptools', 'make', 'python-virtualenv', 'libxml2-dev', 
                    'libxslt1-dev', 'libevent-dev', 'redis-server','postgresql', 'postgresql-contrib']

# Required packages(Will be installed via pip)                   
required_pip_packages: ['redis', 'hiredis', 'nydus', 'psycopg2']



A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

No dependencies, this role will install all the required packages. 

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - sentry

License
-------

MIT

Author Information
------------------
Role created by RaviTezu - http://ravitezu.me
Date: Feb 2 2015
