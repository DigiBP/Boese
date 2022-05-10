# Boese

The focus of this project is to digitalize parts of the admission process of the Kalaidos FH, the business logic either from the Law School or Business School.

- David Mäder
- Patrick Consonni
- Ramona Boeh
- Zoe Mitter

# Use Case

The project group decides in agreement with the Kalaidos Project Leader and Enterprise Architect, which process part to digitalize according to the existing business logic of KFH and the requirements of FHNW for the project group. The admission process for all departments of KFH will be modelled in a generic way.

The modelling is done on the basis of the following documents:

- Admission rules of KFH
- Previously modelled admission process for the Kalaidos Law School
- Admission Process Model in EPC of KFH

The admission process is digitalized as a prototype since the timelines between the deadline of the university project and the Kalaidos project are not aligned. Thus, the university project provides value to KFH by providing the admission process modelled in BPMN 2.0 and a digitalization mock-up ready to be scripted accordingly in the school administration software by the external provider. The project group have implemented the workflow in the software provided by FHNW.

# As Is Process

## Kalaidos FH

The Kalaidos FH (KFH) is the only accredited university of applied sciences which is not financially supported by the government. Its story goes back to 1997 where it was founded out of the AKAD Akademikergesellschaft für Erwachsenenbildung university. Its unique selling point was to enable working people to obtain higher education or the general qualification for university entrance by providing permeability inside the education system and between it and the working world (AKAD, 2021). Beside other educational institutes KFH is part of the Kalaidos educational group.
Problem model

Working with 40 year old outdated legacy systems, study program coordinators face a heavy workload due to the growth of the university in the recent years and the slowness of the software processing the data. Therefore, KFH decided to implement a new school administration system. The project group Team Boese's focus is on the student admission process. Based on the process, modelled in EPC-notation (Event-Driven-Process-Chain) by the KFH process management, we modelled the process in BPMN.

<img width="1398" alt="Screenshot 2022-05-03 at 10 43 25" src="https://user-images.githubusercontent.com/101626421/166426121-978a758e-a34c-4204-a25d-13c140b4a9a6.png">

The as-is process contains loops due to students which forget to submit all their documents. Furthermore, there are multiple manual tasks like consulting the applicant and checking a sur dossier application. Several parties are involved in handling this process.

# DigiBP Camunda Template

[![License](http://img.shields.io/:license-apache-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![Deploy to Heroku](https://img.shields.io/badge/deploy%20to-Heroku-6762a6.svg?longCache=true)](https://heroku.com/deploy)

## Releases

### [7.16.0](https://github.com/DigiBP/digibp-camunda-template/tree/7.16.0)
- Updating Camunda to 7.16.0
- Updating Camunda Spring Boot Starter to 7.16.0
- Updating Spring Boot to 2.5.4

### [7.14.0](https://github.com/DigiBP/digibp-camunda-template/tree/7.14.0)
- Updating Camunda to 7.14.0
- Updating Camunda Spring Boot Starter to 7.14.0
- Updating Spring Boot to 2.3.1.RELEASE

### [7.13.0](https://github.com/DigiBP/digibp-camunda-template/tree/7.13.0)
- Updating Camunda to 7.13.0
- Updating Camunda Spring Boot Starter to 7.13.0
- Updating Spring Boot to 2.2.5.RELEASE

### [3.4.0](https://github.com/DigiBP/digibp-camunda-template/tree/3.4.0)
- Updating Camunda to 7.12.0
- Updating Camunda Spring Boot to 3.4.0
- Updating Spring Boot to 2.2.1.RELEASE

### [3.3.0](https://github.com/DigiBP/digibp-camunda-template/tree/3.3.0)
- Updating Camunda to 7.11.0
- Updating Camunda Spring Boot to 3.3.4
- Updating Spring Boot to 2.1.6.RELEASE
- Removing Maven Wrapper
- Removing Camunda Modeler Templates

### 3.2.3
- Adding `spring-boot-starter-jdbc` dependency, otherwise `spring:datasource` is ignored.

### 3.2.2
- Use of Camunda deployment procedure (embedded:deployment) instead of Spring Boot (embedded:app)
- Change of resource folder structure due to the use deployment procedure  

### 3.2.1
- Rearrange the order of the REST and Web Apps dependencies

### 3.2.0
- Updating Camunda Spring Boot to 3.2.0
- Updating Spring Boot to 2.1.1.RELEASE

### 3.1.0
- Updating Camunda to 7.10.0
- Updating Camunda Spring Boot to 3.1.0

### 3.0.0
- Updating Camunda to 7.9.0
- Updating Camunda Spring Boot to 3.0.0
- Updating Spring Boot to 2.0.2.RELEASE

### 2.0.7
- Default Maven goal `clean spring-boot:run`
- Camunda Modeler Element Template (not in archetype)

### 2.0.6
- A much nicer `deploy to Heroku` shield.

### 2.0.5
- Adding 'authorization: enabled: false' to application.yaml

### 2.0.4
- Adding application-local.yaml to .gitignore
- Updating application.yaml and application-heroku.yaml

### 2.0.3
- Adding a README.md file

### 2.0.2
- Adding a .gitignore file

### 2.0.1
- Adding a .gitignore template file

### 2.0.0
- Updating Camunda Spring Boot to 2.3.0
- Updating Spring Boot to 1.5.8.RELEASE

### 1.0.6

- Updating Camunda Spring Boot to 2.1.0
- Updating Spring Boot to 1.5.3.RELEASE
- Adding to application.yaml: `camunda:bpm:authorization:enabled:true`

### 1.0.5

- Updating Camunda Enterprise Edition to 7.6.4
- Uncommenting Camunda REST API
- Adding (uncommented) Spring Boot Data
- Adding (uncommented) Hibernate configuration to application.yaml

### 1.0.4

- Adding Camunda Enterprise Edition

### 1.0.3

- Fixing the Maven issue

### 1.0.2

- Fixing the Eclipse issue

### 1.0.1

- Fixing the basic package

### 1.0.0

- Initial version

## Maintainer
- [Andreas Martin](https://github.com/andreasmartin)

## License
- [Apache License, Version 2.0](https://github.com/DigiBP/digibp-archetype-camunda-boot/blob/master/LICENSE)
