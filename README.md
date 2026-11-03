# TaskFlow — React Task Management Dashboard

A responsive task management dashboard built with React, Vite, and CSS. It demonstrates reusable components, React state, event handling, conditional rendering, form validation, and filtering.

## Features

- Dashboard counts for total, pending, and completed tasks.
- Add tasks with a required title, optional description, and Low/Medium/High priority.
- Rejects empty and whitespace-only titles.
- Toggle tasks between Pending and Completed.
- Delete tasks.
- Filter by All, Pending, and Completed.
- Responsive desktop and mobile layouts.
- Saves tasks in `localStorage`, so your list remains after refresh.

## Requirements

- Node.js 18 or newer
- npm

## Run locally

1. Extract the project ZIP.
2. Open a terminal in the project folder.
3. Install dependencies:

   ```bash
   npm install
   ```

4. Start the development server:

   ```bash
   npm run dev
   ```

5. Open the local address printed by Vite (usually `http://localhost:5173`).

## Production build

```bash
npm run build
npm run preview
```

## Project structure

```text
task-management-dashboard/
├── index.html
├── package.json
├── README.md
└── src/
    ├── App.jsx
    ├── main.jsx
    ├── styles.css
    └── components/
        ├── DashboardSummary.jsx
        ├── TaskForm.jsx
        ├── TaskList.jsx
        └── TaskCard.jsx
```

## How it works

- `App.jsx` owns the task array and selected filter in React state. It calculates summary counts, adds tasks, toggles status, and deletes tasks.
- `DashboardSummary.jsx` receives the calculated counts through props and displays the three overview cards.
- `TaskForm.jsx` owns the form fields, validates the trimmed title, calls `onAddTask`, and resets after a successful submission.
- `TaskList.jsx` renders the filter controls and conditionally displays task cards or an empty state.
- `TaskCard.jsx` displays one task and exposes status and delete actions through callback props.
- `styles.css` contains the visual design and responsive breakpoints.

Task IDs are generated with `crypto.randomUUID()` where available, with a timestamp-based fallback. The optional `localStorage` enhancement is included.

## Reset sample tasks

The starter tasks are loaded only when no saved list exists. To reset the browser's saved list, open the browser developer console and run:

```js
localStorage.removeItem('taskflow-tasks');
location.reload();
```
