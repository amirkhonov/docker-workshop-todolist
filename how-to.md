## Database

docker run --name todo-list-db -p 5432:5432 -e POSTGRES_DB=tododb -e POSTGRES_USER=todouser -e POSTGRES_PASSWORD=todopassword -d postgres

## Backend

docker build -t babanin/todo-list-backend:latest -t babanin/todo-list-backend:0.1 .
docker run --net=host -p 3001:3001 -e DATABASE_HOST=localhost -e DATABASE_USER=todouser -e DATABASE_PASS=todopassword babanin/todo-list
-backend

## Frontend

docker build -t babanin/todo-list-frontend:latest -t babanin/todo-list-frontend:0.1 .
docker run -p 3000:80 -e API_URL=http://localhost:3001 babanin/todo-list-frontend
