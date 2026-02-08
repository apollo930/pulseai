# 🚀 Quick Deployment Guide - Get Live in 15 Minutes

## 🎯 Goal
Get Pulse Moment deployed and accessible via public URL before the hackathon demo.

---

## Option 1: Demo Mode (No APIs) - 2 Minutes ⚡

**Best for:** Quick testing, initial presentation without API costs

### Steps:
1. Open `index.html` in a browser
2. That's it! The demo mode uses simulated AI responses

### Pros:
- Zero setup
- No API costs
- Works offline
- Instant gratification

### Cons:
- Not "real" AI processing
- Can't show actual API calls
- Judges may question authenticity

---

## Option 2: Vercel Deployment (With APIs) - 15 Minutes ⭐ RECOMMENDED

**Best for:** Winning the hackathon with a real, deployed product

### Prerequisites:
- GitHub account
- Vercel account (free tier works)
- API keys ready (see below)

### Step-by-Step:

#### 1. Get API Keys (5 minutes)

**Gemini API (Free tier: 1500 requests/day)**
- Go to https://makersuite.google.com/app/apikey
- Click "Create API Key"
- Copy key

**Groq API (Free tier: 14,400 requests/day)**
- Go to https://console.groq.com/keys
- Sign up with Google
- Click "Create API Key"
- Copy key

**Fal.ai API (Free tier: $5 credit)**
- Go to https://fal.ai/dashboard
- Sign up
- Click "API Keys" → "Create Key"
- Copy key

#### 2. Push to GitHub (3 minutes)

```bash
# In your project directory
git init
git add .
git commit -m "Initial commit - Pulse Moment"

# Create GitHub repo and push
git remote add origin https://github.com/YOUR_USERNAME/pulse-moment.git
git push -u origin main
```

#### 3. Deploy to Vercel (5 minutes)

**Via Web UI (Easiest):**
1. Go to https://vercel.com
2. Click "Import Project"
3. Select your GitHub repo
4. Click "Import"
5. Add Environment Variables:
   - `GOOGLE_AI_API_KEY` = [your Gemini key]
   - `GROQ_API_KEY` = [your Groq key]
   - `FAL_API_KEY` = [your Fal key]
6. Click "Deploy"
7. Wait 2 minutes
8. Get your public URL: `https://pulse-moment.vercel.app`

**Via CLI (Faster if you know it):**
```bash
npm install -g vercel
vercel login
vercel

# Add environment variables when prompted
# Or add them later in Vercel dashboard
```

#### 4. Test Deployment (2 minutes)

1. Open your Vercel URL
2. Click "Start Monitoring"
3. Click "Manual Check"
4. Verify event detection works
5. Check that content generates

**If something breaks:**
- Check Vercel function logs
- Verify API keys are correct
- Ensure billing is enabled on API accounts

---

## Option 3: Local Development (For Testing) - 5 Minutes

### Setup:
```bash
cd pulse-moment

# Install dependencies
npm install

# Create .env.local file
cp .env.example .env.local

# Add your API keys to .env.local
nano .env.local

# Run development server
npm run dev

# Open http://localhost:3000
```

### Pros:
- Test everything locally first
- Easier debugging
- Faster iteration

### Cons:
- Not publicly accessible (judges can't test)
- Need to deploy anyway for demo

---

## 🔧 Troubleshooting

### "API key invalid"
- Double-check you copied the full key
- Ensure no trailing spaces
- Verify billing is enabled (some APIs require it)

### "Function timeout"
- Increase timeout in `vercel.json` (max 30s on free tier)
- Optimize API calls to be faster
- Use caching for repeated requests

### "Deployment failed"
- Check build logs in Vercel dashboard
- Verify `package.json` has all dependencies
- Ensure Next.js version is compatible

### "Can't access deployment URL"
- Wait 2-3 minutes after deploy (DNS propagation)
- Try incognito mode
- Check Vercel status page

---

## 📋 Pre-Demo Checklist

**1 Hour Before Pitching:**
- [ ] Deployment URL is accessible
- [ ] All API keys have remaining credits
- [ ] Test event detection with sample clip
- [ ] Verify content generation works
- [ ] Check social posting simulation
- [ ] Clear old events for clean demo
- [ ] Load YouTube demo clip in separate tab
- [ ] Take screenshots of successful run (backup)
- [ ] Have screen recording ready (backup backup)

**15 Minutes Before:**
- [ ] Open dashboard on presentation computer
- [ ] Test internet connection
- [ ] Verify APIs are responding
- [ ] Run through demo flow once
- [ ] Have backup video queued

**During Demo:**
- [ ] Show URL immediately
- [ ] Point to latency metrics
- [ ] Explain AI thinking process
- [ ] Show multiple business types if time
- [ ] End with "Try it yourself"

---

## 💡 Pro Tips

### Speed Optimization
- Use Vercel Edge Functions (faster than serverless)
- Cache event detection for 5 seconds (avoid duplicate API calls)
- Pre-warm Flux API by calling once before demo
- Use smaller Gemini model (Flash vs Pro) for speed

### Cost Optimization
- Gemini Flash: ~$0.0001/frame
- Groq DeepSeek: ~$0.0001/request
- Flux: ~$0.05/image
- **Total per event: ~$0.06**

### Reliability
- Always have backup demo video
- Test with multiple Super Bowl clips
- Verify on different networks
- Have mobile hotspot ready

### Presentation
- Use big screen for judges to see
- Zoom in on latency numbers
- Point to AI log in real-time
- Show generated content immediately

---

## 🆘 Emergency Backup Plan

**If deployment fails:**
1. Show demo mode (index.html)
2. Explain "this is the working version"
3. Show architecture slides
4. Promise to fix deployment for judges to test
5. Have team member fix it during other pitches

**If APIs fail:**
1. Use backup screen recording
2. Say "let me show you a successful run from this morning"
3. Explain architecture anyway
4. Show code to prove it's real

**If demo computer fails:**
1. Use phone to show deployment
2. Have teammate present from their computer
3. Show slides only and promise demo after

---

## 🎯 Success Criteria

### Minimum Viable Demo
- [ ] Public URL works
- [ ] Event detection shows result
- [ ] Strategy generates
- [ ] Visual appears
- [ ] Latency < 45 seconds

### Ideal Demo
- [ ] Everything above PLUS:
- [ ] Multiple event types shown
- [ ] Different business types demonstrated
- [ ] One-click posting works
- [ ] Latency < 30 seconds
- [ ] Judges can test themselves

---

## 📞 Last-Minute Help

**Vercel Issues:**
- Vercel Status: https://vercel-status.com
- Discord: https://vercel.com/discord

**API Issues:**
- Gemini Support: https://ai.google.dev/docs
- Groq Discord: https://discord.gg/groq
- Fal Support: https://fal.ai/docs

**General:**
- Your team
- Hackathon organizers
- Stack Overflow

---

## ✅ Final Check

Before you pitch:
```bash
# Test the full flow
curl -X POST https://your-url.vercel.app/api/detect-event \
  -H "Content-Type: application/json" \
  -d '{"frameData": "test"}'

# Should return JSON with event data
```

If that works, you're ready to win. 🏆

---

**Remember:** A deployed, working product beats a perfect slide deck every time.

**Deploy early, test often, win big.**
