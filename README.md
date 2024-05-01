# Introduction

This repository is a fork of the official Apache Superset Docker Compose repository, it's designed to simplify deployment. For detailed information on additional configurations, please refer to the [Apache Superset Docker Installation Guide](https://superset.apache.org/docs/installation/docker-compose) and the [official Apache Superset GitHub repository](https://github.com/apache/superset).

## Getting Started

### Important Preliminary Steps

Before starting the quick setup, please note the following adjustments:



1. **File Renaming**:
   To better align with production environments, the original `docker-compose.yml` has been renamed to `docker-compose-dev.yml`, and `docker-compose-image-tag.yml` has been renamed to `docker-compose.yml`. Ensure you are using the correct file for your needs.

2. **Important Note on Port Mapping**: The `docker-compose.yml` file contains a port mapping to `127.0.0.1`, limiting access to the localhost only. To make the service accessible from other machines or publicly, change the IP address in the port mapping. For instance, use `0.0.0.0` to bind to all network interfaces, updating the ports line to `- "0.0.0.0:8088:8088"` for broader network access.

3. **Configuration of `docker/.env` File**:
   The `docker/.env` file is pre-configured with settings that are fully functional for a development environment. However, to align with the specific requirements of a production environment and achieve optimal operation, further modifications are recommended. Below are key configuration steps to ensure your Apache Superset installation is secure and tailored to your needs:

   - **Version Configuration**:
     The `docker/.env` file is preset with the `TAG` version `4.0.0` of Apache Superset. To deploy a different version, update the image tag in the `docker/.env` file.

   - **Environment Setup**:
     Alter `SUPERSET_ENV` from `development` to `production` to remove the development environment indicator from the Superset frontend.
   
   - **Security Enhancements**:
     Enhance your installation's security by updating the following variables:
     - `DATABASE_PASSWORD`
     - `EXAMPLES_PASSWORD`
     - `POSTGRES_PASSWORD`
     - `SUPERSET_SECRET_KEY`

### Quick Setup

Follow these steps to quickly set up and start Apache Superset:

1. **Clone the Repository**:
   Clone this repository to your local machine using the following Git command:
   ```bash
   git clone https://github.com/ramuyk/docker-superset.git
   cd docker-superset
   ```

2. **Build and Start Superset**:
   Use the following command to build the Superset image and start the service using the custom Docker Compose file:
   ```bash
   docker compose up -d
   ```

3. **Access Apache Superset**:
   Open a web browser and navigate to `http://localhost:10030` to access the Apache Superset web interface. The default login credentials are:
   - **Username**: admin
   - **Password**: admin

   It is highly recommended to change these default credentials after your first login to enhance security.

## Screenshots & Gifs

**Video Overview**
<!-- File hosted here https://github.com/apache/superset-site/raw/lfs/superset-video-4k.mp4 -->
https://user-images.githubusercontent.com/64562059/234390129-321d4f35-cb4b-45e8-89d9-20ae292f34fc.mp4

<br/>

**Large Gallery of Visualizations**

<kbd><img title="Gallery" src="superset-frontend/src/assets/images/screenshots/gallery.jpg"/></kbd><br/>

**Craft Beautiful, Dynamic Dashboards**

<kbd><img title="View Dashboards" src="superset-frontend/src/assets/images/screenshots/slack_dash.jpg"/></kbd><br/>

**No-Code Chart Builder**

<kbd><img title="Slice & dice your data" src="superset-frontend/src/assets/images/screenshots/explore.jpg"/></kbd><br/>

**Powerful SQL Editor**

<kbd><img title="SQL Lab" src="superset-frontend/src/assets/images/screenshots/sql_lab.jpg"/></kbd><br/>

