## Required Installations:
- Java
- Spring Tool Suite
- Required Libraries for pom.xml 

### To install our application, the following Hardware Requirements are needed :
- Intel Core i5 Processor
- 4 GB RAM

### Software Requirements:
- Spring Tools Suite (STS):
  Download and install the latest version of Spring Tools Suite.
- Java Development Kit (JDK):
  Install Java Development Kit from [Oracle](https://www.oracle.com/java/technologies/downloads/)

## Setting up Cloud SQL for Flight Booking System

1. **Log in to Google Cloud**: Visit [cloud.google.com](https://cloud.google.com) and log in to your Google Cloud account.

2. **Check for Cloud SQL Service**: Navigate to the Google services and ensure that Cloud SQL is available.

3. **Create MySQL Instance**: Create a MySQL instance with the Enterprise option. Ensure to configure it according to your requirements.

4. **Create Flight Booking System Database**: Once the MySQL instance is created, set up the Flight Booking System database within the instance.

5. **Retrieve Cloud Shell IP**: Open Cloud Shell and run the following command to retrieve the IP address:
    ```bash
    curl -s checkip.dyndns.org | sed -e 's/.*Current IP Address: //' -e 's/<.*$//'
    ```
    Note down this IP address.

6. **Retrieve Machine IP**: Obtain the IP address of your machine. Example: `34.124.248.153`.

7. **Add IPs to Network Connections**: Add both the Cloud Shell IP and the machine IP to your network connections for proper communication.

8. **Check SQL Connection**: Verify the SQL connection with the instance by using the following command:

    ```bash
    mysql -h 34.171.162.115 -u root -p
    ```
    Enter the password when prompted.

9. **Update Spring Boot Application Properties**: In your Spring Boot application, update the application properties with the SQL instance IP:

    ```properties
    spring.mvc.view.prefix = /WEB-INF/views/
    spring.mvc.view.suffix = .jsp
    spring.jpa.hibernate.ddl-auto=update
    spring.datasource.url=jdbc:mysql://34.171.162.115/FBS  # SQL instance IP
    spring.datasource.username=root
    spring.datasource.password=root
    ```
Follow these steps carefully to ensure the successful setup of Cloud SQL for your Flight Booking System.

### To run the Application:
- Right-click on the project in STS.
- Choose "Run As" > "springboot application" option.
