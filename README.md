Project Overview
ReactReduxTasker is an application for managing personal tasks, tasks within a group or at work, school, or home, Ideally, it is an application of Web-Portofolio created using a modern React Framework – Redux, with features of Toolkit, and combined with Bootstrap. Through the help of the control panel, users are able to perform operations such as creating, modifying as well as deleting tasks. Every task has a title and a description in the form of text or as a webmap. The application provides the ability to save tasks locally by creating a JSON file in the browser’s local storage.

Key Functionalities
Add Task: A feature users can afford to an application is the ability to add a new task with a title and description.

Edit Task: The title and a brief description of a task can be edited by the users who have initiated the creation of the given task.

Delete Task: Users can delete a task.
[Currently, when a user gets to a task, he/she has the ability to delete it from a list of tasks].

Persist Tasks: By default, local storage is used, which means that the tasks will still be there after the page is refreshed.


Project Structure
The project is organized into the following directories and files:
api: Contains API calls for fetching, creating, updating, and deleting tasks.
components: Contains React components for the task management interface.
redux: Contains the Redux store and slice for managing task state.
styles: Contains CSS files for styling the application.
App.tsx: The main application component.
index.tsx: The entry point of the application.


Implementation Steps
Setup Redux Store and Slice:
Create a Redux store using @reduxjs/toolkit's configureStore.
Define a slice (tasksSlice) with actions and reducers for managing tasks (add, edit, delete).
Create async thunks for API calls to load, create, update, and delete tasks.
Create API Integration:
Use axios to define functions for API requests.
Implement functions for fetching all tasks, creating a new task, updating a task, and deleting a task.


Build React Components:
AddTask: A form component for adding new tasks.
Contains input fields for title and description.
Dispatches the addTask action on form submission.
TaskList: A component for displaying the list of tasks.
Fetches tasks from the Redux store and displays them.
Includes edit and delete buttons for each task.
Provides input fields for editing tasks inline.


Apply Styling:
Use Bootstrap classes for basic styling.
Add custom CSS for additional styling and layout adjustments.
Ensure the layout is responsive and visually appealing.


Persist Data in Local Storage:
Use redux-persist to save the Redux state to local storage.
Configure the Redux store to use redux-persist's persistReducer and persistStore.


Detailed Explanation of Core Features

Adding a Task
Component: AddTask
Functionality: Allows users to input a title and description for a new task.
Process:
User fills in the title and description fields.
On form submission, the addTask action is dispatched.
The task is added to the Redux store and sent to the backend API.

Editing a Task
Component: TaskList
Functionality: Allows users to edit the title and description of an existing task.
Process:
User clicks the edit button next to a task.
The task's title and description are displayed in editable fields.
User makes changes and clicks the save button.
The editTask action is dispatched with the updated task details.
The task is updated in the Redux store and sent to the backend API.

Deleting a Task
Component: TaskList
Functionality: Allows users to delete an existing task.
Process:
User clicks the delete button next to a task.
The deleteTask action is dispatched with the task ID.
The task is removed from the Redux store and deleted from the backend API.

Persisting Tasks
Tool: redux-persist
Functionality: Ensures tasks are saved in local storage and reloaded when the application is reopened.
Process:
Configure redux-persist to use local storage as the storage medium.
Wrap the root reducer with persistReducer.
Use persistStore to persist the Redux store.
