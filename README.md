# Career-forge
CareerForge is a modern career-focused web platform designed to help students build skills, showcase their projects, prove their abilities, and prepare for career opportunities. Built with modern web technologies and AI-assisted development, the project focuses on practical skill development, portfolio building, and career growth.

CareerForge — Deployment Guide (V12)
This folder contains the complete CareerForge front-end: 17 self-contained HTML files (16 pages + a 404 page). Each file has its logo and fonts embedded, so there are no separate image or asset folders to keep track of — you can drag-and-drop this whole folder onto most static hosts and it will work immediately.
What's in this package
File
Page
index.html
Homepage
login.html
Log in
signup.html
Sign up
onboarding.html
5-step account setup
dashboard.html
Main dashboard (after login)
profile.html
User profile
career-path.html
Career path detail
skills.html
Skills management
roadmap.html
Interactive roadmap
projects.html
Project listing
project-detail.html
Single project detail
proof-vault.html
Evidence/proof tracker
resume.html
Resume builder
portfolio.html
Portfolio builder
opportunities.html
Opportunity tracker
forgeai.html
AI assistant (demo UI)
404.html
Not-found page
Important — this is a front-end-only build. There is no database or server yet. Every page uses realistic demo data (the "Alex Kumar" example) so the product can be reviewed and clicked through, but nothing is actually saved between visits or between pages. See careerforge-backend-architecture.md (from V10) for what a real backend needs to look like.
Option 1: Netlify (easiest, free, recommended)
Go to app.netlify.com/drop
Drag this entire folder onto the page
Netlify gives you a live URL immediately (e.g. random-name-123.netlify.app)
To use your own domain later: Site settings → Domain management → Add custom domain
No account is required for the first deploy, but creating a free account lets you update the site later instead of only ever getting a new random URL.
Option 2: Vercel
Go to vercel.com and sign up (free)
Click Add New → Project → Deploy without Git (or drag the folder in if offered)
Vercel auto-detects it as a static site and deploys it
Option 3: GitHub Pages (free, good if you already use GitHub)
Create a new GitHub repository
Upload all files in this folder to the repository root
Go to Settings → Pages
Under "Source," select the main branch and / (root) folder
GitHub gives you a URL like yourusername.github.io/repo-name
Note: with GitHub Pages, your homepage must be named index.html (it already is) for the root URL to work automatically.
Option 4: Any basic web host / shared hosting
Since every file is plain HTML/CSS/JS with no build step:
Upload all files via FTP or your host's file manager into the public_html (or equivalent) folder
Make sure index.html stays at the root so it loads as the homepage
Done — no server configuration, no Node.js, no database needed for this stage
Before sharing the live link publicly
A few things worth checking once it's live:
Click through every sidebar link on a logged-in page (dashboard → skills → roadmap → etc.) to confirm they still resolve correctly on the live URL
Test on an actual phone, not just a resized browser window
Decide whether you want search engines to index this yet — if not, add a robots.txt file with Disallow: / until the backend is ready
Remember: login/signup forms don't actually create accounts yet (no backend) — anyone who submits them will be redirected to the dashboard with the same demo data, not their own account
What comes after deployment
Per the V10 architecture document, the next real milestone is connecting a backend (auth, database, file storage) so that:
Signup/login actually create and check real accounts
Skills, proof items, and project progress persist per user
The Resume/Portfolio "Download" and "Publish" buttons produce real output instead of demo alerts
ForgeAI connects to a real AI model instead of canned responses
Until then, this deployment is best used for design review, user testing, and stakeholder demos — not as a live product accepting real signups.