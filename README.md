# Boese

The focus of this project is to digitalize parts of the admission process of the Kalaidos FH, the business logic either from the Law School or Business School.

- David Mäder
- Patrick Consonni
- Ramona Boeh
- Zoe Mitter

# Use Case
## Perspective of study program coordinators
The Kalaidos FH is growing at an uncontrollable speed. Workload for study program coordinators is heavy. The admission process is work intensive due to the individual consultation for potential students since Kalaidos FH offers a variety of tailored study program solutions. Currently, study program coordinators must transfer data from the application, coming in via a form over the website, manually into their system which is time-consuming and repetitive. The current application form allows students to send it without uploading the necessary documents as certificates of employment or qualification for university entrance. Thus, study program coordinators have incomplete applications pending while asking the applicants for those documents, sometimes waiting for them up to six months. 
A reduction of this administrative task would leave more time for consulting which is a USP of Kalaidos FH.

## Perspective project "Symphony"
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

An applicant fills out a form on the Kalaidos Website to apply for a study program. On pressing the send button, the application goes directly to M-Files, a document management system. Study program coordinators check the application manually according to their respective admission criteria. Sometimes applicants forget to upload some necessary documents or based on the received information, study program coordinators need additional documents to continue the admission process. Thus, they contact the applicant and request the necessary information. This might happen before or after checking the study program specific admission criteria which is a task assigned to the dean. Based on this, the dean decides whether it's a Sur Dossier applicant. If yes, he engages in consulting the applicant and specifies required criteria for acquiring admission approval. He argues in writing why the applicant should be accepted to the study program and hands the document over to the admission committee which decides on approval and on further requirements to fulfill or not. Either way, the admission committee informs the study program coordinator who informs the applicant about the decision. If it's no Sur Dossier applicant the dean still has to review the application to give the definitive admission. Still, he can assign requirements to an applicant if he thinks it's necessary. The study program coordinator informs the applicant about rejection or approval of the application and potential additional requirements to fulfill. 

The as-is process contains loops due to students which forget to submit all their documents. Furthermore, there are multiple manual tasks like consulting the applicant and checking a sur dossier application. Several parties are involved in handling this process.

# To Be Process

## School administration software

The new school administration software is currently customized by the supplier for KFH. They implement assistents which guide study program coordinators through certain processes. Since it's a challenge to standardize the student admission process for all departements of the KFH, its implementation hasn't been yet addressed. But the supplier's intention is to build a workflow in the software to support this process. Because they only work on this in autumn 2022, we couldn't work in the real software supporting them. In agreement with the supplier and KFH project leader, we decided to build a mock-up workflow which contains the business logic.

## BPMN 2.0 student admission process

As opposed to the as-is process we modelled the to-be process without any real-world loops and inquiries, just the activities which are relevant for the student admission and especially tasks which have potential for automation. Since dispensation and sur dossier admission are important parts of the admission process for KFH, we modelled the process twice. Both parts are manual and thus not automatable. Still, we included them in one of our processes to show we considered them as well.

![Zulassungsprozess_mit Dispensation_v0 3](https://user-images.githubusercontent.com/101626421/166431596-073473e0-69f1-43c0-8fbf-1c7cb78560a6.png)

We explicitly take the student admission process without dispensation, since it has no potential for digitalization. In chapter "Innovation - Chat function" it's showed how a chat on the website could be used to handle a dispensation in a fast and efficient way.

![Zulassungsprozess_ohne Dispensation_v0 2](https://user-images.githubusercontent.com/101626421/166432004-4bdbd97d-067c-4012-808e-62994230b589.png)

## Deliverables and benefits

KFH will get the entire standardized high-level admission process that will be valid for all departments. In addition, the admission business logic for either the Law School or Business School will be defined. A prototype of the digitalized process will be created in Camunda to support KFH in the implementation of a digital workflow in the school administration software.

# Application Submission

## Application Form

Currently, the study program coordinator must transfer the personal data from the application into their system. Now when submitting the form, it is written directly to the database.

![Personal Data](https://user-images.githubusercontent.com/101626421/172023279-a05c992f-f5ab-4af7-bf13-5aa42492b46b.png)

Assessing the language level is crucial for studying. Today, students can submit the application via the Kalaidos website without uploading any documents. But this form doesn't allow to proceed with the application process without proving with a document a potential student's eligibility. The potential student is explicitly advised to submit his/her documents completely. Otherwise the application cannot be processed.

![Language Level](https://user-images.githubusercontent.com/101626421/172023328-dc619f1a-624c-46a0-8308-c0cc1f2f956f.png)

In Switzerland, there are many qualifications one can obtain. For statistic purposes, study program coordinators must type in the respective qualification for university into the current system. With this form, it's directly written to the database.

![Qualification for university](https://user-images.githubusercontent.com/101626421/172023405-35ec97b3-2748-4c31-b946-28184fc554a8.png)

Right now, the form on the Kalaidos FH website prompts the potential student to upload all documents in the end after filling out everything else. This form is process based and asks for the respective document to be uploaded while prompting the potential student to fill out questions. For example, when the user must check the checkbox to his/her language level C2, C1, B2, B1, A2 or A1, he/she is also prompted to upload his/her language diploma.

## Application Form Responses
![image](https://user-images.githubusercontent.com/28218908/166429287-439eaccd-6a9b-4581-8dbf-7325f6241b0f.png)

# Evaluation Phase 
## Application Form Responses / Database storage
Based on the information included in the application form the workflow is triggered (see explanation below). In addition, all the data is stored in the database as illustrated in the excel table which stands representative for the database. Through this automation, the study program coordinators in KFH are supported in the student admission process.

## Workflow
Below is the first level admission approval workflow illustrated. Based on the study application form the workflow triggers the manual “SurDossier” procedure for not fulfilled general qualification criteria and the manual assessment check for fulfilled qualification criteria. In the next chapters, a detailed explanation regarding DMN and Assessment is provided.
![image](https://user-images.githubusercontent.com/28218908/172043098-a9bc2934-123f-4891-a5fb-5194e508a49f.png)

## DMN
The DMN’s are the central element of the admission approval workflow part. Basically, all the defined requirements in the policies and guidelines from Kaladios are incorporated in the DMNs as a rule-set and decisions according to that are automatically possible. This enables a more efficient and simplified process without manual involvement for each requirement.

### DMN_1 Programmtyp Prüfen
Based on the required basic information and pre-defined DMN rule-set the workflow automatically triggers the correct procedure. For example, if the level of german is below C2, processing further in the application procedure won’t be possible. If the required level is met the next DMN rule-set (DMN_2) will be triggered based on the study programme selection.
![image](https://user-images.githubusercontent.com/28218908/172042932-baa47e2b-67c3-4d5a-9e12-4dceb484a08a.png)

### DMN_2 Regelzulassung Bachelor prüfen
According to de selection of the study program in the DMN_1, the respective DMN_2 will be triggered for the first pre-assessment of the general qualification criteria. This example showcases the pre-assessment for the Bachelor “Applied Psychology”. Based on the selected answers by the application the DMN_2 evaluates if general qualifications are sufficient or if the SurDossiert process is required. If all the requirements are met the process via “Studengnagskomission” will be initiated an additional assessment will be performed and for traceability reson documented in specif assessment tables within CampusNut, as explained in the next chapter.
![image](https://user-images.githubusercontent.com/28218908/172042978-9e6d2014-5a45-47a7-987b-78720eff1dbe.png)

## Assessment documentation of first level admission approval procedure in CampusNet
Based on the information and uploaded documents in the registration form, a first pre-assessment is automatically performed via DMN as explained in the previous chapter. In case the general qualification criteria are not fulfilled, the manual procedure so-called “Sur Dossier” will be triggered within the department “Zulassungskommision”. However manual assessment of general qualification criteria is also required after the successful fulfilment of the pre-assessment. This is performed within the department “Studienganskomission” and comprises, for example, authenticity checks of the uploaded documents. This assessment is directly documented within the software CampusNet as part of the first level admission approval steps. The table below illustrates a possible solution for such an assessment table as part of the first level admission approval procedure. The advantage is that, not only reasonable documentation for the next steps are in place, but also storage of all the decisions and additional information during the administration process on the database is ensured. Please note that the table below is just a possible solution for incorporating assessment documentation in CampusNet.
![image](https://user-images.githubusercontent.com/28218908/172043070-a36aa4a1-e9c8-4fbf-83a2-1f912a315457.png)

# Innovation – Chat Function
JivoChat is an all-in-one business messenger that teams use to talk to customers. Embedding JivoChat in the website via code snippet is easily done.

<img width="600" alt="KFH_website_JivoChat" src="https://user-images.githubusercontent.com/101626421/170881030-9d3fa580-9773-43a2-ad76-03eac72cd7ba.png">

Being available for potential students during office hours in order to answer their questions immediately contributes a lot to customer satisfaction. It's also possible to exchange files via chat.

<img width="600" alt="JivoChat_conversation" src="https://user-images.githubusercontent.com/101626421/170881999-2485b3fb-e165-4646-b9a5-723abe73bb07.png">

In the contact center where the conversation takes place it's also possible to create a deal. It's marked on the screenshot with a red box: this deal can be assigned to a teammember; in this case it's assigned to Ramona Boeh. The study program coordinator can add a description of the deal, set the value of the deal and add a task with a reminder. This deal is then automatically visible in the JivoChat CRM which is structured as a Kanban board.

<img width="600" alt="JivoChat_CRM" src="https://user-images.githubusercontent.com/101626421/170882420-b8ad74cf-406f-447c-a05b-f63188d2de04.png">
As soon as the customer's needs are fulfilled, the study program coordinator can set the chat on "resolved". We can enable a webhook in JivoChat for connecting it via API to a google spreadsheet which serves as a database where all the conversations are stored. Thus, JivoChat with implemented CRM and database storage can serve as a replacement of the CRM light in DidacNew with which Kalaidos FH currently works.
The customer can rate the conversation in the chat.

![Chat_rating](https://user-images.githubusercontent.com/101626421/170883034-76fd639b-0ba7-4fdc-9d04-e85eb01c3f8c.png)

The ratings are shown on the statistics dashboard. There are also other activities visible like chats activity, proactive chat invitations, agents online time, pipelines, incoming and outgoing calls, callbacks and an aggregated report which can be downloaded either as an excel or csv file.

<img width="600" alt="JivoChat_statistics" src="https://user-images.githubusercontent.com/101626421/170883218-b789f100-5455-4000-882a-acafbb0d7694.png">

JivoChat allows agents to do phone or video calls as well and to monitor visits to the website where the chat is implemented.
Furthermore, the user can download the chat conversation for him/herself.

![Chatlog_user](https://user-images.githubusercontent.com/101626421/170883245-7e1006e4-fb87-4260-abe7-a75b286f39bd.png)

The video shows the usecase of a dispensation request.
                                                                                                                                                      
https://user-images.githubusercontent.com/101626421/172022024-9ef533ed-0c00-4025-88ed-6e1a23f2ee75.mov                                                                                                                      

Annotation: JivoChat is a 14 days free trial and ends on 12. June 2022.
                                                                                                                                                      
            Account data for access:
            Email: ramona.boeh@students.fhnw.ch
            Password: Quark278
                                                                                                                                   
# Conclusion

## Conclusion                                                                                                                                               
* A process can be made much leaner if the business logic is implemented in a DMN.

* Workflows are very handy for standardised processes. As soon as the business logic becomes too specific and therefore rare, it might be difficult to find the balance between the effort of implementing the workflow and the benefit. In some cases automation isn't an option due to regulations as e.g. with the university law which claims that documents have to be reviewed by a human being.
                                                                                                                                                      
* Assignment of specific tasks to each employee ensures responsibility and standardisation of the process.

* Information management is important! 
                                                                                                                                                      
* Case of Applied Psychology: 25min performance test and 35min questionnaire must be filled out AFTER the first admission criteria are fulfilled. Therefore, we cannot implement a decision table, because we do not get this data simultaneously with the google forms application. This would make the process different for the Applied Psychology study program than for other study programs

* With all the data received in the google forms application, we have all information we need for the two-step admission. Therefore, we might not need 3 decision tables and the process might be leaner.

## Lesson Learned
While doing this project, we realized that a standardized process is only possible, when there are not many exceptions. For the case of KFH, however, it is not possible, as different requirements should be met for different study programs.

Define a name convention master system from where to copy all variables into the other softwares!
                                                                                                                                                      
Plan enough time to debug since it is not easy to find the mistake while working with four softwares!
                                                                                                                                                      
Debug systematically and implement aids!

# Artefacts, Applications & Accesses

## Artefacts
Link to Video

Link to [Presentation Slides](https://fhnw365.sharepoint.com/:p:/r/teams/SS22_MSc_BIS_DigiBP_M365-TeamBse/Freigegebene%20Dokumente/Team%20B%C3%B6se/Team%20Boese_KFH_DigiBP%20Presentation.pptx?d=w790887638fe849cd807d1cdf5493e419&csf=1&web=1&e=Y86XaF)

Link to [Github Repository](https://github.com/DigiBP/Boese)

Link to [Application Form](https://docs.google.com/forms/d/1Pu0OEYmcLoRq8y_Kv-V_W75egXivgVsw934t60xnTWw/prefill)

Link to [Application Form Responses](https://docs.google.com/spreadsheets/d/1ay9QjBoXIt0xETxmyPe8PUPAkzq_FAgbj9-pnePwSQ4/edit?resourcekey#gid=674478772)

Link to [Study Program KFH Bachelor Applied Psychology](https://www.kalaidos-fh.ch/de-CH/Studiengaenge/BSc-Bachelor-Angewandte-Psychologie)

Link to Admission/Exam Regulations [Zulassungsreglement V3.0_KFH.pdf](https://github.com/DigiBP/Boese/files/8838430/Zulassungsreglement.V3.0_KFH.pdf) [Prüfungsreglement_Weiterbildung (ID 1521911).pdf](https://github.com/DigiBP/Boese/files/8838433/Prufungsreglement_Weiterbildung.ID.1521911.pdf)

                                                                                                                                                      
Link to [Mock-up Website](https://sites.google.com/view/teamboese)

## Camunda Engine
Link to [Camunda Engine](https://digibp.herokuapp.com/camunda/app/tasklist/default/#/login)

### Camunda user

## Make (Integromat)
Link to [Make](https://www.make.com/en/login)
                                                                                                                                                      
Make Login-in:
Email: bpma06olten@gmail.com
Password: Olten2022#Z

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
