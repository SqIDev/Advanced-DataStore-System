--[[
SafeStore: A Robust DataStore Module for Roblox
SafeStore is a powerful wrapper for Roblox's DataStoreService designed to make saving and loading player data safe, reliable, and easy. It abstracts away the common pitfalls of data management, such as API errors, data loss from rapid re-joining (session locking), and manual saving, allowing you to focus on building your game.

Why Use SafeStore?
Working directly with DataStoreService can be risky. Without proper handling, you can face issues like:

Data loss due to unexpected API failures.

Item duplication or data overwrites when a player leaves and rejoins a different server quickly.

Losing significant progress if a server crashes.

Complex and messy code for handling player data.

SafeStore is designed to solve these problems with a simple, easy-to-use API.

Core Features
🔂 Automatic Retries: If a Roblox DataStore API call fails, SafeStore will automatically try again several times before reporting an error, overcoming most temporary service disruptions.

🔒 Session Locking: Prevents data corruption and duplication exploits. When a player joins a server, their data is "locked" to that session. If they attempt to join another server before the first session releases the lock, they will be kicked, ensuring data integrity.

💾 Data Caching: Player data is loaded once and cached on the server. All data interactions happen with this fast, local cache, drastically reducing the number of DataStore API calls and improving performance.

⏱️ Autosaving: SafeStore automatically saves a player's data periodically in the background. If a server crashes, players will only lose a few minutes of progress at most, instead of everything from their session.

📜 Data Versioning: You can define a version for your data structure. If a player joins with an older data version, you can write custom migration logic to update their data to the new structure without losing their progress. This is essential for long-term game updates.

📦 Default Data Template: Easily define a "starter pack" of data for all new players who join your game for the first time.

Installation
Create a ModuleScript in ServerScriptService.

Name it SafeStore.

Paste the module's code into the script.
--]]
