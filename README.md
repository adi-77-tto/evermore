<div align="center">
  <p>
    <img alt="Evermore" src="Frontend/public/assets/images/logo.png" width="140" />
  </p>
  <h1>Evermore</h1>
  <p>Full-stack ecommerce website with a React (Vite) frontend and a PHP/MySQL backend.</p>

  <p>
    <img alt="React" src="https://img.shields.io/badge/React-18+-61DAFB?logo=react&logoColor=000" />
    <img alt="Vite" src="https://img.shields.io/badge/Vite-4+-646CFF?logo=vite&logoColor=fff" />
    <img alt="PHP" src="https://img.shields.io/badge/PHP-8.2-777BB4?logo=php&logoColor=fff" />
    <img alt="MySQL" src="https://img.shields.io/badge/MySQL-8.0-4479A1?logo=mysql&logoColor=fff" />
  </p>
</div>

<details>
  <summary><strong>Stack</strong></summary>
  <br />
  <ul>
    <li>Frontend: React + Vite</li>
    <li>Backend: PHP (MySQL)</li>
    <li>Database: MySQL / MariaDB</li>
  </ul>
</details>

<details>
  <summary><strong>Features</strong></summary>
  <br />
  <ul>
    <li>Product listing, categories, and search</li>
    <li>Custom design builder</li>
    <li>Cart and checkout flow</li>
    <li>User auth and profile management</li>
    <li>Admin area for products/orders</li>
  </ul>
</details>

<details>
  <summary><strong>Project Structure</strong></summary>
  <br />
  <ul>
    <li>Frontend/</li>
    <li>backend/</li>
    <li>database/</li>
  </ul>
</details>

<h2>Local Setup</h2>

<h3>1) Requirements</h3>
<ul>
  <li>Node.js 18+</li>
  <li>XAMPP (Apache + MySQL) or another PHP/MySQL stack</li>
</ul>

<h3>2) Database import</h3>
<ol>
  <li>Start MySQL (XAMPP Control Panel -&gt; Start MySQL)</li>
  <li>Import the dump:</li>
</ol>

```bash
mysql -u root -e "DROP DATABASE IF EXISTS evermore_db; CREATE DATABASE evermore_db"
Get-Content database/evermore_evermore_db.sql | mysql --max_allowed_packet=256M -u root evermore_db
```

<h3>3) Backend config</h3>
<ul>
  <li>Copy <code>backend/config/secrets.example.php</code> to <code>backend/config/secrets.php</code> if you need SMTP.</li>
  <li>Create <code>.env</code> in the repo root (not committed):</li>
</ul>

```env
EVERMORE_IS_PRODUCTION=false
EVERMORE_DB_MODE=local
EVERMORE_LOCAL_DB_HOST=localhost
EVERMORE_LOCAL_DB_PORT=3306
EVERMORE_LOCAL_DB_USER=your_user
EVERMORE_LOCAL_DB_PASS=your_password
EVERMORE_LOCAL_DB_NAME=your_database
```

<h3>4) Run backend</h3>
<p>Place the <code>backend</code> folder under your web root (e.g., <code>xampp/htdocs/backend</code>) so it is served at:</p>

```
http://localhost/backend
```

<h3>5) Run frontend</h3>

```bash
cd Frontend
npm install
npm run dev
```

The app runs at http://localhost:5173.

<h2>Screenshots</h2>
<p>
  <img alt="Home" src="docs/screenshots/home.png" width="48%" />
  <img alt="Products" src="docs/screenshots/products.png" width="48%" />
</p>
<p>
  <img alt="Cart" src="docs/screenshots/cart.png" width="48%" />
  <img alt="Admin" src="docs/screenshots/admin.png" width="48%" />
</p>

<h2>Notes</h2>
<ul>
  <li>Frontend API base URL defaults to <code>/backend</code> and uses a Vite proxy in dev.</li>
  <li><code>.env</code> and <code>backend/config/secrets.php</code> are ignored by git.</li>
</ul>

<h2>Deployment</h2>
<ul>
  <li>Ensure production env vars are set for DB and SMTP.</li>
  <li>Set <code>EVERMORE_IS_PRODUCTION=true</code> and <code>EVERMORE_DB_MODE=remote</code> on the server.</li>
</ul>
