# /v/conspiracy Archive

This archive of the /v/conspiracy community on Voat preserves 42,505 posts and 159,856 comments from November 11, 2016 through December 25, 2020. It serves as an archive for the 43,913 users whose voices were silenced when Voat shut down on December 25, 2020.

---

## Repository Structure

```
voat-conspiracy-archive/
├── comments             # Directory containing comment index files
├── date                 # Directory containing date-related index files
├── favicon.ico          # Favicon for the archive site
├── index.html           # Main landing page for the archive
├── LICENSE              # Repository license
├── post.webp            # Associated image for the archive
├── README.md            # This README file
├── search.html          # Search page for the archive
├── static               # Directory containing static assets (CSS, JS)
└── v
    └── conspiracy       # Directory containing the post HTML pages for /v/conspiracy
```

### Static Assets Structure

```
static/
├── css
│   └── page.css         # Stylesheet for the archive
└── js
    ├── comments-toggle.js  # Script to toggle comments
    └── jquery-3.7.1.slim.min.js  # jQuery library
```

---

## Download Options

You can download this archive or clone the repository using one of the following methods:

### Clone via Git

```bash
git clone https://github.com/c0mmando/voat-conspiracy-archive.git
```

### Download ZIP or TAR

1. **ZIP Download:**  
   Visit [https://github.com/c0mmando/voat-conspiracy-archive](https://github.com/c0mmando/voat-conspiracy-archive), click on the "Code" button, and select "Download ZIP".

2. **TAR Download:**  
   Similarly, click on the "Code" button and then choose "Download TAR".  

*GitHub automatically provides these download options.*

---

## Hosting via GitHub Pages

GitHub Pages is an easy way to host static content online. Follow these steps to deploy your archive:

1. **Push Your Repository to GitHub**

   Ensure your repository is available on GitHub under your username (if you haven't done so already):

   ```bash
   git init
   git add .
   git commit -m "Initial commit of voat-conspiracy-archive"
   git remote add origin https://github.com/c0mmando/voat-conspiracy-archive.git
   git push -u origin main
   ```

2. **Configure GitHub Pages**

   - Go to your repository on GitHub.
   - Click on **Settings**.
   - Scroll down to the **GitHub Pages** section.
   - Under **Source**, select the branch (e.g., `main`) and choose the folder (typically `/ (root)` if your `index.html` is at the root).
   - Click **Save**.
   - GitHub Pages will provide you with a URL where your site is hosted (typically `https://c0mmando.github.io/voat-conspiracy-archive/`).

3. **Adding a CNAME (Custom Domain)**

   If you wish to use a custom domain:
   
   - Create a file named `CNAME` (with no file extension) in the root of your repository.
   - Add your custom domain (for example, `www.example.com`) on a single line in that file.
   - Commit and push the `CNAME` file:
     
     ```bash
     git add CNAME
     git commit -m "Add CNAME for custom domain"
     git push
     ```
     
   - Configure your DNS settings to point your custom domain to GitHub Pages.  
     For more details, refer to GitHub’s guide on [configuring a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

NOTE: This project includes hard-coded SEO tags (in the HTML and meta tags within the files) that would need to be replaced or updated for anyone mirroring and hosting the project.

---

## Hosting via nginx

To host the archive using nginx on your own server, follow these steps:

1. **Install nginx**

   On Ubuntu/Debian:

   ```bash
   sudo apt update
   sudo apt install nginx
   ```

   On CentOS/RHEL:

   ```bash
   sudo yum install epel-release
   sudo yum install nginx
   ```

2. **Clone the Repository onto Your Server**

   Use git clone to download the latest version on your server:

   ```bash
   cd /var/www/html
   sudo git clone https://github.com/c0mmando/voat-conspiracy-archive.git
   ```

3. **Configure nginx**

   Create a new configuration file (e.g., `/etc/nginx/sites-available/voat-conspiracy-archive`):

   ```nginx
   server {
       listen 80;
       server_name your_domain_or_ip;

       root /var/www/html/voat-conspiracy-archive;
       index index.html;

       location / {
           try_files $uri $uri/ =404;
       }
   }
   ```

   Replace `your_domain_or_ip` with your actual domain or server IP.

4. **Enable the Configuration**

   Create a symbolic link to enable the site:

   ```bash
   sudo ln -s /etc/nginx/sites-available/voat-conspiracy-archive /etc/nginx/sites-enabled/
   ```

5. **Restart nginx**

   Apply your changes by restarting nginx:

   ```bash
   sudo systemctl restart nginx
   ```

6. **Access Your Archive**

   Open your web browser and navigate to `http://your_domain_or_ip` (or your configured domain) to view the archive.


NOTE: This project includes hard-coded SEO tags (in the HTML and meta tags within the files) that would need to be replaced or updated for anyone mirroring and hosting the project.

---

## Offline Viewing Instructions

If you prefer to view the archive offline (e.g., without a web server), you can do so by simply opening the local files directly in your web browser:

1. **Using a File Explorer:**

   - Navigate to the directory where you cloned or downloaded the repository.
   - Open the `index.html` file (by double-clicking or right-clicking and selecting your preferred browser).

2. **From the Command Line:**

   If you're using a local HTTP server (such as Python’s built-in one) for a more seamless navigation experience, you can start one in the repository root:

   For Python 3:

   ```bash
   cd /path/to/voat-conspiracy-archive
   python3 -m http.server 8000
   ```

   For Python 2:

   ```bash
   cd /path/to/voat-conspiracy-archive
   python -m SimpleHTTPServer 8000
   ```

   Then open your browser and go to `http://localhost:8000/` to navigate the archive as if it were hosted on a web server.

---

## Additional Notes

- Ensure file permissions allow nginx (or your local HTTP server) to read the archive files.
- Changes to GitHub Pages may take a short while to propagate.
- Before serving the archive publicly, review any legal or privacy considerations regarding its content.
- Remember: Some SEO meta tags and other hard-coded SEO elements within the HTML files need to be updated or replaced if you mirror or host this project elsewhere.

This README provides instructions for downloading, cloning, hosting (via GitHub Pages or nginx), and viewing the /v/conspiracy archive offline. If you have any issues or need further assistance, please refer to the respective hosting platform's documentation.