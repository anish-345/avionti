# 🚀 Vercel Deployment Guide

This guide will help you deploy the PicToPDF website to Vercel using Git integration.

## 📋 Prerequisites

- Git repository (✅ Already initialized)
- GitHub/GitLab/Bitbucket account
- Vercel account (free tier available)

## 🔧 Step-by-Step Deployment

### 1. Push to GitHub

First, create a new repository on GitHub and push your code:

```bash
# Add GitHub remote (replace with your repository URL)
git remote add origin https://github.com/yourusername/pictopdf-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 2. Deploy to Vercel

#### Option A: Vercel Dashboard (Recommended)

1. **Go to Vercel**: Visit [vercel.com](https://vercel.com)
2. **Sign Up/Login**: Use your GitHub account for easy integration
3. **Import Project**: Click "New Project" → "Import Git Repository"
4. **Select Repository**: Choose your `pictopdf-website` repository
5. **Configure Project**:
   - **Project Name**: `pictopdf-website`
   - **Framework Preset**: Other (static site)
   - **Root Directory**: `./` (default)
   - **Build Command**: Leave empty (static site)
   - **Output Directory**: Leave empty (static site)
6. **Deploy**: Click "Deploy" button

#### Option B: Vercel CLI

```bash
# Install Vercel CLI
npm i -g vercel

# Login to Vercel
vercel login

# Deploy from project directory
vercel

# Follow the prompts:
# ? Set up and deploy "~/vercel"? [Y/n] y
# ? Which scope do you want to deploy to? [Your Account]
# ? Link to existing project? [y/N] n
# ? What's your project's name? pictopdf-website
# ? In which directory is your code located? ./
```

### 3. Custom Domain (Optional)

1. **Go to Project Settings**: In Vercel dashboard → Your Project → Settings
2. **Domains Tab**: Click "Domains"
3. **Add Domain**: Enter your custom domain (e.g., `pictopdf.com`)
4. **Configure DNS**: Update your domain's DNS settings:
   ```
   Type: CNAME
   Name: www (or @)
   Value: cname.vercel-dns.com
   ```

### 4. Environment Variables (If Needed)

If you need to add environment variables:

1. **Project Settings** → **Environment Variables**
2. **Add variables** like:
   - `GOOGLE_ANALYTICS_ID`
   - `CONTACT_EMAIL`

## 🔄 Automatic Deployments

Once connected to GitHub, Vercel will automatically:

- **Deploy on Push**: Every push to `main` branch triggers deployment
- **Preview Deployments**: Pull requests get preview URLs
- **Rollback**: Easy rollback to previous deployments

## 📊 Performance Optimization

Your `vercel.json` is already configured with:

- **Static File Caching**: Assets cached for 1 year
- **Security Headers**: XSS protection, content type sniffing prevention
- **Clean URLs**: Removes `.html` extensions
- **Redirects**: SEO-friendly URL redirects

## 🌐 Expected URLs

After deployment, your site will be available at:

- **Production**: `https://pictopdf-website.vercel.app`
- **Custom Domain**: `https://your-domain.com` (if configured)
- **Preview**: `https://pictopdf-website-git-branch.vercel.app` (for PRs)

## 📱 Mobile Testing

Test your deployed site on various devices:

- **Responsive Design Tester**: Use browser dev tools
- **Real Device Testing**: Test on actual mobile devices
- **Performance**: Check with Google PageSpeed Insights

## 🔍 Monitoring & Analytics

### Built-in Analytics
Vercel provides:
- **Page Views**: Traffic analytics
- **Performance**: Core Web Vitals
- **Geography**: Visitor locations

### Google Analytics (Optional)
Add Google Analytics by updating the HTML:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 🚨 Troubleshooting

### Common Issues

1. **Build Fails**:
   - Check `vercel.json` syntax
   - Ensure all files are committed

2. **Images Not Loading**:
   - Verify image paths are relative
   - Check file extensions match exactly

3. **Custom Domain Issues**:
   - Wait 24-48 hours for DNS propagation
   - Use DNS checker tools

4. **Performance Issues**:
   - Optimize images (use WebP format)
   - Minimize CSS/JS files
   - Enable compression

### Support Resources

- **Vercel Docs**: [vercel.com/docs](https://vercel.com/docs)
- **Community**: [github.com/vercel/vercel/discussions](https://github.com/vercel/vercel/discussions)
- **Status Page**: [vercel-status.com](https://vercel-status.com)

## 📈 Post-Deployment Checklist

- [ ] Test all pages and links
- [ ] Verify mobile responsiveness
- [ ] Check loading speed (< 3 seconds)
- [ ] Test contact forms (if any)
- [ ] Verify SEO meta tags
- [ ] Set up monitoring/analytics
- [ ] Test on different browsers
- [ ] Check accessibility compliance

## 🔄 Updates & Maintenance

To update your website:

1. **Make Changes**: Edit files locally
2. **Test Locally**: Serve and test changes
3. **Commit & Push**:
   ```bash
   git add .
   git commit -m "Update: description of changes"
   git push origin main
   ```
4. **Auto-Deploy**: Vercel automatically deploys changes

## 📞 Support

If you need help with deployment:

- **Email**: support@pictopdf.app
- **Documentation**: Check this README.md
- **Vercel Support**: Use Vercel's help center

---

**🎉 Your PicToPDF website is ready for the world!**

The site is optimized for:
- ⚡ Fast loading (< 2 seconds)
- 📱 Mobile-first design
- 🔍 SEO optimization
- 🔒 Security headers
- 🌍 Global CDN delivery