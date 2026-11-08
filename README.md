# Little Things

Little Things is a small, dependency-free to-do app. The complete app is in
`index.html`; it uses native browser APIs and does not need a build step,
server, package manager, or network connection.

## Run the app

Open `index.html` in a modern web browser. Tasks are stored in that browser's
local storage, so the app works offline after the file is available.

## Features

- **Add tasks:** Enter a task and select **Add task** or submit the form.
  Blank entries are ignored.
- **Complete and delete tasks:** Use the checkbox to toggle completion or the
  delete button to remove a task.
- **Filter the list:** Choose **All**, **Active**, or **Completed**. The task
  count and completion progress continue to reflect the full list.
- **Set optional due dates:** Choose a date with the native date control on
  each task. The date is displayed with a clear label; overdue dates are
  highlighted for tasks that are not complete.
- **Reorder tasks:** Drag a task by its handle, or use its **Move up** and
  **Move down** buttons. The buttons provide a non-drag alternative for
  keyboard and touch users. When a filter is active, reordering moves tasks
  within the visible list positions while leaving hidden tasks in place.
- **Clear completed tasks:** Use **Clear completed** to remove all completed
  tasks.
- **Adapt to your device and preferences:** The layout is narrow and responsive,
  follows the operating system's light or dark color scheme, and respects the
  reduced-motion preference.

## Persistence and compatibility

Tasks are saved automatically in the browser's `localStorage` under
`little-things-tasks-v1`. Each record contains an `id`, `text`, and `done`
value; new records also include a `dueDate` value (`YYYY-MM-DD`, or an empty
string when no date is set). The array order is the task order.

Previously saved records without a `dueDate` remain usable and are treated as
tasks without a due date. Invalid saved due dates are ignored. Starter tasks are
shown only when the storage key has not been set; clearing or deleting tasks
does not restore them. Storage is local to the browser profile and is not
synchronized across devices.

## Accessibility

Interactive controls have accessible names and visible focus indicators. The
task filters expose their selected state, and task reordering can be performed
without dragging. Changes to task order are announced to assistive technology.
The app also uses semantic form controls, including the browser's native date
input.

## Project structure

- `index.html` — app markup, styles, and JavaScript.
- `README.md` — usage and feature documentation.
