# Docker Configuration for WordPress with Nginx and MySQL  

This repository contains Docker configuration files to set up and run a WordPress instance with Nginx and MySQL using Docker Compose on Ubuntu 22.04.  

## Features  
- WordPress with a pre-configured database  
- Nginx as the web server  
- MySQL as the database backend  
- Persistent storage for both WordPress and MySQL  

## Requirements  
- Ubuntu 22.04  
- Docker 20.10 or later  
- Docker Compose  

## Setup  

### 1. Clone the Repository  
```bash  
git clone https://github.com/<your-username>/<repo-name>.git  
cd <repo-name>  
```  

### 2. Configure Environment Variables  
Rename the `.env.example` file to `.env` and modify the following values as needed:  
```bash  
cp .env.example .env  
```

- `WORDPRESS_DB_NAME`: Name of the WordPress database  
- `WORDPRESS_DB_USER`: MySQL user for WordPress  
- `WORDPRESS_DB_PASSWORD`: Password for the MySQL user  
- `MYSQL_ROOT_PASSWORD`: Root password for MySQL  

### 3. Start the Containers  
Run the following command to start all containers:  
```bash  
docker-compose up -d  
```  

### 4. Access the Application  
- Visit your WordPress site at `http://localhost` or your server’s IP address.  
- Configure WordPress using the credentials specified in the `.env` file.  

## Folder Structure  
```plaintext  
.  
├── docker-compose.yml      # Docker Compose configuration  
├── nginx/  
│   └── default.conf        # Nginx configuration  
├── wordpress/  
│   └── wp-content/         # Persistent WordPress content  
├── mysql/  
│   └── data/               # Persistent MySQL data  
└── .env.example            # Environment variable template  
```  

## Stopping and Cleaning Up  
To stop the containers without removing them:  
```bash  
docker-compose stop  
```  

To stop and remove all containers, networks, and volumes:  
```bash  
docker-compose down -v  
```  

## Contributing  
Feel free to open issues or submit pull requests for improvements.  

## License  
This project is licensed under the MIT License.  
