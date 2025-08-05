# Zomato Management System - Backend

This is the backend server for the Zomato Management System, built with Node.js, Express, and MySQL.

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 or higher)
- MySQL (v8.0 or higher)
- npm or yarn

### Installation

1. **Clone the repository and navigate to backend:**
   \`\`\`bash
   cd backend
   \`\`\`

2. **Install dependencies:**
   \`\`\`bash
   npm install
   \`\`\`

3. **Configure environment variables:**
   \`\`\`bash
   cp .env.example .env
   # Edit .env with your database credentials
   \`\`\`

4. **Setup database:**
   \`\`\`bash
   npm run setup
   \`\`\`

5. **Start the server:**
   \`\`\`bash
   npm start
   # or for development with auto-reload:
   npm run dev
   \`\`\`

## 📊 Database Setup

The system includes automated database setup scripts that will:
- Create the `zomato_management` database if it doesn't exist
- Create all required tables with proper relationships
- Insert sample data for testing

### Available Commands

\`\`\`bash
# Complete setup (recommended for first time)
npm run setup

# Database operations
npm run db:setup    # Create database and tables
npm run db:check    # Check database status
npm run db:reset    # Reset database completely
\`\`\`

### Manual Database Setup

If you prefer to run the SQL scripts manually:

\`\`\`bash
# Connect to MySQL and run:
mysql -u root -p < backend/scripts/create-database.sql
mysql -u root -p < backend/scripts/seed-data.sql
\`\`\`

## 🗄️ Database Schema

### Core Tables
- **customers** - Customer information and contact details
- **restaurants** - Restaurant profiles and settings
- **menu_categories** - Menu organization
- **menu_items** - Individual food items
- **orders** - Order tracking and management
- **order_items** - Items within each order
- **restaurant_hours** - Operating hours configuration
- **customer_addresses** - Customer delivery addresses
- **reviews** - Customer reviews and ratings

### Key Features
- **Foreign key constraints** for data integrity
- **Indexes** for optimized query performance
- **ENUM types** for status management
- **Timestamps** for audit trails
- **Cascading deletes** for data consistency

## 🔧 API Endpoints

### Restaurant Management
- `GET /api/restaurants` - List all restaurants
- `GET /api/restaurants/:id` - Get restaurant details
- `GET /api/restaurants/:id/menu` - Get restaurant menu
- `PUT /api/outlet` - Update outlet settings

### Menu Management
- `GET /api/menu` - Get menu items
- `POST /api/menu` - Add new menu item
- `PUT /api/menu/:id` - Update menu item
- `DELETE /api/menu/:id` - Delete menu item
- `GET /api/categories` - Get menu categories
- `POST /api/categories` - Add new category

### Order Management
- `GET /api/orders` - Get orders (with filters)
- `POST /api/orders` - Create new order
- `PUT /api/orders/:id` - Update order status
- `GET /api/orders/:id` - Get order details

### Customer Management
- `GET /api/customers` - List customers
- `POST /api/customers` - Register new customer

## 🔒 Environment Variables

\`\`\`env
# Database Configuration
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=zomato_management

# Server Configuration
PORT=5000
NODE_ENV=development
\`\`\`

## 🛠️ Development

### Project Structure
\`\`\`
backend/
├── scripts/
│   ├── create-database.sql    # Database schema
│   ├── seed-data.sql         # Sample data
│   ├── database-setup.js     # Setup automation
│   └── run-setup.js          # Setup runner
├── server.js                 # Main server file
├── package.json             # Dependencies
├── .env.example             # Environment template
└── README.md               # This file
\`\`\`

### Adding New Features
1. Update database schema in `create-database.sql`
2. Add sample data in `seed-data.sql`
3. Implement API endpoints in `server.js`
4. Test with the frontend components

## 🔍 Troubleshooting

### Common Issues

**Database Connection Failed:**
- Check MySQL is running
- Verify credentials in `.env`
- Ensure MySQL user has proper permissions

**Tables Already Exist:**
- Use `npm run db:reset` to start fresh
- Or manually drop tables and re-run setup

**Port Already in Use:**
- Change PORT in `.env`
- Kill existing process: `lsof -ti:5000 | xargs kill`

### Logs and Debugging
- Server logs show all database operations
- Enable MySQL query logging for detailed debugging
- Use `npm run db:check` to verify database state

## 📈 Performance Optimization

The database includes several optimizations:
- **Indexes** on frequently queried columns
- **Connection pooling** for efficient database access
- **Prepared statements** to prevent SQL injection
- **Optimized queries** with proper JOINs

## 🔐 Security Features

- **SQL injection prevention** with parameterized queries
- **Input validation** on all endpoints
- **CORS configuration** for cross-origin requests
- **Environment variable protection** for sensitive data
