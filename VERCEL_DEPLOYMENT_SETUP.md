# GitHub Actions - Vercel Deployment Setup

This workflow automatically deploys your project to Vercel whenever you push commits to the `main` or `master` branch.

## Setup Instructions

### 1. Connect Your Repository to Vercel
- Go to [Vercel Dashboard](https://vercel.com/dashboard)
- Click "Import Project"
- Select your GitHub repository
- Follow the import wizard to connect your project

### 2. Get Your Vercel Credentials
You need three secrets from Vercel:

**VERCEL_TOKEN:**
- Go to [Vercel Settings > Tokens](https://vercel.com/account/tokens)
- Create a new token with appropriate scopes
- Copy the token value

**VERCEL_ORG_ID:**
- In Vercel Dashboard, go to Settings > General
- Copy your "Team ID" (for personal projects) or Organization ID

**VERCEL_PROJECT_ID:**
- In Vercel Dashboard, select your project
- Go to Settings > General
- Copy the "Project ID"

### 3. Add Secrets to GitHub
1. Go to your GitHub repository
2. Navigate to Settings > Secrets and variables > Actions
3. Click "New repository secret"
4. Add the following secrets:
   - Name: `VERCEL_TOKEN` → Value: (your Vercel token)
   - Name: `VERCEL_ORG_ID` → Value: (your Vercel org/team ID)
   - Name: `VERCEL_PROJECT_ID` → Value: (your Vercel project ID)

### 4. Push to GitHub
Once secrets are configured, any push to `main` or `master` branch will:
- Trigger the GitHub Action automatically
- Deploy your project to Vercel
- Update your live deployment

## How It Works
- **Trigger**: On every push to main/master branch
- **Action**: Uses Vercel's official GitHub Action
- **Deployment**: Automatically creates a production deployment on Vercel
- **Status**: Check workflow status in GitHub Actions tab

## Troubleshooting
If deployment fails:
1. Check GitHub Actions logs (Actions tab in your repository)
2. Verify all three secrets are correctly set
3. Ensure your Vercel account has an active project
4. Check that your repository is connected to Vercel
