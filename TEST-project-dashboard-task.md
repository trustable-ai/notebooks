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

# 6 - Complete responsive redesign and interactive dashboard

Completely redesign the UI to provide a true mobile-first responsive experience without changing any existing functionality.

Every page, component and layout must be reviewed and refactored if necessary.

Responsive requirements:

- Use Tailwind responsive breakpoints (sm, md, lg, xl).
- Design mobile-first, then progressively enhance for larger screens.
- There must never be horizontal scrolling.
- Every page must be fully usable at widths from 320px to 1920px.

Navigation:
- On mobile replace the sidebar with a hamburger menu or slide drawer.
- Collapse navigation when screen width is small.
- Keep navigation accessible on every device.

Dashboard:
- Statistic cards must become a 1-column layout on phones.
- Use 2 columns on tablets.
- Use 3–4 columns on desktop depending on available space.
- Cards must have equal height.
- Cards must never overflow.

Interactive statistics:
- Every statistic card must be clickable.
- Clicking a card opens the Tasks page with the correct filter already applied.
- Selected filters remain active until changed by the user.

Task list:
- Replace desktop tables with stacked task cards on mobile.
- Desktop may continue using a table or grid.
- Buttons must wrap correctly.
- Long titles must truncate gracefully.
- Filters become collapsible on small screens.

Forms:
- Inputs occupy full width on phones.
- Buttons stack vertically when necessary.
- Labels remain readable.
- Dialogs never exceed viewport width.

General UI:
- All buttons must have a minimum touch target of 44×44 px.
- Typography scales using responsive Tailwind classes.
- Consistent spacing across breakpoints.
- Images and icons scale correctly.
- Cards, modals and containers adapt fluidly.

Quality checks:
- Test layouts at approximately 320px, 375px, 768px, 1024px, 1440px and 1920px.
- Fix every overflow, clipping, misalignment or broken layout.
- Preserve all existing functionality while improving only the UI and responsiveness.

The application should feel like a production-quality responsive web app, not simply a desktop layout that shrinks on mobile.
