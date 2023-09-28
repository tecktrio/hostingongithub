## How to Add a Custom Domain to GitHub Pages (Hostinger Edition)
webdev
tutorial
cloud
beginners
I recently finished my portfolio website, and it was a dream come true to have a small space of my own on the internet. To make this happen, I bought a domain name from Hostinger. I was already using GitHub Pages to host my site, so I needed to add my new domain name to it.

There weren't any videos on how to do this, so I went through the documentation. The process is a bit different for Hostinger, but if you're like me and you want to set things up quickly, you can follow this blog post.

Refer to this.

### Step 1: Go to your Hostinger domain DNS settings

The first step is to go to your Hostinger domain DNS settings. You can do this by visiting https://hpanel.hostinger.com/domain/yourdomain.com/dns. For example, https://hpanel.hostinger.com/domain/sidharthmohanty.com/dns.

### Step 2: Delete the existing CNAME record and A type record

By default, there should be a CNAME record for your domain. This record points your domain to Hostinger's default website. We need to delete this record so that we can create a new CNAME record that points to our GitHub Pages site. Also delete any default A type records so that there is no collision or clash.

### Step 3: Create two new CNAME records

We need to create two new CNAME records. The first record will point www.yourdomain.com to <your-github-username>.github.io. The second record will point yourdomain.com to <your-github-username>.github.io.

Enter Type - CNAME, Name - www, Points to - .github.io, TTL you can leave as default. This is for when someone types www.yourdomain.com.
Then we need the same for APEX domains or when someone just types yourdomain.com, for this enter another CNAME with Name - @ and Points to .github.io. This will automatically set an ALIAS type and add it to the DNS records.
It should look like this when added,

CNAME records

### Step 4: Add the GitHub Pages IP addresses

Finally, we need to add the IP addresses for GitHub Pages to our DNS records. Add A type, Name - @, TTL can be left as default records for each of the following IP addresses (should be copied and pasted into “Points to”)
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```
Once you've added the IP addresses, your DNS records should look like this:

GitHub IPs added

### Step 5: Add the custom domain to GitHub Pages

The last step is to add the custom domain to GitHub Pages. You can do this by going to your GitHub repository and clicking on the Settings tab. Then, click on the Pages tab and enter your custom domain in the Custom domain field.
