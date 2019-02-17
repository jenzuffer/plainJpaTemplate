# plainJpaTemplate
Fork this project to get a ready to use template for JPA-development in a plain java project (no web server)

# Getting started
- Clone the project (from your fork) and navigate into the project folder

### Change settings in the POM-file
**Important:**
The first thing you should do is, change the following settings in your POM-file:

- `groupId` : This will identify your project uniquely across all projects, so you need to enforce a unique naming schema. 
- `artifactId`: This will be the name of the jar without the version. You can choose "anything" you like for this name
- `version`: Leave it as it is for SNAPSHOT versioning, or replace with typical version numbers if you like (1.0, 1.0.1, 1.1, ...)

[See higest voted answer for details](https://stackoverflow.com/questions/3724415/maven-artifact-and-groupid-naming)


### Executing the test cases
- run `maven test` to execute the simple JUnit Case that ships with the project
- run `maven verify`to execute the simple integration test that ships with the project 
(this is a copy of the simple Unit-test, it's added to demonstrate how to add integration tests)

This worked, because the project ships with a persistence.xml file in `\src\test\resources\META-INF\persistence.xml` 
which uses an in-memory derby database

### Setting up your Local Database

Use MySQL Workbench to create a new database for the project (jpademo, for example)
The real persistence.xml file is git-ignored, so you don't get it with the project. The project, however, does contain a template in `\src\main\resources\META-INF\persistence_TEMPLATE.xml`

- Open this file and (in source mode) change properties to reflect the database you just created
- Rename this file to persistence.xml
- TBD (make an option to do this without NetBeans) Open the project in NetBeans and run the file `utils.Tester` 
- Verify that this created the Single table in your database

**Now your project is ready for you to do great stuff :smiley:**
