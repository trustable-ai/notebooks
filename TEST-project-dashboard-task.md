# 1 - Project setup and initial working interface

Create a new application called Project Dashboard Task using React and Tailwind CSS.

Set up a clean architecture with:
- Dashboard page
- Tasks page
- Reusable UI components
- Services folder for future integrations

Prepare the project structure for MongoDB, Redis, TodoWrite and Nuvolaris OpenServerless integrations without implementing them yet.

Build a fully working first version containing:
- Responsive layout
- Appropriate button size
- Sidebar or top navigation
- Dashboard page
- Tasks page
- Basic task cards
- Working navigation between pages

Ensure the application is fully runnable and usable before moving to the next step.

---

# 2 - Task management with MongoDB and TodoWrite

Replace the mock task storage with MongoDB.

Each task must contain:
- Title
- Description
- Category
- Priority (low, medium, high)
- Due date
- Status (todo, in progress, completed)
- Creation date

Create backend APIs or Nuvolaris OpenServerless actions to:
- Create tasks
- Read tasks
- Update tasks
- Delete tasks

Integrate TodoWrite to manage task operations.

Implement:
- Create task form
- Edit task form
- Delete task action
- Complete task action
- Task list page
- Filters by status and priority

Verify the entire CRUD workflow works correctly before continuing.

---

# 3 - Fast search and Redis caching

Add a complete search and filtering system.

Implement:
- Global search bar
- Search by title
- Search by description
- Filter by category
- Filter by priority
- Filter by status
- Real-time search updates

Use Redis to:
- Cache frequently requested task lists
- Cache common searches
- Improve dashboard loading performance

Ensure the application remains fully functional and testable after adding caching.

---

# 4 - Statistics dashboard and UI improvements

Build the statistics dashboard.

Display:
- Total tasks
- Completed tasks
- Pending tasks
- Overdue tasks
- Tasks grouped by priority
- Tasks grouped by category
- Completion percentage

Create clear dashboard cards and visual components.

Improve the interface with Tailwind CSS:
- Responsive layout
- Status badges
- Priority badges
- Loading states
- Empty states
- Error states

Statistics must update automatically whenever tasks change.

---

# 5 - Final polish, testing and deployment preparation

Review the entire Project Dashboard Task application.

Verify:
- Navigation works correctly
- All CRUD operations work
- TodoWrite integration works
- MongoDB integration works
- Redis caching works
- Search works correctly
- Statistics update correctly
- Responsive design works on all screen sizes
- Nuvolaris OpenServerless functions are properly configured

Improve:
- Error handling
- Code quality
- Performance
- Accessibility
- User experience

Prepare the application for deployment while keeping all features fully functional.

---

# 6 - Interactive dashboard, clickable statistics and full mobile responsiveness

Enhance the Project Dashboard Task application by improving navigation, usability and responsiveness.

Make every statistics card on the Home Dashboard fully clickable.

Clicking a statistics card must automatically navigate to the Tasks page with the corresponding filters already applied. Examples:
- Total Tasks → show all tasks
- Completed Tasks → show only completed tasks
- Pending Tasks → show only pending tasks
- Overdue Tasks → show only overdue tasks
- High Priority → show only high priority tasks
- A category card → show only tasks from that category

Ensure filters are synchronized with the URL or application state so they persist after navigation.

Improve the overall user experience by:
- Adding hover, focus and active states
- Making cards keyboard accessible
- Displaying clear loading and empty states
- Preserving selected filters when returning to the dashboard

Make the entire application fully mobile responsive.

Optimize every page for phones, tablets and desktops by ensuring:
- Responsive navigation
- Responsive dashboard cards
- Responsive task list and forms
- Proper spacing and typography on small screens
- No horizontal scrolling
- Buttons remain easy to tap
- Dialogs and forms fit small displays
- Statistics cards wrap correctly
- Tables become responsive cards when necessary

Review every page and component to guarantee a consistent responsive layout, smooth navigation and a polished user experience across all supported screen sizes.
