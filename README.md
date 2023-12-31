# Grafana Docker Setup

This repository contains the necessary files to set up a Grafana instance along with a MySQL database using Docker Compose. You can use this setup to explore Grafana's features and create visualizations based on the provided data.

## Getting Started

1. Clone this repository to your local machine:

`git clone https://github.com/TomMcC89/GrafanaDemo.git`

Navigate to the cloned repository:

`cd GrafanaDemo`

Start the Grafana and MySQL containers:

`docker-compose up -d`

2. Populate the Metrics schema:
A sample script (test-data.sql) can be ran in a MYSQl db client (such as DataGrip, SequelPro, or MySQL workbench) which will populate a metrics.deployments table with sample data including a build_id, timestamp & pass/fail data.

3. Access Grafana:

Open your web browser and go to http://localhost:3001.
Log in using the admin credentials (Username: admin, Password: admin).

4. Connect to the MySQL Data Source:

Add a MySQL data source in Grafana by specifying the host as mysql, username, password, and database details as provided in the docker-compose.yml file.

5. Create Visualizations:

Use Grafana's Query Editor to create dashboards and visualizations based on the "deployments" data.

6. (Optional) Import the QA.json dashboard file via dashboards > new > import.


## Troubleshooting
1. Connection Issues
If you're having trouble connecting to Grafana or the MySQL database, make sure you've started the Docker containers using docker-compose up -d.
Double-check the host and port configurations in Grafana to match those in the docker-compose.yml file.
2. Data Not Showing
If you don't see data in Grafana, ensure that you've correctly executed the SQL script (test-data.sql) to populate the MySQL database with sample data.
3. Permissions or Volume Issues
Ensure that the grafana_data and mysql_data directories are created in the same directory as your Docker Compose file.
Check that the user running Docker has sufficient permissions to read and write to these directories.
4. Grafana Login Issues
If you're unable to log in to Grafana, use the default admin credentials: Username: admin, Password: admin.
You can change these credentials later within Grafana.