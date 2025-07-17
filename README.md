### Connect Your Cloudflare Domain to GitHub Pages

You can easily use a custom domain from Cloudflare for your GitHub Pages website at no extra cost. This guide will walk you through the process, assuming you have an existing GitHub repository for your website that is already published on GitHub Pages. 

### **Step 1: Set Up Your Repository** 

First, ensure your website's files are in a GitHub repository. 

*   **Navigate to your repository:** Go to the repository containing your website's code. 
*   **Enable GitHub Pages:** 
    *   Click on the "Settings" tab in your repository.
    *   In the left-hand menu, select "Pages".
    *   Under "Custom Domain", type your custom domain (e.g., `www.yourdomain.com`) and click "Save".

### **Step 2: Configure DNS Settings in Cloudflare** 

Next, you'll need to configure your domain's DNS settings in your Cloudflare account. 

*   **Log in to Cloudflare:** Access your Cloudflare account. 
*   **Select your domain:** Choose the domain you wish to configure. 
*   **Add DNS records:** 
    *   Navigate to the "DNS" tab.
    *   You'll need to add `A` records and a `CNAME` record. 
    *   **A Records:** Create four `A` records. For each, set the "Name" to `@` and enter one of the following IP addresses in the "IPv4 address" field. 
        *   185.199.108.153 
        *   185.199.109.153 
        *   185.199.110.153 
        *   185.199.111.153 
    *   **CNAME Record:** Create a `CNAME` record. 
        *   **Name:** `www` 
        *   **Target:** your-username.github.io. 
    *   **Save your changes.** 

### **Step 3: Verify DNS Propagation** 

It may take some time for the DNS changes to take effect. You can check the status by visiting both `http://yourdomain.com` and `http://www.yourdomain.com`. 

**Important Note:** It is recommended to turn off the "Proxy status" (grey-cloud) for your DNS records in Cloudflare initially. GitHub Pages may have trouble generating an SSL certificate if the records are proxied. You can re-enable the proxy after the certificate has been issued. 

### **Additional Tips** 

*   If you encounter any issues, try clearing your browser's cache or using an incognito window, as old DNS settings can sometimes be cached. 
*   Forcing HTTPS on your GitHub Pages site is recommended for security.
