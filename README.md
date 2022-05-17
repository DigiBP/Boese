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

## Problem model

Working with 40 year old outdated legacy systems, study program coordinators face a heavy workload due to the growth of the university in the recent years and the slowness of the software processing the data. Therefore, KFH decided to implement a new school administration system. The project group Team Boese's focus is on the student admission process. Based on the process, modelled in EPC-notation (Event-Driven-Process-Chain) by the KFH process management, we modelled the process in BPMN.

<img width="1398" alt="Screenshot 2022-05-03 at 10 43 25" src="https://user-images.githubusercontent.com/101626421/166426121-978a758e-a34c-4204-a25d-13c140b4a9a6.png">

## Process Description

An applicant fills out a form on the Kalaidos Website to apply for a study program. On pressing the send button, the application goes directly to M-Files, a document management system. Study program coordinators check the admission manually according to their respective admission criteria. Sometimes applicants forget to upload some necessary documents or based on the received information, study program coordinators need additional documents to continue the admission process. Thus, they contact the applicant and request the necessary information. This might happen before or after checking the study program specific admission criteria which is a task assigned to the dean. Based on this, the dean decides whether it's a Sur Dossier applicant. If yes, he engages in consulting the applicant and specifies required criteria for acquiring the admission. He argues in writing why the applicant should be accepted to the study program and hands the document over to the admission committee which decides on approval and on further requirements to fulfill or not. Either way, the admission committee informs the study program coordinator who informs the applicant about the decision. If it's no Sur Dossier applicant the dean still has to review the application to give the definitive admission. Still, he can assign requirements to an applicant if he thinks it's necessary. The study program coordinator informs the applicant about rejection or approval of the application and potential additional requirements to fulfill. 

The as-is process contains loops due to students which forget to submit all their documents. Furthermore, there are multiple manual tasks like consulting the applicant and checking a sur dossier application. Several parties are involved in handling this process.

# To Be Process

## School administration software

The new school administration software is currently customized by the supplier for KFH. They implement assistents which guide study program coordinators through certain processes. Since it's a challenge to standardize the student admission process for all departements of the KFH, its implementation hasn't been yet addressed. But the supplier's intention is to build a workflow in the software to support this process. Because they only work on this in autumn 2022, we couldn't work in the real software supporting them. In agreement with the supplier and KFH project leader, we decided to build a mock-up workflow which contains the business logic.

## BPMN 2.0 student admission process

As opposed to the as-is process we modelled the to-be process without any real-world loops and inquiries, just the activities which are relevant for the student admission and especially tasks which have potential for automation. Since dispensation and sur dossier admission are important parts of the admission process for KFH, we modelled the process twice. Both parts are manual and thus not automatable. Still, we included them in one of our processes to show we considered them as well.

![Zulassungsprozess_mit Dispensation_v0 3](https://user-images.githubusercontent.com/101626421/166431596-073473e0-69f1-43c0-8fbf-1c7cb78560a6.png)

We explicitly take the student admission process without dispensation, since it has no potential for digitalization.

![Zulassungsprozess_ohne Dispensation_v0 2](https://user-images.githubusercontent.com/101626421/166432004-4bdbd97d-067c-4012-808e-62994230b589.png)

## Deliverables and benefits

KFH will get the entire standardized high-level admission process that will be valid for all departments. In addition, the admission business logic for either the Law School or Business School will be defined. A prototype of the digitalized process will be created in Camunda to support KFH in the implementation of a digital workflow in the school administration software.

# Application Submission

## Application Form

![image](https://user-images.githubusercontent.com/28218908/166430517-f6b58b07-c180-45ae-a0f1-91a27411e781.png)
![image](https://user-images.githubusercontent.com/28218908/166430702-00448660-2378-4ea0-980a-5d931cd38664.png)

## Application Form Responses
![image](https://user-images.githubusercontent.com/28218908/166429287-439eaccd-6a9b-4581-8dbf-7325f6241b0f.png)


# Evaluation Phase
Three decision tables were applied to implement the business logic. Through this automation, the study program coordinators in KFH are supported in the student admission process.

- add screenshot Decision Diagram

- add screenshot Decision Table 

# Conclusion

## Conclusion
* Case of Applied Psychology: 25min performance test and 35min questionnaire must be filled out AFTER the first admission criteria are fulfilled. Therefore, we cannot implement a DMN, because we do not get this data simultaneously with the google forms application. This would make the process different for the AP study program than for other study programs

* With all the data received in the google forms application, we have all information we need for the two-step admission. Therefore, we might not need 3 DMNs and the process might be leaner.

## Lesson Learned
While doing this project, we realized that a standardized process is only possible, when there are not many exceptions. For the case of KFH, however, it is not possible, as different requirements should be met for different study programs.

# Artefacts, Applications & Accesses

## Artefacts
Link to Video

Link to [Presentation Slides](https://fhnw365.sharepoint.com/:p:/r/teams/SS22_MSc_BIS_DigiBP_M365-TeamBse/Freigegebene%20Dokumente/Team%20B%C3%B6se/Team%20Boese_KFH_DigiBP%20Presentation.pptx?d=w790887638fe849cd807d1cdf5493e419&csf=1&web=1&e=Y86XaF)

Link to [Github Repository](https://github.com/DigiBP/Boese)

Link to [Application Form](https://docs.google.com/forms/d/1Pu0OEYmcLoRq8y_Kv-V_W75egXivgVsw934t60xnTWw/prefill)

Link to [Application Form Responses](https://docs.google.com/spreadsheets/d/1ay9QjBoXIt0xETxmyPe8PUPAkzq_FAgbj9-pnePwSQ4/edit?resourcekey#gid=674478772)

Link to [Study Program KFH Bachelor Applied Psychology](https://www.kalaidos-fh.ch/de-CH/Studiengaenge/BSc-Bachelor-Angewandte-Psychologie)

Link to Admisssion/Exam Regulations (Blocker)

## Camunda Engine
Link to [Camunda Engine](https://digibp.herokuapp.com/camunda/app/tasklist/default/#/login)

### Camunda user

## Make (Integromat)
Link to [Make](https://www.make.com/en/login)

### Make overview


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
