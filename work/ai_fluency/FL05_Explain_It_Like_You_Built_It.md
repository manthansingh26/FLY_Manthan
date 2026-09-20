# Explain It Like You Built It

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 5)  

---

## 1. Selected Technical Feature

**Chosen Feature:** *How Static Single-Page HTML Deployment & Continuous Integration Work on GitHub Pages*

---

## 2. Plain-Words Explanation (Teaching a Friend)

Imagine you write a letter (your HTML code) and store it in a drawer on your computer. If a friend in another city wants to read it, they can't look inside your laptop's hard drive.

Here is how we turn that local file into a live website that anyone on earth can visit in 3 simple steps:

1. **The Public Storage Locker (GitHub Repo):** We upload our code folder (`docs/index.html`) to a public repository on GitHub. Think of GitHub as a digital library where everyone can see your published files.
2. **The Automated Web Server (GitHub Pages):** When we enable GitHub Pages in repo settings, GitHub turns on a high-speed web server. Every time we update our code and run `git push origin main`, GitHub's automated server detects the new file, packages it up, and makes it available over the internet in under 60 seconds.
3. **The Web Address (HTTPS URL):** GitHub assigns a clean address (`https://manthansingh26.github.io/FLY_Manthan/`). When someone types this into a web browser, their phone or laptop requests the `index.html` file from GitHub's server. The server sends back the HTML text, and your browser instantly paints the text, colors, tables, and charts on your screen.
