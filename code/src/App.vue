<script setup>
const navigation = [
  { label: 'All Chats', count: 24, active: true },
  { label: 'Projects', count: 4 },
  { label: 'Unreviewed', count: 9 },
  { label: 'Keep', count: 8 },
  { label: 'Move', count: 4 },
  { label: 'Archive', count: 2 },
  { label: 'Delete', count: 1 },
]

const projects = [
  { name: 'Product research', colour: 'teal' },
  { name: 'Writing ideas', colour: 'blue' },
  { name: 'Personal admin', colour: 'purple' },
]

const conversations = [
  {
    title: 'Ideas for a weekly planning ritual',
    date: '24 Sep 2026',
    project: 'Personal admin',
    state: 'Unreviewed',
  },
  {
    title: 'Research notes for the onboarding flow',
    date: '22 Sep 2026',
    project: 'Product research',
    state: 'Reviewed',
  },
  {
    title: 'Outline for a long-form essay',
    date: '18 Sep 2026',
    project: 'Writing ideas',
    state: 'Unreviewed',
  },
  {
    title: 'Compare simple feedback tools',
    date: '12 Sep 2026',
    project: 'Product research',
    state: 'Reviewed',
  },
]
</script>

<template>
  <div class="app-shell">
    <header class="app-header">
      <div class="brand">
        <span class="brand-mark">K</span>
        <div>
          <h1>The Keep</h1>
          <p>A calm place to review and organise your conversations.</p>
        </div>
      </div>
      <button class="import-button" type="button">
        <span aria-hidden="true">＋</span>
        Import chats
      </button>
    </header>

    <div class="workspace">
      <aside class="sidebar">
        <nav aria-label="Conversation views">
          <p class="sidebar-label">Library</p>
          <a
            v-for="item in navigation"
            :key="item.label"
            href="#"
            class="nav-item"
            :class="{ active: item.active }"
            @click.prevent
          >
            <span class="nav-name">
              <span class="nav-dot" aria-hidden="true"></span>
              {{ item.label }}
            </span>
            <span class="nav-count">{{ item.count }}</span>
          </a>
        </nav>

        <section class="projects" aria-labelledby="projects-title">
          <div class="sidebar-section-heading">
            <p id="projects-title" class="sidebar-label">Projects</p>
            <button type="button" aria-label="Add project">＋</button>
          </div>
          <ul>
            <li v-for="project in projects" :key="project.name">
              <span class="project-dot" :class="project.colour" aria-hidden="true"></span>
              <span>{{ project.name }}</span>
            </li>
          </ul>
        </section>
      </aside>

      <main class="main-area">
        <section class="library-panel" aria-labelledby="library-title">
          <div class="section-intro">
            <div>
              <p class="eyebrow">Your library</p>
              <h2 id="library-title">Conversation review</h2>
            </div>
            <p>Sort through imported chats and decide what is worth keeping.</p>
          </div>

          <div class="controls" aria-label="Conversation controls">
            <label class="search-field">
              <span class="search-icon" aria-hidden="true"></span>
              <span class="sr-only">Search conversations</span>
              <input type="search" placeholder="Search conversations" />
            </label>
            <label class="select-field">
              <span>Filter</span>
              <select aria-label="Filter conversations">
                <option>All conversations</option>
                <option>Reviewed</option>
                <option>Unreviewed</option>
              </select>
            </label>
            <label class="select-field">
              <span>Sort</span>
              <select aria-label="Sort conversations">
                <option>Newest first</option>
                <option>Oldest first</option>
                <option>Title</option>
              </select>
            </label>
          </div>

          <div class="stats" aria-label="Library totals">
            <article><span>Chats</span><strong>24</strong></article>
            <article><span>Projects</span><strong>4</strong></article>
            <article><span>Reviewed</span><strong>15</strong></article>
            <article class="attention-stat"><span>Unreviewed</span><strong>9</strong></article>
          </div>

          <div class="conversation-list">
            <div class="list-header" aria-hidden="true">
              <span>Conversation</span>
              <span>Date</span>
              <span>Project</span>
              <span>Status</span>
              <span>Action</span>
            </div>

            <article
              v-for="(conversation, index) in conversations"
              :key="conversation.title"
              class="conversation-row"
              :class="{ selected: index === 0 }"
            >
              <div class="conversation-title" data-label="Conversation">
                <span class="conversation-icon" aria-hidden="true">⌁</span>
                <strong>{{ conversation.title }}</strong>
              </div>
              <span data-label="Date">{{ conversation.date }}</span>
              <span data-label="Project">{{ conversation.project }}</span>
              <span data-label="Status">
                <span class="status" :class="{ reviewed: conversation.state === 'Reviewed' }">
                  {{ conversation.state }}
                </span>
              </span>
              <span data-label="Action">
                <button class="text-button" type="button">
                  {{ index === 0 ? 'Selected' : 'Review' }}
                </button>
              </span>
            </article>
          </div>
        </section>

        <aside class="review-panel" aria-labelledby="review-title">
          <div class="review-heading">
            <div>
              <p class="eyebrow">Selected chat</p>
              <h2 id="review-title">Review details</h2>
            </div>
            <span class="status">Unreviewed</span>
          </div>

          <div class="review-title-block">
            <span class="field-label">Title</span>
            <h3>Ideas for a weekly planning ritual</h3>
            <p>Last updated 24 Sep 2026</p>
          </div>

          <div class="review-fields">
            <label>
              <span class="field-label">Current project</span>
              <input type="text" value="Personal admin" readonly />
            </label>
            <label>
              <span class="field-label">Intended project</span>
              <select>
                <option>Personal admin</option>
                <option>Product research</option>
                <option>Writing ideas</option>
              </select>
            </label>
            <label>
              <span class="field-label">Action</span>
              <select>
                <option>Keep</option>
                <option>Move</option>
                <option>Archive</option>
                <option>Delete</option>
              </select>
            </label>
            <div>
              <span class="field-label">Reviewed state</span>
              <div class="state-control">
                <span class="state-indicator" aria-hidden="true"></span>
                Not yet reviewed
              </div>
            </div>
            <label>
              <span class="field-label">Notes</span>
              <textarea rows="5" placeholder="Add a note about this conversation..."></textarea>
            </label>
          </div>

          <div class="review-actions">
            <button class="secondary-button" type="button">Skip for now</button>
            <button class="primary-button" type="button">Mark reviewed</button>
          </div>
        </aside>
      </main>
    </div>
  </div>
</template>
