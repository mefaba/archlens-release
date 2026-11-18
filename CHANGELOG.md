# Changelog

## 0.3.0

- Your coding agents connect to the running ArchLens, at `http://localhost:47821/mcp`, instead of each starting its own copy. A visualization they start is made in ArchLens, shows on the **Create** page, and keeps going if you close the agent session. ArchLens has to be running when the agent session starts. **After updating from 0.2.0, open Settings → Coding agents and choose Update for each agent.** Until then, they keep working as before.
- Closing the window keeps ArchLens running in the notification area (the system tray on Linux). Right-click its icon to open ArchLens, stop or start MCP for your coding agents, or quit. **Settings → Desktop app** turns this off.
- **Stop MCP** makes ArchLens refuse your coding agents' tool calls until you choose **Start MCP**, without changing their settings.
- Settings opens over the page, with its sections in a sidebar, a search box, and an **About** section.

## 0.2.0

- ArchLens updates itself. It looks for a new version shortly after it starts and every few hours, and asks before it downloads one and before it restarts to install it. **Help → Check for Updates** looks right away. This works for the Windows installer, the AppImage and the `.deb`. Version 0.1.0 cannot update itself: install 0.2.0 over it once.
- **Settings → Coding agents** shows whether Codex and Claude Code are connected to ArchLens, explains each state in a sentence, and offers the one action that fits: Connect, Update, Test connection or Disconnect.

## 0.1.0

The first release, for Windows and Linux.

- Explore software systems at every level of detail, from the whole system down to one function call, and play scenarios step by step.
- Architecture, sequence and execution views of the same story.
- Create visualizations with Codex or Claude Code, from the app or from the coding agent you already use.
- Share a visualization as a `.zip` package, or as a link that opens at [archlens.net](https://archlens.net).
- Two example visualizations to start from.
