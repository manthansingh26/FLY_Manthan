# Personal Website Live & DNS Walkthrough (PF-04)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 5)  
**Code:** PF-04  

---

## 1. Live HTTPS Website Deliverable

* **Live Public URL:** [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/)
* **Status:** Live over HTTPS (SSL secured).
* **Included Links:**
  * GitHub Repository: [manthansingh26/FLY_Manthan](https://github.com/manthansingh26/FLY_Manthan)
  * Live Capstone Research Paper: [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/)
  * LinkedIn & Professional Contact Links.

---

## 2. Plain-Language DNS Walkthrough (1 Page)

### What Happens When You Type a Website Address?

When a user types `https://manthansingh26.github.io/FLY_Manthan/` into a web browser, their computer doesn't naturally know where that website lives. Computers communicate across the internet using numerical IP addresses (like `185.199.108.153`). 

**Domain Name System (DNS)** is the internet's phonebook that translates human-readable domain names into machine-readable IP addresses. Here is the 4-step walkthrough of what happens behind the scenes:

#### Step 1: The Local Search & DNS Resolver
Your web browser first checks its local cache. If it doesn't find the IP address, it sends a request to a **DNS Recursive Resolver** (usually provided by your Internet Service Provider or public DNS like Google `8.8.8.8` or Cloudflare `1.1.1.1`).

#### Step 2: Querying the Root & TLD Nameservers
If the resolver doesn't have the answer cached, it asks the **Root Nameserver**, which points it to the **Top-Level Domain (TLD) Nameserver** responsible for `.io` or `.com` domains.

#### Step 3: Authoritative Nameservers & CNAME Records
The TLD nameserver directs the resolver to GitHub's **Authoritative Nameserver**.
* **What is a CNAME Record?** A **Canonical Name (CNAME)** record is an alias in DNS that maps one domain name to another domain name rather than a raw IP address. For custom domain setups (e.g., `portfolio.manthansingh.com`), a CNAME record points your domain to `manthansingh26.github.io`.
* The authoritative nameserver responds with the exact IP address of GitHub's CDN web server.

#### Step 4: HTTPS SSL Handshake & Page Response
Once your browser gets the IP address, it initiates a secure **HTTPS Connection**:
1. **SSL/TLS Handshake:** The web server presents a digital SSL certificate. Your browser verifies that the certificate is valid and encrypts all data sent back and forth (showing the secure padlock icon 🔒 in your address bar).
2. **Page Delivery:** The server returns the HTML, CSS, and JavaScript files, and your browser renders the live website on your screen.
