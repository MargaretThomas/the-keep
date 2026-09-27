# Project Backlog

## Foundation

- [x] **Initialise repository structure**  
  Create the base repository folders and supporting files.

- [x] **Create basic Vue app**  
  Initialise a minimal Vue 3 + Vite application inside `/code`.

- [x] **Create basic app layout**  
  Build the initial single-page structure for The Keep with space for importing, browsing, organising, and reviewing chats.

- [x] **Add simple navigation**  
  Add lightweight navigation between the main areas of the app without introducing unnecessary routing complexity.

- [ ] **Define local data structure**  
  Decide how chats, project assignments, actions, review states, and notes are represented in local JSON.

## Chat Import

- [ ] **Import initial ChatGPT conversation data**  
  Allow the user to select and import ChatGPT conversation JSON into The Keep.

- [ ] **Parse conversation data**  
  Convert the ChatGPT export format into the internal format used by The Keep.

- [ ] **Store imported conversations locally**  
  Save the imported chat data into The Keep's local JSON structure without modifying the original export.

- [ ] **Import new or updated chats**  
  Support future ChatGPT exports without replacing the existing dataset.

  When a new export is imported:
  - Add conversations that do not already exist.
  - Update existing conversations when their exported data has changed.
  - Preserve The Keep's own organisation data such as projects, notes, actions, and review state.
  - Update relevant ChatGPT metadata such as title, timestamps, or project information when newer data is available.
  - Avoid creating duplicate chats.

- [ ] **Show import summary**  
  After importing, show how many conversations were added, updated, unchanged, or skipped.

- [ ] **Handle import errors**  
  Provide clear feedback when a file is missing expected data or cannot be parsed.

## Browse & Visualise

- [ ] **Display conversation list**  
  Show imported chats with useful metadata such as title, date, project, and action.

- [ ] **Search chats**  
  Search conversation titles and available message content.

- [ ] **Filter chats**  
  Filter by date, project, action, review state, or other useful metadata.

- [ ] **Sort chats**  
  Sort conversations by fields such as newest, oldest, title, or message count.

- [ ] **Add basic visual overview**  
  Provide a simple visual summary of the conversation collection.

- [ ] **Show conversation counts**  
  Display useful totals for chats, projects, and action states.

## Organise

- [ ] **Create custom projects**  
  Allow projects such as Gardening, Career, Art, or other user-defined groups.

- [ ] **Assign chats to projects**  
  Record the chat’s current imported ChatGPT project and, where needed, the target project it should be moved to.

- [ ] **Add reviewed state**  
  Mark chats as reviewed or unreviewed to make large cleanup sessions manageable.

- [ ] **Add notes**  
  Allow short local notes to be attached to a conversation.

- [ ] **Bulk select chats**  
  Select multiple conversations and apply organisation changes together.

## Actions

- [ ] **Mark chats as Keep**  
  Identify conversations that should remain where they are.

- [ ] **Mark chats as Move**  
  Identify conversations that should be moved into a ChatGPT Project.

- [ ] **Mark chats as Archive**  
  Identify conversations that should be removed from the main ChatGPT history but retained.

- [ ] **Mark chats as Delete**  
  Identify conversations that may eventually be deleted.

- [ ] **Filter by action**  
  View only conversations assigned to a particular action.

- [ ] **Create action queues**  
  Group chats into practical queues such as "Move to Gardening" or "Archive".

- [ ] **Open chats in batches**  
  Open selected ChatGPT conversations in manageable batches, such as 10 at a time, for manual action.

- [ ] **Track completed actions**  
  Record which queued chats have already been processed in ChatGPT.

## Local Data

- [ ] **Save organisation data to JSON**  
  Store The Keep's project assignments, actions, notes, and review states separately from the original ChatGPT data.

- [ ] **Load existing organisation data**  
  Restore previous work when reopening The Keep.

- [ ] **Export organisation data**  
  Allow The Keep's local data to be backed up as ordinary JSON.

- [ ] **Use localStorage for lightweight UI state**  
  Store temporary preferences such as active filters, sort order, or view mode in the browser.

## Polish

- [ ] **Improve visual design**  
  Develop a clean interface that makes large chat collections comfortable to browse.

- [ ] **Add empty states**  
  Provide useful screens when no chats have been imported or a filter has no results.

- [ ] **Add confirmations where needed**  
  Protect actions that could cause accidental loss of organisation data.

- [ ] **Add progress summaries**  
  Show how much of the collection has been reviewed, organised, or processed.

- [ ] **Add responsive layout**  
  Ensure the interface remains usable across different screen sizes.