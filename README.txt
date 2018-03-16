DEPLOYING TO HEROKU
---------------------------------------------

heroku login

heroku create

heroku addons:create heroku-postgresql:hobby-dev


--------------------------------------------------------------------------------
<!--Use this dependency to deploy to Heroku. pom.xml file:-->
	<dependency>
		<groupId>org.postgresql</groupId>
		<artifactId>postgresql</artifactId>
		<version>9.4-1201-jdbc4</version>
	</dependency>



#===application.properties file change:
#======================================
# = HEROKU DATA SOURCE
#=======================================
spring.datasource.url=${JDBC_DATABASE_URL}
spring.datasource.username=${JDBC_DATABASE_USERNAME}
spring.datasource.password=${JDBC_DATABASE_PASSWORD}



# ===============================
# = JPA / HIBERNATE / WITH Heroku
# ===============================
spring.jpa.show-sql = false
spring.jpa.generate-ddl=true
spring.jpa.hibernate.ddl-auto=update
# ===============================
# ===============================
#spring.jpa.hibernate.ddl-auto=create
#spring.jpa.hibernate.ddl-auto=create-drop
#================================
---------------------------------------------------------------------------------

git push heroku master 

----or, if have changes:---------------------

git add .
git commit -m "Database Changes for Heroku"
git push heroku master

git remote add origin https://github.com/aavolkova/SpringBoot2_25_2.git






