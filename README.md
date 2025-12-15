
# Project — Rick And Morty

Full-stack application inspired by the "Rick and Morty" series that allows searching, viewing and managing characters. The project is split into two main parts: the frontend (folder `Client`) and the backend (folder `Server`).

### Architecture — Frontend (Client)
- #### Main stack: React with Vite for fast bundling and development.
- #### Folder structure:
  - `src/components`: reusable components (Cards, Card, Detail, Favorites, Form, Nav, SearchBar, etc.).
  - `src/redux`: global state logic (actions, types and reducer).
  - `src/assets` and `public`: static resources.
  - `src/main.jsx` and `src/App.jsx`: entry point and root component.
- #### State & flow: 
Redux is used for global state (character list, favorites, partial auth). Components dispatch actions and read state via selectors to update the UI.
- #### Backend communication:
 The frontend makes HTTP requests (fetch/axios) to server routes to fetch characters, authenticate and manage favorites.

### Architecture — Backend (Server)
- #### Main stack: Node.js with Express exposing a lightweight REST API.
- #### Folder structure:
  - `src/controllers`: endpoint logic (`getCharById.js`, `handleFavorites.js`, `login.js`).
  - `src/routes`: route definitions and controller mounting.
  - `src/utils`: utilities and sample data (`data.js`, `users.js`).
  - `src/index.js` / `src/app.js`: server initialization and middleware configuration.
- #### Typical endpoints:
  - Get character by id (controller `getCharById`).
  - Favorites management (add/remove via `handleFavorites`).
  - Basic authentication (controller `login`).
- #### Persistence:
The current structure uses in-memory utilities/data (`utils/data.js`, `utils/users.js`) suitable for development; these can be replaced with a real database if needed.

### Front↔Back Communication
- The frontend consumes the backend REST API via routes exposed in `Server/src/routes`.
- Main operations include character search, favorites management and authentication.

