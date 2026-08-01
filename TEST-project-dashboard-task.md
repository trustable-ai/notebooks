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

# 6 - Mobile-first responsive redesign

The current application is designed primarily for desktop. Completely redesign the layout using a mobile-first approach while preserving every existing feature and backend integration.

Do not simply add responsive classes. Refactor the layout where necessary.

## Global layout

- Screens smaller than 768px must use a completely different layout optimized for phones.
- No horizontal scrolling anywhere.
- Every page must fit naturally inside the viewport.
- Maximum content width should remain comfortable on large monitors.

## Navigation

Desktop:
- Keep the left sidebar.

Tablet:
- Collapse the sidebar.

Mobile:
- Replace the sidebar with a hamburger menu and slide-out drawer.
- The header must remain fixed at the top.
- Navigation should never occupy permanent screen space.

## Dashboard

Desktop:
- Keep the current dashboard style.

Tablet:
- Statistics cards in 2 columns.

Mobile:
- Statistics cards become a single vertical column.
- Every chart becomes full width.
- Recent Tasks moves below the charts.
- Priority and Category sections stack vertically.
- All cards use equal spacing and rounded corners.

## Statistics cards

Every statistics card must:
- Be fully clickable.
- Navigate to the Tasks page.
- Automatically apply the correct filter.
- Show hover, focus and active states.
- Have a minimum touch target of 44px.

## Tasks page

Desktop:
- Grid or table layout.

Mobile:
- Replace tables with stacked cards.
- Every task card displays:
  - Title
  - Status
  - Priority
  - Category
  - Due date
  - Action buttons

Buttons wrap naturally and never overflow.

## Search and filters

Desktop:
- Horizontal toolbar.

Tablet:
- Wrap into multiple rows.

Mobile:
- Filters collapse inside a "Filters" expandable section.
- Search bar uses full width.

## Forms

On mobile:
- Every input uses full width.
- Buttons stack vertically.
- Dialogs never exceed screen width.
- Comfortable spacing between controls.

## Charts

Charts must resize automatically.

No chart may overflow its container.

If a chart is too wide, redesign it rather than shrinking it.

## Responsive breakpoints

Use Tailwind breakpoints:

- <640px → Mobile
- 640–767px → Large Mobile
- 768–1023px → Tablet
- 1024–1279px → Laptop
- ≥1280px → Desktop

## Validation

Test and fix the UI at:

- 320px
- 375px
- 390px
- 430px
- 768px
- 1024px
- 1440px
- 1920px

Fix every overflow, clipping, spacing issue, alignment issue and unusable interaction.

The final result should feel like a modern production-quality SaaS application with a dedicated mobile experience, not a desktop interface that simply shrinks.
