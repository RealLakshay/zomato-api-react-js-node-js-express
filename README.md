# Zomato Management System

A complete restaurant management system with REST API backend and React frontend, featuring order management, menu management, and customer management.

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 or higher)
- MySQL (v8.0 or higher) 
- npm or yarn

### Installation

1. **Clone and install dependencies:**
   \`\`\`bash
   git clone <repository-url>
   cd zomato-management-system
   npm run install:all
   \`\`\`

2. **Setup backend database:**
   \`\`\`bash
   cd backend
   cp .env.example .env
   # Edit .env with your MySQL credentials (default: root/root)
   npm run setup
   \`\`\`

3. **Start development servers:**
   \`\`\`bash
   # From root directory
   npm run dev
   \`\`\`

   This will start:
   - Backend API server on http://localhost:5000
   - Frontend React app on http://localhost:3000

## 📁 Project Structure

\`\`\`
zomato-management-system/
├── backend/                 # REST API Server
│   ├── scripts/            # Database setup scripts
│   ├── server.js           # Main server file
│   ├── package.json        # Backend dependencies
│   └── .env               # Environment variables
├── frontend/               # React Frontend
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── App.jsx        # Main app component
│   │   └── main.jsx       # Entry point
│   ├── package.json       # Frontend dependencies
│   └── vite.config.js     # Vite configuration
└── package.json           # Root package.json with scripts
\`\`\`

## 🔧 Available Scripts

### Root Level Scripts
\`\`\`bash
npm run dev              # Start both backend and frontend
npm run start            # Production start
npm run setup            # Setup backend and frontend
npm run install:all      # Install all dependencies
npm run test:api         # Test REST API endpoints
\`\`\`

### Backend Scripts
\`\`\`bash
cd backend
npm run dev              # Start with nodemon
npm run start            # Production start
npm run setup            # Database setup
npm run test:connection  # Test MySQL connection
npm run db:reset         # Reset database
\`\`\`

### Frontend Scripts
\`\`\`bash
cd frontend
npm run dev              # Start Vite dev server
npm run build            # Build for production
npm run preview          # Preview production build
\`\`\`

## 🗄️ Database Setup

The system uses MySQL with the following configuration:

**Default Credentials (for development):**
- Host: localhost
- Port: 3306
- Username: root
- Password: root
- Database: zomato_management

**Setup Process:**
1. Ensure MySQL is running
2. Run `npm run setup` from backend directory
3. Database and tables will be created automatically
4. Sample data will be inserted

## 🌐 REST API Endpoints

### Restaurants
- `GET /api/restaurants` - Get all restaurants
- `GET /api/restaurants/:id` - Get restaurant by ID
- `POST /api/restaurants` - Create restaurant
- `PUT /api/restaurants/:id` - Update restaurant
- `DELETE /api/restaurants/:id` - Delete restaurant
- `GET /api/restaurants/:id/menu` - Get restaurant menu

### Menu Items
- `GET /api/menu-items` - Get all menu items
- `GET /api/menu-items/:id` - Get menu item by ID
- `POST /api/menu-items` - Create menu item
- `PUT /api/menu-items/:id` - Update menu item
- `DELETE /api/menu-items/:id` - Delete menu item

### Categories
- `GET /api/categories` - Get all categories
- `GET /api/categories/:id` - Get category by ID
- `POST /api/categories` - Create category
- `PUT /api/categories/:id` - Update category
- `DELETE /api/categories/:id` - Delete category

### Orders
- `GET /api/orders` - Get all orders
- `GET /api/orders/:id` - Get order by ID
- `POST /api/orders` - Create order
- `PUT /api/orders/:id` - Update order
- `DELETE /api/orders/:id` - Cancel order

### Customers
- `GET /api/customers` - Get all customers
- `GET /api/customers/:id` - Get customer by ID
- `POST /api/customers` - Create customer
- `PUT /api/customers/:id` - Update customer
- `DELETE /api/customers/:id` - Delete customer

### Analytics
- `GET /api/analytics/restaurants/:id` - Restaurant analytics
- `GET /api/analytics/overview` - System overview

### Utility
- `GET /api/health` - Health check
- `GET /api/docs` - API documentation

## 🎯 Features

### Restaurant Dashboard
- **Menu Management**: Add, edit, delete menu items and categories
- **Order Management**: Real-time order tracking and status updates
- **Outlet Management**: Configure restaurant settings and operating hours
- **Analytics**: View sales reports and performance metrics

### Customer App
- **Restaurant Discovery**: Browse available restaurants
- **Menu Browsing**: View restaurant menus with categories
- **Order Placement**: Add items to cart and place orders
- **Order Tracking**: Track order status in real-time
- **User Management**: Customer registration and profile management

### REST API Features
- **Full CRUD Operations**: Complete Create, Read, Update, Delete for all entities
- **Pagination**: Efficient data loading with pagination support
- **Filtering**: Advanced filtering options for all endpoints
- **Error Handling**: Comprehensive error responses
- **Validation**: Input validation and data integrity
- **Documentation**: Built-in API documentation

## 🔐 Environment Variables

### Backend (.env)
\`\`\`env
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=root
DB_NAME=zomato_management
PORT=5000
NODE_ENV=development
\`\`\`

## 🛠️ Development

### Adding New Features
1. **Backend**: Add new routes in `backend/server.js`
2. **Frontend**: Create new components in `frontend/src/components/`
3. **Database**: Update schema in `backend/scripts/create-database.sql`

### Testing
\`\`\`bash
# Test API endpoints
npm run test:api

# Test database connection
cd backend && npm run test:connection

# Check API documentation
curl http://localhost:5000/api/docs
\`\`\`

## 🚀 Deployment

### Production Build
\`\`\`bash
# Build frontend
cd frontend && npm run build

# Start production servers
npm run start
\`\`\`

### Environment Setup
1. Update environment variables for production
2. Configure production database
3. Set up reverse proxy (nginx recommended)
4. Enable SSL certificates

## 🔍 Troubleshooting

### Common Issues

**Database Connection Failed:**
- Check MySQL is running
- Verify credentials in `.env`
- Test connection: `npm run test:connection`

**Port Already in Use:**
- Change PORT in `.env`
- Kill existing process: `lsof -ti:5000 | xargs kill`

**API Endpoints Not Working:**
- Ensure backend server is running on port 5000
- Check Vite proxy configuration
- Verify API base URL in frontend

**Frontend Not Loading:**
- Check if Vite dev server is running on port 3000
- Clear browser cache
- Check console for JavaScript errors

### Reset Everything
\`\`\`bash
# Reset database
cd backend && npm run db:reset

# Reinstall dependencies
npm run install:all

# Restart development servers
npm run dev
\`\`\`

## 📊 Sample Data

The system includes sample data:
- 4 restaurants with different cuisines
- 30+ menu items across categories
- 4 sample customers
- 3 sample orders with different statuses

## 🤝 Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -am 'Add feature'`
4. Push to branch: `git push origin feature-name`
5. Submit pull request

## 📄 License

This project is licensed under the MIT License.
