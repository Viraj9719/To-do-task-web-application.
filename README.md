# Todo Task Web Application

## Architecture

- **Frontend**: React with TypeScript and Tailwind CSS
- **Backend**: Express.js REST API
- **Database**: MySQL 8.0
- **Deployment**: Docker and Docker Compose


## Prerequisites

- Docker
- Docker Compose
- (or Node.js 18+ and MySQL 8.0 for local development)


### Build and Run with Docker

```bash
docker-compose up --build
```

This will:
- Start MySQL database on port 3306
- Build and start the backend API on port 3000
- Build and start the frontend on port 5173

### Access the Application

- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:3000/api/tasks

## Local Development

### Prerequisites

- Node.js 18+
- MySQL 8.0

### Setup

1. **Install root dependencies**:
```bash
npm install
```

2. **Install backend dependencies**:
```bash
cd server
npm install
cd ..
```

3. **Configure environment variables**:
Create a `.env` file in the root directory:
```
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=password
DB_NAME=todo_db
PORT=3000
```

4. **Start MySQL**:
```bash
mysql -u root -p < init.sql
```

5. **Build and run**:
```bash
npm run build
```

6. **Start backend** (in separate terminal):
```bash
cd server
npm start
```

7. **Start frontend** (in separate terminal):
```bash
npm run dev
```


## API Endpoints

### Get Tasks
```
GET /api/tasks
```
Returns the 5 most recent incomplete tasks.


### Create Task
```
POST /api/tasks
```


### Complete Task
```
PUT /api/tasks/:id
```



## Environment Variables

### Frontend
- `VITE_API_URL`: Backend API URL (default: http://localhost:3000)

### Backend
- `DB_HOST`: MySQL host
- `DB_USER`: MySQL user
- `DB_PASSWORD`: MySQL password
- `DB_NAME`: MySQL database name
- `PORT`: Server port (default: 3000)
- `NODE_ENV`: Environment (development/production)


## Testing

Run tests with:
```bash
npm test
```

## License

MIT


