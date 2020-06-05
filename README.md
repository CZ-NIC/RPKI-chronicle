# RPKI-Chronicle

Copyright (C) 2019-2020 CZ.NIC, z.s.p.o.

This is the RPKI-chronicle project -- web-based history keeper for
RPKI.

## Project aim and intended audience

There are many occasions when the Internet Service Providers, security experts or users need to know specifics about certain
IP prefixes and Autonomous Systems. The major examples include but are not limited to:

* an ISP that needs to verify that its own announcements comply with the current best practices with regard to RPKI,
* a security expert that needs to asses quality of processes in any partnering or colaborating organization, based on adherence to the current best practices,
* a security expert that investigates a specific incident and needs information about source of the attack at the specific time of its occurrence,
* a user that needs to verify rightful user of a specific IP prefixes,
* an IP address broker that needs to know BGP history of the prefixes to be transfered.

Apart from making the software and its running instance publicly available, there is a strong internal need to have
trusted source of RPKI history for CSIRT.CZ, which falls into the case of the security experts investigating specific incidents
and cybersecurity threats that need information about source of the attack at the specific time of its occurrence.

RPKI-chronicle makes it possible to investigate rapid and short-lived attacks even after they are finished and after their visible effects on Internet routing disapeared. This brings major advantage to the CSIRT.CZ and to the entire industry by helping to mitigate impact of long reaction time before the security threat is reported and can be investigated.

## Existing public tools

There are publicly available tools that we acknowledge, build upon when possible and encourage their usage in complementary tasks or for verification of our dataset:

* RIPE NCC RPKI Validator: https://github.com/RIPE-NCC/rpki-validator-3
* publicly available running instance of the former: https://rpki-validator.ripe.net/
* RIPE RIS: https://www.ripe.net/analyse/internet-measurements/routing-information-service-ris
* NIST RPKI monitor: https://rpki-monitor.antd.nist.gov/
* NIST Cybersecurity framework: https://www.nist.gov/cyberframework
* RPKI ROV deployment measurement: https://rov.rpki.net/
* Dragon Research Labs RPKI Toolkit: https://github.com/dragonresearch/rpki.net/#dragon-research-labs-rpki-toolkit

## Deployment

The project consists of two major submodules that have different requirements and deployment procedures.

Please follow steps in appropriate parts of README files of each submodule.

### General requirements/dependencies

* RIPE RPKI Validator 3
* Python 3

Python modules:
* tabulate
* flask
* wtforms
* psycopg2
* flask-paginate
* sqlalchemy
* Flask-SQLAlchemy
* flask_session
* redis
* flask-debugtoolbar
* envelope
* fasteners

### Deployment tips

* WSGI can be deployed and exposed by various methods, peferrably with NGINX 1.16.1
* DB engine is needed, preferrably PostgreSQL 12.1
* The local RIPE NCC RPKI Validator or remotely-accessed validator is needed. See
readme file for RIPE NCC RPKI Validator connector.

