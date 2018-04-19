# airflow-postgres-redis-forex

This repository implements the airflow-postgres-redis-forex data pipeline as proposed by Mark Litwintschik in his [blog post](http://tech.marksblogg.com/airflow-postgres-redis-forex.html). 
The pipeline is composed from Docker containers.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine.

### Prerequisites

* OS: tested on Windows 10
* Docker 18.03.0-ce (Compose 1.20.1)

### Deployment

1. Create docker volume for postgresql: docker volume create --name airflow-postgresql -d local
2. Clone the git repository and fire up the containers: docker-compose up -d
3. Go to http://localhost:8080
4. Add connection under Admin -> Connections
	a. A connection type of Postgres
	b. A connection identifier of rates
	c. A host string of postgres (the postgresql service name, see docker-compose.yml)
	d. A schema string (database name) of airflow
	e. A login of username=airflow and password=airflow
5. Add connection under Admin -> Connections
	a. A connection type of HTTP
	b. A connection identifier of openexchangerates
	c. A host string of the full API endpoint: https://openexchangerates.org/api/latest.json?app_id=<your_app_id>


## Workflow

* File issues for features. They can be small or big, as long as they are solveable. You should be able to tell when something is done from reading the issue. Too open ended and it cannot be closed.

* Develop created issues

* Commits should touch one thing, preferably, with a label that matches the code. For example, a change that reads "reformat foo" shouldn't add new features, etc.

* Open a pull request (PR) for review from the branch to master

* Try to keep the commits on a PR branch below a dozen

* Keep the PR open for 24 hours to give people the chance to comment and look at it

* Review the changes

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/smomni/daqstore/tags). 

## Authors

* **Simo Tumelius** - *Data pipeline containerization* - [smomni](https://github.com/smomni)

See also the list of [contributors](https://github.com/smomni/daqstore/contributors) who participated in this project.

## License

This project is licensed under the GNU GPLv3 license - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* **Mark Litwintschik** - *Initial data pipeline architecture*

