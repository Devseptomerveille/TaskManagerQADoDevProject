# Docker Setup

## Docker Compose Configuration

- MySQL service
- Backend Laravel service
- Jenkins service
- Node-RED service

## Backend Dockerfile

Located at: `backend/Dockerfile`

## phpMyAdmin Integration

A phpMyAdmin service has been added to manage MySQL through a web interface.

Docker Compose configuration:

```yaml
phpmyadmin:
  image: phpmyadmin/phpmyadmin
  container_name: taskmanager_phpmyadmin
  restart: always
  ports:
    - "8081:80"
  environment:
    PMA_HOST: mysql
    PMA_PORT: 3306
  depends_on:
    - mysql

