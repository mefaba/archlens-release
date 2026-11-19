# Changelog

## 0.5.0

- Create visualizations with **Antigravity CLI** (`agy`), Google's coding agent, as well as Codex and Claude Code, using the sign-in you already have. Each job gets settings for that session only: its terminal commands run in Antigravity's sandbox, your repositories can be read but not changed, and web pages, the browser and MCP tools are turned off. Antigravity's web search cannot be turned off.
- **Settings → Coding agents** connects Antigravity CLI too, so it can make ArchLens visualizations from any repository you work in.

## 0.4.0

- **Visualizations**, **Create**, and **Components** share the same navigation and keep Settings and the theme switch in reach. In the viewer, Settings and Components are also available from the sidebar. The desktop app supports **Back** and **Forward** from the View menu, keyboard shortcuts, and mouse side buttons.
- On phones, the diagram fills the screen and the sidebar and inspector open over it. The timeline keeps playback and speed controls within reach. The inspector has its own close button, and the Share menu stays inside the viewport.
- On Windows, the title bar follows the app theme and shows the current page title alongside the app menu and native window controls.
- Desktop updates show up on the home page with download progress and a **Restart to update** button. **Settings → About** shows release notes and update errors. ArchLens asks before restarting if a visualization is still being created.
- The Windows installer now installs for the current user with one click. If you installed 0.3.0 or earlier for all users, uninstall that copy before installing 0.4.0. Your visualizations and settings are kept.
- During development, Vite ignores generated runtime files, desktop build output, and browser test reports so they no longer trigger reloads.

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
