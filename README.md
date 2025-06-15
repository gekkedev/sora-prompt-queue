# Sora Prompt Queue Userscript

A Tampermonkey/Greasemonkey userscript that adds a prompt-queue feature to Sora. Manage your collection of prompts in a simple GUI, persist them across page reloads, track which have been submitted, and re-queue prompts as needed.

---

## Features

- **Prompt Management GUI**  
  Add, edit, reorder, and remove prompts in a sidebar panel.
- **Persistent Storage**  
  All prompts and their submission statuses are stored in `localStorage`, surviving page reloads.
- **Submission Tracking**  
  Each prompt has a “submitted” flag. Submitted prompts are visually marked. You can unmark to resubmit.
- **Easy Submission**  
  Click a prompt in the queue to auto-fill Sora’s input box, submit it, and mark it as submitted (optional).
- **Bulk Actions**  
  Mark all as unsubmitted, clear submitted prompts, or import/export your prompt list as JSON.
- **Customizable**  
  Initial prompt array and localStorage key are configurable in the script header.

---

## Installation

1. Install [Tampermonkey](https://www.tampermonkey.net/) or [Greasemonkey](https://www.greasespot.net/) in your browser.
2. Click **“Add new script…”** and paste in the contents of `sora-prompt-queue.user.js`.
3. Save the script and make sure it’s enabled.
4. Navigate to your Sora chat page—your prompt-queue sidebar should appear automatically.

---

## Usage

1. **Open the Sidebar**  
   Click the floating “📋 Prompt Queue” button in the bottom-right corner.
2. **Add a Prompt**  
   - Click **“+ Add Prompt”**.  
   - Enter your prompt text and press **Enter** (or click **Save**).
3. **Reorder Prompts**  
   - Drag and drop prompts in the list to rearrange.
4. **Submit a Prompt**  
   - Click the “▶️” button next to any prompt to auto-fill and submit it in Sora.  
   - The prompt will then be marked as **Submitted**.
5. **Toggle Submission Status**  
   - Click the checkmark icon to toggle “submitted” on/off for any prompt.
6. **Bulk Actions**  
   - **Unsubmit All**: Reset all prompts to unsubmitted.  
   - **Clear Submitted**: Remove all prompts marked as submitted.  
   - **Import/Export**: Copy JSON to import a list, or export your current list as JSON for backup.

---

## Configuration

At the top of the userscript file, you can adjust:

```js
// ==UserScript==
// @name        Sora Prompt Queue
// @namespace   https://your.domain/
// @version     1.0.0
// @match       https://sora.example.com/*
// @grant       none
// @run-at      document-end
// ==/UserScript==

(function() {
  /** @type {string} Key under which prompts are stored in localStorage */
  const STORAGE_KEY = 'soraPromptQueue';

  /** @type {Array<{ id: string, text: string, submitted: boolean }>} */
  let prompts = [];
  // ...
})();
