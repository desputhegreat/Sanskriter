# Sanskrit Study Guide Generator

## Deploy to Vercel (free, 2 minutes)

### Step 1 — Push to GitHub
1. Create a new repo on github.com
2. Upload all these files keeping the folder structure:
   ```
   api/proxy.js
   public/index.html
   vercel.json
   ```

### Step 2 — Deploy on Vercel
1. Go to vercel.com → sign in with GitHub
2. Click "Add New Project" → import your repo
3. Leave all settings as default → click "Deploy"

### Step 3 — Add your API key
1. In your Vercel project → go to Settings → Environment Variables
2. Add:
   - Name: `ANTHROPIC_API_KEY`
   - Value: your key from console.anthropic.com
3. Go to Deployments → click the 3 dots on latest deploy → "Redeploy"

Done! Your site URL will be something like `https://your-project.vercel.app`

## Why this works
The browser can't call the Anthropic API directly (CORS restriction).
`api/proxy.js` is a serverless function that runs on Vercel's servers,
where CORS doesn't apply. Your API key stays secret on the server side too.
