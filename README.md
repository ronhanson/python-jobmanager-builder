Job Manager Builder
===================

About
-----

Docker Image Builder is a helper tool to allow you to easily build Job Manager Client Docker images, and pack your own jobs/code into it.

Project url : https://github.com/ronhanson/python-jobmanager-builder

<table>
    <tr>
        <td>
            <img src="doc/screencaptures/jobmanager-builder-index.png" alt="Index page" width="300" />
        </td>
        <td>
            <img src="doc/screencaptures/jobmanager-builder-file.png" alt="File Upload page" width="300" />
        </td>
    </tr>
    <tr>
        <td>
            <img src="doc/screencaptures/jobmanager-builder-code.png" alt="Code page" width="300" />
        </td>
        <td>
            <img src="doc/screencaptures/jobmanager-builder-list.png" alt="List Image page" width="300" />
        </td>
    </tr>
</table>

Usage
-----

Use jobmanager-builder script :

    > bin/jobmanager-builder -h

Command lines parameters are as follow :    

    usage: jobmanager-builder -s SERVER [-p PORT] [-d DATABASE] [-b HTTP_BIND]
                              [-o HTTP_PORT] [-a APP_NAME] [--debug]
                              [-r REGISTRY URL] [-ru REGISTRY USERNAME]
                              [-rp REGISTRY PASSWORD] [-i BASE IMAGE]
                              [-l LOG_FILE] [-q]
                              [-v {DEBUG,INFO,WARNING,ERROR,CRITICAL}]
                              [-c CONFIG_FILE]
                              [--create-config-file CONFIG_OUTPUT_PATH] [-h]
                              [--version]
    
    Job Manager Docker Image Builder API Args that start with '--' (eg. -s) can
    also be set in a config file (/etc/jobmanager/builder.yaml or ./builder.yaml
    or specified via -c). The config file uses YAML syntax and must represent a
    YAML 'mapping' (for details, see http://learn.getgrav.org/advanced/yaml). If
    an arg is specified in more than one place, then commandline values override
    environment variables which override config file values which override
    defaults.
    
    Job Database:
      -s SERVER, --server SERVER
                            Address of the MongoDB database server containing
                            jobs. [env var: JOBMANAGER_DATABASE_HOST] (default:
                            None)
      -p PORT, --port PORT  Port to connect the MongoDB database. [env var:
                            JOBMANAGER_DATABASE_PORT] (default: 27017)
      -d DATABASE, --database DATABASE
                            Database name containing jobs. [env var:
                            JOBMANAGER_DATABASE_NAME] (default: jobmanager)
    
    HTTP Server options:
      -b HTTP_BIND, --http-bind HTTP_BIND
                            Server IP address bindings. [env var:
                            JOBMANAGER_BUILDER_HTTP_BIND] (default: 0.0.0.0)
      -o HTTP_PORT, --http-port HTTP_PORT
                            Port to bind. [env var: JOBMANAGER_BUILDER_HTTP_PORT]
                            (default: 5001)
      -a APP_NAME, --app-name APP_NAME
                            Application name (displayed on web interface). [env
                            var: JOBMANAGER_BUILDER_APP_NAME] (default: None)
      --debug               Activate HTTP debug output. [env var:
                            JOBMANAGER_BUILDER_DEBUG] (default: False)
    
    Docker registry options:
      -r REGISTRY URL, --registry-url REGISTRY URL
                            Docker registry url. Registry where to push newly
                            built images. [env var:
                            JOBMANAGER_DOCKER_REGISTRY_URL] (default: None)
      -ru REGISTRY USERNAME, --registry-username REGISTRY USERNAME
                            Docker registry username for login in. If not set, it
                            will bypass login. [env var:
                            JOBMANAGER_DOCKER_REGISTRY_USERNAME] (default: None)
      -rp REGISTRY PASSWORD, --registry-password REGISTRY PASSWORD
                            Docker registry password for login in. [env var:
                            JOBMANAGER_DOCKER_REGISTRY_PASSWORD] (default: None)
      -i BASE IMAGE, --base-image BASE IMAGE
                            Base Docker image of Job Manager Client to build upon.
                            (default: ronhanson/jobmanager-client:latest) [env
                            var: JOBMANAGER_CLIENT_DOCKER_BASE_IMAGE] (default:
                            None)
    
    Log output:
      -l LOG_FILE, --log-file LOG_FILE
                            Optionally log to file. [env var:
                            JOBMANAGER_BUILDER_LOG_FILE] (default: None)
      -q, --quiet           Do not output on screen. [env var:
                            JOBMANAGER_BUILDER_QUIET] (default: False)
      -v {DEBUG,INFO,WARNING,ERROR,CRITICAL}, --verbosity {DEBUG,INFO,WARNING,ERROR,CRITICAL}
                            Log verbosity to screen. [env var:
                            JOBMANAGER_BUILDER_VERBOSITY] (default: INFO)
    
    Config file:
      -c CONFIG_FILE, --config-file CONFIG_FILE
                            config file path (default: None)
      --create-config-file CONFIG_OUTPUT_PATH
                            takes the current command line args and writes them
                            out to a config file at the given path, then exits
                            (default: None)
    
    Miscellaneous commands:
      -h, --help            show this help message and exit.
      --version             show program's version number and exit [env var:
                            JOBMANAGER_BUILDER_VERSION]
    
    "According to this program calculations, there is no such things as too much
    wine."

Example : 

    > bin/jobmanager-builder -s localhost

Then open your browser on *http://0.0.0.0:5001/* 


Compatibility
-------------

This project can be used on Linux or macOS systems.

This libraries are compatibles with Python 2.7+ and Python 3.X.

Mainly tested on 2.7 and 3.6.


Author & Licence
----------------

Copyright (c) 2018 Ronan Delacroix

This program is released under MIT Licence. Feel free to use it or part of it anywhere you want.
 
