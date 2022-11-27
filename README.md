# Docker example setup for fullstack project

This project is an example of setup for connecting contenerized applications of frontend and backend using docker compose.

## Docker

- Each project has own Dockerfile where one can specify image and all steps to run a project.
- docker-compose.yml maps ports and points to each Dokerfile to run whole system and download dependencies.
- check `localhost:3001` in browser for frontend. You shoud see Lorem ipsum paragraph.
- check `localhost:8080` in browser for backend.

### How to run project?

1. Open terminal and go to folder containing repo and type `docker-compose up`

## Frontend

Basic Nuxt Project fetching data from backend container.

## Backend

Simple PHP script returning json with lorem ipsum.
