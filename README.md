# Real-Time PHP Chat Room

A modern, real-time multi-room chat application built with PHP, MySQL, and WebSockets (Ratchet). Features user authentication, chat rooms, message history, and a responsive UI.

## Features
- **Real-time Messaging:** Instant message delivery using WebSockets (Ratchet PHP)
- **Chat Rooms:** Users can join/leave public chat rooms
- **Message History:** See past messages when joining a room
- **User List:** View active users in each room
- **Authentication:** Register/login with email and password (secure, hashed)
- **Responsive UI:** Clean, mobile-friendly interface
- **Typing Indicator:** (Optional) See when others are typing
- **Desktop Notifications:** (Optional) Get notified of new messages
- **Message Timestamps:** Every message shows when it was sent
- **Security:** XSS prevention in chat messages

## Database Structure
See `chatroom.sql` for full schema. Main tables:
- `users` (id, username, email, password, created_at)
- `chat_rooms` (id, name, description, created_at)
- `messages` (id, room_id, user_id, message_text, timestamp)

## Setup Instructions

### 1. Prerequisites
- PHP 7.4+
- MySQL
- Composer (for PHP dependencies)
- Node.js (optional, for frontend tooling)
- XAMPP/WAMP/LAMP recommended for local development

### 2. Clone the Repository
```
git clone <repo-url>
cd chatRoom
```

### 3. Install PHP Dependencies
```
composer install
```

### 4. Set Up the Database
- Create a MySQL database (e.g., `chatroom`)
- Import `chatroom.sql` using phpMyAdmin or the MySQL CLI

### 5. Configure Database Connection
- Edit `db.php` with your MySQL credentials if needed

### 6. Start the WebSocket Server
```
php websocket-server.php
```

### 7. Run the Application
- Start Apache/MySQL via XAMPP
- Visit [http://localhost/chatRoom/](http://localhost/chatRoom/) in your browser

## Usage
- Register or log in
- Join a chat room or create a new one
- Start chatting in real time!

## Security Notes
- All user input is sanitized to prevent XSS
- Passwords are securely hashed

## License
MIT 