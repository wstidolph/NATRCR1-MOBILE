---
description: Initialize the agent's understanding of the project
---

# Initialize Workflow

This workflow is used to sync the agent with the current state of the NATRC Region 1 Mobile project.

## Steps

1. **Review Project Structure**:
   - List the root directory to see available HTML files and directories.
   - Check `REFACTORING_README.md` for recent architectural changes.

2. **Verify Site Health**:
   // turbo
   - Start a local server: `npx -y http-server -p 8080 &`
   - Open `http://127.0.0.1:8080` in the browser.
   - Click through the main navigation links (Home, Ride Schedule, Gallery, Contact) to ensure they work.
   - Take a screenshot of the home page.

3. **Check Documentation**:
   - Ensure `.agent/walkthrough.md` is up to date with the current architecture.

4. **Report Status**:
   - Summarize the current state of the project to the user.
