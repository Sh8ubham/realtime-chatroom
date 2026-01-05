# 🔒 Private Chatroom

A secure, self-destructing real-time chat application built with Next.js, Redis, and WebSockets. Messages disappear after a set time limit, ensuring private conversations stay private.


## ✨ Features

- 🚀 **Real-time messaging** - Instant message delivery using WebSockets
- ⏱️ **Self-destructing rooms** - Automatic room deletion after 10 minutes
- 🔐 **Anonymous usernames** - Auto-generated anonymous identities
- 📱 **Responsive design** - Works seamlessly on desktop and mobile
- 🎨 **Modern UI** - Sleek, terminal-inspired interface
- 💾 **Redis-powered** - Fast, reliable message storage
- 🔗 **Shareable room links** - Easy collaboration with one-click copy

## 🛠️ Tech Stack

- **Frontend:** Next.js 16, React, TypeScript
- **Styling:** TailwindCSS
- **Backend:** Next.js API Routes, Elysia
- **Database:** Redis (Upstash)
- **Real-time:** WebSockets
- **State Management:** TanStack Query (React Query)
- **Validation:** Zod

## 📋 Prerequisites

Before you begin, ensure you have:

- Node.js 18+ installed
- A Redis database (recommend [Upstash](https://upstash.com) for free tier)
- npm or bun package manager

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/realtime-chatroom.git
cd realtime-chatroom
```

### 2. Install dependencies

```bash
npm install
# or
bun install
```

### 3. Set up environment variables

Create a `.env.local` file in the root directory:

```env
REDIS_URL=your_redis_url_here
REDIS_TOKEN=your_redis_token_here
NODE_ENV=development
```

**Getting Redis credentials:**
1. Sign up at [Upstash](https://upstash.com)
2. Create a new Redis database
3. Copy the `UPSTASH_REDIS_REST_URL` and `UPSTASH_REDIS_REST_TOKEN`
4. Paste them as `REDIS_URL` and `REDIS_TOKEN`

### 4. Run the development server

```bash
npm run dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📁 Project Structure

```
realtime-chatroom/
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   └── [[...slugs]]/
│   │   │       └── route.ts          # API routes (Elysia)
│   │   ├── room/
│   │   │   └── [roomId]/
│   │   │       └── page.tsx          # Chat room page
│   │   ├── layout.tsx                # Root layout
│   │   ├── page.tsx                  # Home page
│   │   └── globals.css               # Global styles
│   ├── components/
│   │   └── providers.tsx             # React Query provider
│   ├── hooks/
│   │   └── use-username.ts           # Username hook
│   ├── lib/
│   │   ├── client.ts                 # API client
│   │   ├── realtime.ts               # Realtime server logic
│   │   ├── realtime-client.ts        # Realtime client hook
│   │   └── redis.ts                  # Redis connection
│   └── middleware.ts                 # Next.js middleware
├── public/                           # Static assets
├── .env.local                        # Environment variables (create this)
├── next.config.mjs                   # Next.js config
├── tailwind.config.ts                # Tailwind config
├── tsconfig.json                     # TypeScript config
└── package.json                      # Dependencies
```

## 🎯 Usage

### Creating a Room

1. Visit the homepage
2. Your anonymous username is auto-generated
3. Click **"CREATE SECURE ROOM"**
4. You'll be redirected to your new chat room

### Sharing a Room

1. Click the **"COPY"** button next to the Room ID
2. Share the link with others
3. Anyone with the link can join and chat

### Sending Messages

1. Type your message in the input field
2. Press **Enter** or click **"SEND"**
3. Messages appear instantly for all users in the room

### Self-Destruct Timer

- Each room has a **10-minute** countdown timer
- Timer shows in the header (turns red when < 1 minute)
- Click **"DESTROY NOW"** to manually delete the room
- When time expires, the room and all messages are permanently deleted

## 🔧 Configuration

### Adjust Room TTL (Time-to-Live)

Edit `src/app/api/[[...slugs]]/route.ts`:

```typescript
const ROOM_TTL_SECONDS = 60 * 10  // Change this value (currently 10 minutes)
```

### Customize Anonymous Names

Edit `src/app/page.tsx`:

```typescript
const ANIMALS = ["wolf", "hawk", "bear", "shark"]  // Add more animals
```

## 🚀 Deployment

### Deploy to Vercel (Recommended)

1. Push your code to GitHub
2. Visit [vercel.com](https://vercel.com)
3. Import your repository
4. Add environment variables:
   - `REDIS_URL`
   - `REDIS_TOKEN`
   - `NODE_ENV=production`
5. Click Deploy

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)

### Deploy to Netlify

1. Connect your GitHub repo
2. Build command: `npm run build`
3. Publish directory: `.next`
4. Add environment variables
5. Deploy

### Deploy to Railway

1. Create new project from GitHub
2. Railway auto-detects Next.js
3. Add environment variables
4. Deploy

## 🧪 Testing

```bash
# Run linting
npm run lint

# Type checking
npm run type-check
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🐛 Known Issues

- Messages are not end-to-end encrypted (only transport layer security)
- No message history persistence after room deletion
- Limited to text messages only (no file uploads)

## 🗺️ Roadmap

- [ ] End-to-end encryption
- [ ] File/image sharing
- [ ] Custom room passwords
- [ ] Adjustable TTL per room
- [ ] Message reactions
- [ ] Typing indicators
- [ ] User presence indicators

## 📧 Contact

Created by [@yourusername](https://github.com/yourusername)

Project Link: [https://github.com/yourusername/realtime-chatroom](https://github.com/yourusername/realtime-chatroom)

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org/) - The React framework
- [Upstash](https://upstash.com/) - Serverless Redis
- [TailwindCSS](https://tailwindcss.com/) - Utility-first CSS
- [Elysia](https://elysiajs.com/) - Fast web framework
- [TanStack Query](https://tanstack.com/query) - Data fetching

---

⭐ If you found this project helpful, please give it a star!
