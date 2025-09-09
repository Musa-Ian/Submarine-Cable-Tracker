# 🚀 Deployment Guide

## Vercel Deployment (Recommended)

### Option 1: One-Click Deploy

1. **Push to GitHub** (if not already):
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Submarine Cable Tracker"
   git branch -M main
   git remote add origin https://github.com/yourusername/submarine-cable-tracker.git
   git push -u origin main
   ```

2. **Deploy with Vercel**:
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your GitHub repository
   - Vercel will auto-detect the configuration

### Option 2: CLI Deploy

1. **Install Vercel CLI**:
   ```bash
   npm install -g vercel
   ```

2. **Login**:
   ```bash
   vercel login
   ```

3. **Deploy**:
   ```bash
   cd "/Users/ianmusa/Desktop/Submarine Cable Tracker"
   vercel --prod
   ```

4. **Follow prompts**:
   - Set up and deploy? `Y`
   - Which scope? Choose your account
   - Link to existing project? `N`
   - Project name: `submarine-cable-tracker`
   - Directory: `./` (current directory)

### Environment Variables Setup

After deployment, add your Mapbox token:

1. Go to your Vercel dashboard
2. Select your project
3. Go to **Settings** → **Environment Variables**
4. Add:
   - **Name**: `MAPBOX_TOKEN`
   - **Value**: `pk.eyJ1IjoiaWFubXVzYSIsImEiOiJjbWJ4aWM2cDExZDExMmpxM3RlOW9oeHY1In0.49j5NWnRfBOLdx_yhKO1YQ`
   - **Environment**: All (Production, Preview, Development)

5. **Redeploy** to apply changes:
   ```bash
   vercel --prod
   ```

## Alternative Deployment Options

### Netlify

1. **Drag and Drop**:
   - Zip the project folder
   - Go to [netlify.com](https://netlify.com)
   - Drag the zip file to deploy

2. **Environment Variables**:
   - Site Settings → Environment Variables
   - Add `MAPBOX_TOKEN`

### GitHub Pages

1. **Enable GitHub Pages**:
   - Repository Settings → Pages
   - Source: Deploy from a branch
   - Branch: main / (root)

2. **Note**: GitHub Pages doesn't support environment variables, so the token will be visible in the source code.

### Other Static Hosts

The app works on any static hosting service:
- **Firebase Hosting**
- **Surge.sh**
- **AWS S3 + CloudFront**
- **Azure Static Web Apps**

## Post-Deployment Checklist

✅ **Verify the following after deployment**:

1. **Map loads correctly** - Mapbox token is working
2. **Cables display** - TeleGeography API is accessible
3. **Country selection works** - Dropdowns are functional
4. **Traceroute simulation runs** - No JavaScript errors
5. **Mobile responsive** - Test on different screen sizes
6. **HTTPS enabled** - Secure connection for API calls

## Troubleshooting

### Common Issues

1. **Map doesn't load**:
   - Check Mapbox token in environment variables
   - Verify token has correct permissions

2. **CORS errors with cable data**:
   - TeleGeography API should allow cross-origin requests
   - Check browser console for specific errors

3. **Vercel build fails**:
   - Ensure `vercel.json` is in root directory
   - Check all file paths are correct

### Debug Commands

```bash
# Check Vercel deployment logs
vercel logs

# List environment variables
vercel env ls

# Pull environment variables locally
vercel env pull .env.local
```

## Domain Setup (Optional)

1. **Custom Domain**:
   - Vercel Dashboard → Domains
   - Add your domain
   - Configure DNS as instructed

2. **SSL Certificate**:
   - Automatic with Vercel
   - No additional configuration needed

## Performance Optimization

The app is already optimized for production:
- ✅ Minified assets via CDN
- ✅ Gzip compression (Vercel default)
- ✅ HTTP/2 support
- ✅ Global CDN distribution
- ✅ Efficient API caching

## Monitoring

Track your deployment:
- **Vercel Analytics** - Built-in performance monitoring
- **Vercel Speed Insights** - Core Web Vitals
- **Browser Console** - Check for JavaScript errors

Your submarine cable tracker is now ready for the world! 🌍