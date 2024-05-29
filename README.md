# Notes App

- Frontend: React, Vite, TailwindCSS, Zod
- Backend: Go, Gin, Gorm
- Database: Online PostgreSQL (ElephantSQL)
  
### Features
1. Add a task
2. Show on-going taskslist
3. Delete a task
4. Update a task
5. Tick to complete a task
6. Show completed tasks

#### Additional Features
1. Deadline for each task with indicator if the task is due
2. Subtasks, with add, update, delete, and tick functions.
3. Progress bar for task with subtasks.

### Architecture
1. Communication between server (Go) and client (React) was done using REST
2. The database has one table "tasks" with these columns:
   - id: uint
   - name: string
   - due: timestamp
   - completed: boolean
   - parentid: null for task, uint for a subtask. This column referring to it's parent task's id.
   - created_at: timestamp
   - updated_at: timestamp
   - deleted_at: timestamp
  
![image](https://github.com/ahanprojects/react-go-notes/assets/68496198/a51b929b-7b8c-43a3-90d0-838a8249a44e)

### Backend
1. Go to `system-flow/backend`
2. Setup .env `PORT` and `DB_URL`. See GORM documentation for more detail about the database setup.
2. Run migration with `go run migrate.go` in the `migrate` folder
3. Build with `go build`
4. Run `.\motion.exe`
5. The backend will be served in `PORT`

### Frontend
1. Go to `system-flow/frontend`
2. Run `npm i` to install the dependencies
3. Run `npm run build`
4. Run `npm run preview`
5. Go to browser and open the link
6. Run `npm run dev` for development

### Screenshots
Active Tasks
![image](https://github.com/ahanprojects/react-go-notes/assets/68496198/efb26685-2e27-4d7f-a928-853d663e4d1e)

Completed Tasks
![image](https://github.com/ahanprojects/react-go-notes/assets/68496198/4c92a693-e167-408a-b3aa-0aaaad40b21b)

New Task
![image](https://github.com/ahanprojects/react-go-notes/assets/68496198/50f1b81e-08cb-460d-a9ef-a083f1ebfbde)

New Subtask (Example when inputs are empty)
![image](https://github.com/ahanprojects/react-go-notes/assets/68496198/c3b7fe2a-88fa-4356-8592-f7baaeae48b6)

Edit Task
![image](https://github.com/ahanprojects/react-go-notes/assets/68496198/29515a7c-a33c-4943-afa9-00e6b71b1236)

