# Deployment Instructions

This website can be deployed using either Cloudflare Pages or Vercel with automatic GitHub integration.

## Option 1: Cloudflare Pages (Current Setup)

The GitHub Actions workflow (`.github/workflows/deploy-to-cloudflare.yml`) will automatically deploy to Cloudflare Pages when you push commits to the `main` branch.

### Setup Required:
1. Get your Cloudflare API Token:
   - Log in to your Cloudflare dashboard
   - Go to Profile > API Tokens
   - Create a new token with "Cloudflare Pages" permissions

2. Get your Cloudflare Account ID:
   - Available in your Cloudflare dashboard URL or account settings

3. Add GitHub Secrets to your repository:
   - Go to GitHub repository Settings > Secrets and Variables > Actions
   - Create `CLOUDFLARE_API_TOKEN` secret with your API token
   - Create `CLOUDFLARE_ACCOUNT_ID` secret with your account ID

4. The workflow will automatically trigger on every push to `main` branch

## Option 2: Vercel (Recommended for Automatic Deployment)

Vercel offers simpler GitHub integration with no credentials needed.

### Setup:
1. Go to https://vercel.com/dashboard
2. Click "Add New..." > "Project"
3. Select "Import Git Repository"
4. Choose `jr851/leo-reeve-website` repository
5. Vercel will automatically detect the configuration from `vercel.json`
6. Click "Deploy"

After setup, every push to the `main` branch will automatically deploy to Vercel.

### Domain Configuration:
- After deploying to Vercel, update your DNS to point `leoreeve.com` to Vercel's servers
- Or use Vercel's free subdomain (`leo-reeve-website.vercel.app`)

## File Structure

- `index.html` - Main personal website
- `coaching.html` - Comprehensive athletics coaching resource (1194 lines with 14 events)
- `vercel.json` - Vercel deployment configuration
- `.github/workflows/deploy-to-cloudflare.yml` - GitHub Actions workflow for Cloudflare deployment

## Current Status

- ✓ Both `index.html` and `coaching.html` are in the GitHub repository
- ✓ Website is live at https://leoreeve.com
- ⚠️ Cloudflare Pages automatic deployment not yet active (requires API token setup)
- → Choose Option 1 or Option 2 above to enable automatic deployments
