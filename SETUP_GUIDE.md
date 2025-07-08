# README Profile Enhancement Setup Guide

This document explains how to set up and configure the new features added to your GitHub profile README.

## 🚀 New Features Added

### 1. Enhanced Tech Stack Icons
- **Fixed Laravel icon**: Changed from simple-icons to devicons for better reliability
- **Added Flask icon**: Now properly displays using devicons
- **Added React**: Moved to main tech stack as mentioned in About Me
- **Added PHP and TypeScript**: Essential technologies for your stack
- **Enhanced "Also familiar with"**: Added Node.js, MySQL, PostgreSQL, Nginx, Ubuntu

### 2. Blog Posts Integration
- **Medium/Dev.to Integration**: Automatically fetches and displays your latest blog posts
- **GitHub Action**: Runs daily at 8 AM UTC to update blog posts
- **Customizable**: Easy to modify the RSS feed URLs

### 3. WakaTime Coding Activity
- **Time Tracking**: Shows your coding activity and language usage
- **GitHub Action**: Updates daily with your coding statistics
- **Detailed Stats**: Languages, editors, operating systems, and projects

### 4. Enhanced Social Media
- **Medium**: Direct link to your Medium profile
- **Dev.to**: Link to your Dev.to profile  
- **Twitter**: Professional Twitter connection
- **LinkedIn**: Existing connection maintained

### 5. Improved GitHub Stats
- **GitHub Streak**: Shows your commit streak
- **Activity Graph**: Visual representation of your GitHub activity
- **Better Layout**: Centered and organized presentation

## ⚙️ Setup Requirements

### For Blog Posts Integration
1. **Medium RSS Feed**: 
   - Update the feed URL in `.github/workflows/blog-posts.yml`
   - Change `https://medium.com/feed/@arturict` to your actual Medium username
   
2. **Dev.to RSS Feed** (Optional):
   - Add your Dev.to feed: `https://dev.to/feed/yourusername`
   - Uncomment the combined feed line in the workflow

### For WakaTime Integration
1. **WakaTime Account**: Sign up at [wakatime.com](https://wakatime.com)
2. **API Key**: Get your API key from WakaTime dashboard
3. **GitHub Secrets**: Add the following secrets to your repository:
   - `WAKATIME_API_KEY`: Your WakaTime API key
   - `GH_TOKEN`: GitHub personal access token with repo permissions

### For Social Media Links
Update the URLs in the README.md "Connect with Me" section:
- Medium: `https://medium.com/@yourusername`
- Dev.to: `https://dev.to/yourusername`  
- Twitter: `https://twitter.com/yourusername`

## 🔧 Configuration

### Blog Posts Workflow
File: `.github/workflows/blog-posts.yml`
- **Schedule**: Daily at 8 AM UTC
- **Max Posts**: 5 (configurable)
- **Template**: Customizable post format

### WakaTime Workflow  
File: `.github/workflows/wakatime.yml`
- **Schedule**: Daily at midnight UTC
- **Features**: All stats enabled by default
- **Customization**: Modify the `with:` parameters

## 🎨 Customization Options

### Icons
All icons use devicons/devicon for consistency. To add more:
```html
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/TECHNOLOGY/TECHNOLOGY-original.svg" height="40" alt="Technology logo" />
```

### Themes
Current theme: `tokyonight`
Other options: `dark`, `radical`, `merko`, `gruvbox`, `onedark`, `cobalt`, `synthwave`, `highcontrast`, `dracula`

### Blog Post Template
Customize in `blog-posts.yml`:
```yaml
template: "- 📝 [$title]($url) - $description"
```

## 🚀 GitHub Actions Workflows

### Current Workflows
1. **Snake Game**: Updates GitHub contribution snake animation
2. **Blog Posts**: Fetches latest blog posts from Medium/Dev.to
3. **WakaTime**: Updates coding activity statistics

### Manual Triggers
All workflows can be manually triggered:
1. Go to Actions tab in your repository
2. Select the workflow
3. Click "Run workflow"

## 📝 Notes

- **First Run**: Blog posts and WakaTime sections will be empty until the first workflow run
- **Permissions**: Make sure GitHub Actions have write permissions to update README
- **Rate Limits**: Workflows respect API rate limits and run once daily
- **Fallbacks**: If external services are down, existing content remains unchanged

## 🔍 Troubleshooting

### Blog Posts Not Updating
- Check if Medium/Dev.to RSS feeds are accessible
- Verify GitHub Actions have write permissions
- Check workflow logs for errors

### WakaTime Not Working
- Ensure WAKATIME_API_KEY secret is set correctly
- Verify GH_TOKEN has proper permissions
- Check if WakaTime is tracking your coding activity

### Icons Not Loading
- All icons use reliable CDN sources (devicons/jsdelivr)
- If an icon fails, check if the technology name is correct in the URL
- Alternative: Use shields.io badges instead

## 📚 Resources

- [GitHub Profile README Generator](https://rahuldkjain.github.io/gh-profile-readme-generator/)
- [Devicons](https://devicon.dev/)
- [WakaTime](https://wakatime.com/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)