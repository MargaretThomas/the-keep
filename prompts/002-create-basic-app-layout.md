# Create basic app layout

Replace the current `Hello World` screen with the initial single-page layout for **The Keep**.

Keep the existing Vue 3 + Vite + JavaScript + plain CSS setup. Do not add new dependencies.

## Layout

Create a clean desktop-first interface with:

### Header
- The Keep
- Short subtitle
- Placeholder import button

### Sidebar
Include navigation for:
- All Chats
- Projects
- Unreviewed
- Keep
- Move
- Archive
- Delete

Add a few placeholder projects to demonstrate the layout.

### Main area
Include:
- Search input
- Filter control
- Sort control
- Simple placeholder counts for chats, projects, reviewed, and unreviewed
- A small list of hard-coded sample conversations

Each conversation should have space for:
- Title
- Date
- Project
- Review state
- Action

### Review area
Add a simple panel for the selected conversation with space for:
- Title
- Current project
- Intended project
- Action
- Reviewed state
- Notes

Use placeholder content only.

## Theme

Use:

```text
#56d6d6
#45aea8
#348579
#0f6266
#5187a1
#93acdb
#829aed
```

Also use white, black, and neutral greys where needed for backgrounds, text, borders, and dividers.

Keep the design clean and practical with good spacing, subtle borders, restrained rounded corners, and clear visual hierarchy.

Use the theme colours intentionally rather than using every colour everywhere.

## Scope

This task is for the visual layout only.

Do not:
- Add Vue Router
- Implement importing
- Implement real search, filters, or sorting
- Add persistent data or localStorage
- Create the final data model
- Implement project management
- Add external UI libraries
- Over-engineer the component structure

Basic responsive behaviour is enough for now.

The goal is simply to establish the visual skeleton that later backlog tasks can make functional.