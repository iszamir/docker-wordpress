# Dockerized WordPress

[![Docker](https://img.shields.io/badge/Docker-blue?logo=docker&logoColor=white)](https://www.docker.com/)
[![WordPress](https://img.shields.io/badge/WordPress-blue?logo=wordpress&logoColor=white)](https://wordpress.org/)

A simple and easy-to-use Docker setup for running WordPress with MariaDB.

## Table of Contents

* [About the Project](#about-the-project)
* [Getting Started](#getting-started)
    * [Prerequisites](#prerequisites)
    * [Installation](#installation)
* [Usage](#usage)
* [Configuration](#configuration)


## About the Project

This project provides a Docker Compose configuration to quickly spin up a WordPress website with a MariaDB database. It's designed for local development, testing, or even small-scale deployments.

Key features:

* Uses the official `wordpress:latest` and `mariadb:10.6` Docker images.
* Configured with environment variables for easy setup.
* Includes persistent volumes for database and WordPress data.
* Exposes WordPress on port `8000` of the host machine.
* Optionally includes WP-CLI for WordPress command-line management.

## Getting Started

Follow these steps to get your own WordPress instance running locally.

### Prerequisites

* **Docker:** You need to have Docker installed on your system. You can find installation instructions for your operating system on the [official Docker website](https://docs.docker.com/get-docker/).
* **Docker Compose:** Docker Compose is usually installed along with Docker Desktop. If you installed Docker Engine separately, you might need to install Docker Compose separately. Instructions can be found [here](https://docs.docker.com/compose/install/).
* **Git:** (Optional, but recommended for cloning this repository) You need Git installed to clone this repository. You likely already have it if you just pushed your project to GitHub.

### Installation

1.  **Clone the repository (if you haven't already):**

    ```bash
    git clone [https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME.git](https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME.git)
    cd YOUR_REPOSITORY_NAME
    ```

    (Replace `YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME` with the actual URL of your repository).

2.  **Navigate to the project directory:**

    ```bash
    cd YOUR_REPOSITORY_DIRECTORY
    ```

3.  **Start the Docker containers:**

    ```bash
    docker-compose up -d
    ```

    This command will download the necessary Docker images (if they haven't been downloaded before) and start the WordPress and MariaDB containers in detached mode.

## Usage

Once the containers are running, you can access your WordPress website by opening your web browser and navigating to:

http://localhost:8000


This will take you to the WordPress installation wizard if it's the first time you're running it. Follow the on-screen instructions to set up your WordPress site (choose a site title, username, password, email, etc.).

To access the WordPress admin dashboard, go to:

http://localhost:8000/wp-admin/


Use the username and password you created during the installation.

## Configuration

The database connection details for WordPress are configured using environment variables in the `docker-compose.yml` file:

```yaml
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress

You can modify these if needed. The MariaDB service also has environment variables for its root password and the initial database and user.
Contributing

If you'd like to contribute to this project, please feel free to:

    Fork the repository.
    Create a new branch for your feature or bug fix.
    Make your changes.
    Commit your changes
