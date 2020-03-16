# SQIP - About/Vision 
(Pronounced as 'skip')

SQIP is a Python application aimed at generalizing/standardizing the CRUD operations of Auditable data for custom built Government applications.  The developer interface will be a REST API and the way the data is stored is configured through IaC.  The goal is to make it easy for a business to identify the different auditable data domains, have those configured during deployment of sqip and the developers easily review documentation and start making api calls day one.  

![SQIP Architecture Diagram](SQIP-Architecture.svg)

#### Python Environment
The development workflow uses [pipenv](https://github.com/pypa/pipenv) to manage the virtual environments.  

#### File Structure
```
|--.github - github actions
├── app - sqip application
│   └── providers - integration providers
└── infrastructure - all environment deployments
    ├── helm 
    │   └── SQIP
    │       ├── charts
    │       └── templates
    │           └── tests
    └── terraform
```

The `app` directory contains a Flask application, run the application:

```
$ pipenv install # init env from fresh repo clone
$ pipenv shell
$ export FLASK_APP=app
$ export FLASK_ENV=development
$ flask run
 * Serving Flask app "app" (lazy loading)
 * Environment: development
 * Debug mode: on
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 326-874-135
```

Check the `version` API:

```
$ curl http://127.0.0.1:5000/version
SQIP v-0.0.1
```
 
## Use Case Diagram

![SQIP-Model-SQP-Use-Case-Diagram](SQIP-Model-SQP-Use-Case-Diagram.svg)



## Package Diagram

![SQIP Package Diagram](SQIP-Model-SQIP-Package-Diagram.svg)



## Class Diagram

![SQIP-Model-SQIP-Class-Diagram](SQIP-Model-SQIP-Class-Diagram.svg)

# Future

In the future we would love to have a provider system that allows for different queue mechanisms and backend database's or services.  