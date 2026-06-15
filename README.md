# Bambe - Clothes & Shoes E-Commerce Store

A modern e-commerce web application for **Bambe**, a Rwanda-based online fashion store selling clothes and shoes. Built with HTML, CSS, PHP, JavaScript, and MySQL.

## Live Demo

> Deploy using Docker (see below) or host on Railway/Render. Update this URL after deployment.

- **Local:** http://localhost:8080
- **GitHub:** https://github.com/kwizeraangelus/bambStore/
- hosted:**  https://lightslategray-mink-727528.hostingersite.com/

## Features

### Customer Store
- Responsive homepage with navigation and hero section
- Product listing with category filters and search
- Product detail pages with quantity selector
- Shopping cart (add, remove, update quantities, totals)
- Checkout with customer details and order summary
- Order confirmation page

### Admin Panel (`/admin`)
- Secure admin login
- **Dashboard** with revenue, orders, sales charts, and top products
- **Product management** — add, edit, delete products with image upload
- **Order management** — view orders and update status (pending → delivered)
- Analytics statistics for business insights

### Infrastructure
- MySQL database for products, customers, orders, and admins
- Docker containerization
- GitHub Actions CI/CD pipeline

## Tech Stack

| Layer     |         Technology             |
|-------    |--------------------------------|
| Frontend  |       HTML5, CSS3, JavaScript  |
| Backend   |       PHP 8.2                  |
| Database  |       MySQL 8.0                |
| Container |       Docker, Docker Compose   |
| CI/CD     |       GitHub Actions           |

## Project Structure

```
bambe/
├── assets/
│   ├── css/style.css
│   └── js/main.js
├── config/database.php
├── database/schema.sql
├── includes/
│   ├── init.php
│   ├── header.php
│   ├── footer.php
│   └── functions.php
├── .github/workflows/ci-cd.yml
├── index.php
├── products.php
├── product.php
├── cart.php
├── cart-action.php
├── checkout.php
├── order-confirmation.php
├── health.php
├── Dockerfile
├── docker-compose.yml
└── README.md
```

## Admin Access

| Field    | Value                                 |
|----------|-------                                |
| URL      | http://localhost:8080/admin/login.php |
| Username | `admin`                               |
| Password | `admin123`                            |


## Quick Start with Docker

### Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed

### Run the Application

```bash
# Clone the repository
git clone https://github.com/kwizeraangelus/bambStore
cd bambe

# Build and start containers
docker compose up --build -d

# Open in browser
# http://localhost:8080
```

### Stop the Application

```bash
docker compose down
```

### View Logs

```bash
docker compose logs -f web
```

## Manual Setup (Without Docker)

### Requirements

- PHP 8.0+ with PDO MySQL extension
- MySQL 8.0+
- Apache or Nginx web server

### Steps

1. Import the database:
   ```bash
   mysql -u root -p < database/schema.sql
   ```

2. Update database credentials in `config/database.php` or set environment variables:
   ```
   DB_HOST=localhost
   DB_NAME=bambe
   DB_USER=bambe
   DB_PASS=bambe123
   ```

3. Point your web server document root to the project folder.

4. Visit `http://localhost` in your browser.

## Database

The `database/schema.sql` file creates:

- **categories** - Clothes, Shoes
- **products** - 16 sample products with images and prices in RWF
- **customers** - Customer delivery information
- **orders** - Order records with status
- **order_items** - Line items per order
- **admins** - Admin users for the management panel

## CI/CD Pipeline

GitHub Actions workflow (`.github/workflows/ci-cd.yml`):

1. **Build** - Builds Docker images on every push
2. **Test** - Starts containers, runs health checks, verifies pages load
3. **Deploy** - Runs on main branch after tests pass

## Deployment Options

### HOSTINGER

1. Push code to GitHub
2. Connect repository to Railway or Render
3. Add MySQL database service
4. Set environment variables: `DB_HOST`, `DB_NAME`, `DB_USER`, `DB_PASS`
5. Deploy using the Dockerfile



```bash
git clone <repo-url>
cd bambe
docker compose up -d --build
```

## Screenshots

Take screenshots of:
- Homepage
- Product listing
- Product details
- Shopping cart
- Checkout
- Order confirmation

## License

Academic project - Bambe Fashion Store E-Commerce Platform.
