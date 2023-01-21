# Cloudflare Domain Parking

Unlike buying or managing domains with registrars like Namecheap or GoDaddy, Cloudflare does not (yet?) provide a parking page for domains that are not currently being routed to a website host. Instead of a browser showing "This site can't be reached" becasue of a NXDOMAIN error, you can host this domain parking template with Cloudflare Pages for free, so anyone that happens to search your domain can see that you are planning to use the domain.

# Host with Cloudflare Pages

Using Cloudflare Pages, you can conect a GitHub or GitLab account and select a repository to connect as your project’s source code. New commits will trigger Cloudflare to automatically build and deploy your changes. Alternatively, you could use Direct Upload to upload your site's assest directly from your computer or Wrangler CLI to deploy your files from the command line.

# Add Domain Name
Once your project is built, it is given a default address on a `.pages.dev` subdomain, you can add your domain by configuring your domain's Cloudflare DNS with the following CNAME record:

| Type  | Name | Content                  | TTL  |
| ------| ---- | ------------------------ | ---- |
| CNAME | @    | <PROJECT_NAME>.pages.dev | Auto | 

# Additional DNS Settings

If you have not already, Cloudflare also recommends that you add an A, AAAA, or CNAME record for `www` so that `www.yourdomain.com` can resolve. 

| Type  | Name | Content | TTL  |
| ------| ---- | ------- | ---- |
| CNAME | www  | @       | Auto |
