# To-Do List Application

A simple **To-Do List Application** built using HTML, CSS, and JavaScript. This project allows users to add, update, and delete tasks. Tasks are stored in the browser's local storage to ensure persistence even after the page is refreshed.
# Demo https://sagarbangade.github.io/TODO-in-JS/

## Features

- Add tasks with a description and a due date.
- Update existing tasks with new details.
- Delete tasks when no longer needed.
- Persistent storage using localStorage.
- Responsive design with an interactive popup for task updates.

## Technologies Used

- **HTML**: Structure of the application.
- **CSS**: Styling and layout.
- **JavaScript**: Logic for task management and user interaction.
- **LocalStorage**: To save tasks persistently in the browser.

## How to Use

### Adding a Task
1. Enter the task description in the text input field.
2. Select a due date using the date picker.
3. Click the "Add" button to save the task.

### Viewing Tasks
- All tasks are displayed in a grid layout, showing the task description, due date, and action buttons.

### Updating a Task
1. Click the "Update" button for the specific task.
2. A popup will appear with input fields for the updated task description and due date.
3. Enter the new details and click the "Update" button inside the popup to save changes.
4. Close the popup by clicking the "Close" button if needed.

### Deleting a Task
- Click the "Delete" button next to a task to remove it.

## Code Structure

- **HTML**: Defines the layout with input fields, buttons, and containers for displaying tasks.
- **CSS**: Manages styles, grid layout, button designs, and popup appearance.
- **JavaScript**:
  - Adds tasks to the `todoList` array and saves them to localStorage.
  - Updates tasks and re-renders the task list.
  - Deletes tasks from the array and updates localStorage.
  - Manages popup visibility for task updates.

## Installation

1. Clone or download the project files.
2. Open the `index.html` file in your browser.
3. Start adding, updating, and deleting tasks!

## Example Code

### Adding a Task
```javascript
function addTodo() {
  const inputElement = document.querySelector('.js-task');
  const name = inputElement.value;
  const dateInputElement = document.querySelector('.js-date');
  const date = dateInputElement.value;

  todoList.push({
    name,
    date
  });

  inputElement.value = '';
  showtask();
  localStorage.setItem('todoList', JSON.stringify(todoList));
}
```

### Updating a Task
```javascript
function updateTask(index) {
  const nameInput = document.querySelector(`#task-update${index}`);
  const dateInput = document.querySelector(`#date-update${index}`);

  const newName = nameInput.value;
  const newDate = dateInput.value;

  todoList[index].name = newName;
  todoList[index].date = newDate;

  localStorage.setItem('todoList', JSON.stringify(todoList));
  showtask();

  const popup = document.getElementById(`myPopup${index}`);
  popup.style.display = "none";
}
```

## Future Enhancements

- Add task priority levels.
- Implement a search feature to filter tasks.
- Allow users to mark tasks as completed.
- Enhance the UI with animations.

