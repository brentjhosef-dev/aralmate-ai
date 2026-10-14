# AralMate AI — Live AI Edition

Your original purple AralMate interface now uses a server-side OpenAI API connection for Study Notes, AI Tutor, and Quiz Generator. Dashboard, notes, and quiz scores are saved locally in the browser.

## Run locally

1. Install Node.js 20 or newer.
2. Open a terminal in this folder.
3. Create an OpenAI API key at https://platform.openai.com/api-keys and ensure the API account has available billing/credits. ChatGPT subscriptions do not automatically include API credits.
4. Set the key as an environment variable. **Never place the key inside index.html or commit it to a repository.**

   macOS / Linux:
   ```bash
   export OPENAI_API_KEY="your_key_here"
   npm start
   ```

   Windows PowerShell:
   ```powershell
   $env:OPENAI_API_KEY="your_key_here"
   npm start
   ```

5. Open http://localhost:3000 in your browser.

Optional: set `OPENAI_MODEL` to an API model available to your account. `.env.example` is a template; the server reads environment variables directly, not `.env` files automatically.

## Deploy

Deploy as a Node.js web service on a hosting platform that supports Node 20+. Set `OPENAI_API_KEY` in the host's **secret environment variables**, set start command `npm start`, and use the platform's supplied `PORT`. Do not deploy `public/index.html` alone: the `/api/ai` server route is required.

## Notes

- AI API calls incur usage costs.
- A basic per-IP request limit is included, but production use should add authentication, account-level quotas, and durable rate limiting.
- Notes and quiz scores currently use browser localStorage, not cloud sync.
- This project supports pasted text, not document uploads yet.
- Avoid entering confidential personal information into prompts unless you have reviewed your data practices.
