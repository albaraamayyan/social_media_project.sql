# Social Media Database & Core Backend Logic (X / Twitter Simulation) 🚀🐦

An advanced relational database architecture simulating core production systems behind microblogging platforms like X (Twitter). Designed to handle complex entity relationships, security hashing, and automated backend business logic via SQL.

## 🏗️ Architecture & Core Schema
1. **Relational Entities:**
   - `users`: Core account registry with automated timestamping and binary password protection.
   - `profiles`: Extended user profile metadata linked via a strict `One-to-One` constraint.
   - `tweets`: Content publication engine linked via `One-to-Many` relational mapping.
   - `follows`: Self-referencing network graph implementing `Many-to-Many` user connectivity.
   - `likes`: Interaction tracking table bridging users and tweets (`Many-to-Many`).

2. **Advanced Stored Procedures:**
   - `createAccount`: Transactional routine automating secure user onboarding, profile initialization, and `MD5` / `BINARY(64)` cryptographic password hashing.
   - `User_Follow`: Dynamic relational linker resolving human-readable usernames into sequential database primary keys to establish secure follows.

---

## 💻 Quick Setup & Execution
1. Execute the `social_media_project.sql` script inside your MySQL management environment.
2. Register a new user profile via the procedure:
   ```sql
   CALL createAccount('fahad_dev', 'fahad@tech.sa', 'SecurePass123', 'Software Engineer', 'avatar.png');
