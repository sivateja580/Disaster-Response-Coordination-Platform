# Disaster Response Coordination Platform

A comprehensive disaster response platform built with React, Node.js, Express, and Supabase. This platform aggregates real-time data to aid disaster management with advanced features including location extraction, geospatial queries, social media monitoring, and image verification.

## 🚀 Features

### Core Functionality
- **Disaster Data Management**: Complete CRUD operations with audit trails and ownership tracking
- **Location Intelligence**: Google Gemini API integration for location extraction from descriptions
- **Geospatial Mapping**: Coordinate conversion and proximity-based resource queries
- **Real-Time Updates**: WebSocket integration for live data synchronization

### External Integrations
- **Google Gemini API**: Location extraction and image verification
- **Mapping Services**: Support for Google Maps, Mapbox, and OpenStreetMap geocoding
- **Social Media Monitoring**: Mock Twitter API with real-time report aggregation
- **Official Updates**: Web scraping from government and relief websites
- **Image Verification**: AI-powered authenticity checking for disaster images

### Advanced Features
- **Supabase Caching**: TTL-based caching system for API responses
- **Geospatial Queries**: PostGIS integration for location-based resource finding
- **Background Tasks**: Automated data updates and cleanup processes
- **Role-Based Access**: Authentication with different permission levels
- **Real-Time Dashboard**: Live updates with WebSocket notifications

## 🛠 Technology Stack

### Backend
- **Node.js** with Express.js
- **Supabase** (PostgreSQL with PostGIS)
- **Socket.IO** for WebSockets
- **Winston** for structured logging
- **Node-cron** for background tasks

### Frontend
- **React** with TypeScript
- **Tailwind CSS** for styling
- **Lucide React** for icons
- **Socket.IO Client** for real-time updates

### External APIs
- **Google Gemini API** for AI processing
- **Google Maps/Mapbox/OpenStreetMap** for geocoding
- **Twitter API** (with mock fallback)
- **Web scraping** for official updates

## 📋 Prerequisites

- Node.js 18+ and npm
- Supabase account and project
- Google Gemini API key
- (Optional) Google Maps API key or Mapbox token

## 🚀 Quick Start

### 1. Clone and Install
```bash
git clone <repository-url>
cd disaster-response-platform
npm install
```

### 2. Environment Setup
Copy `.env.example` to `.env` and configure:

```env
# Supabase Configuration
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

# Google Gemini API
GEMINI_API_KEY=your_gemini_api_key

# Mapping Service (choose one)
GOOGLE_MAPS_API_KEY=your_google_maps_api_key
MAPBOX_ACCESS_TOKEN=your_mapbox_token

# Server Configuration
PORT=3001
NODE_ENV=development
```

### 3. Database Setup
Run the Supabase migrations:
```bash
# Apply migrations in order:
# 1. create_disasters_table.sql
# 2. create_reports_table.sql
# 3. create_resources_table.sql
# 4. create_cache_table.sql
```

### 4. Start Development
```bash
npm run dev
```

This starts both the backend server (port 3001) and frontend (port 5173).

## 📊 Database Schema

### Tables
- **disasters**: Main disaster records with geospatial data
- **reports**: User-submitted reports with verification status
- **resources**: Emergency resources with location data
- **cache**: API response caching with TTL

### Key Features
- **PostGIS Integration**: Geospatial queries and indexing
- **Row Level Security**: Comprehensive access control
- **Audit Trails**: Complete change tracking
- **Geospatial Functions**: Distance-based resource finding

## 🔌 API Endpoints

### Disasters
- `GET /api/disasters` - List disasters with filtering
- `POST /api/disasters` - Create new disaster
- `PUT /api/disasters/:id` - Update disaster
- `DELETE /api/disasters/:id` - Delete disaster

### Location Services
- `POST /api/geocoding` - Extract location and convert to coordinates

### Social Media
- `GET /api/social-media/:disasterId` - Get social media reports

### Resources
- `GET /api/resources/:disasterId` - Get resources with geospatial filtering
- `POST /api/resources/:disasterId` - Add new resource

### Official Updates
- `GET /api/updates/:disasterId` - Get official government updates

### Verification
- `POST /api/verification/:disasterId` - Verify image authenticity

## 🔄 Real-Time Features

### WebSocket Events
- `disaster_updated` - Disaster CRUD operations
- `social_media_updated` - New social media reports
- `resources_updated` - Resource changes
- `background_social_media_check` - Automated checks
- `resource_status_update` - Status updates
- `daily_summary` - Daily statistics

### Background Tasks
- **Cache Cleanup**: Hourly expired cache removal
- **Social Media Monitoring**: 5-minute report checks
- **Resource Updates**: 15-minute availability updates
- **Daily Summaries**: Midnight statistical reports

## 🔐 Authentication & Authorization

### Mock Users (Development)
- **netrunnerX**: Admin with full permissions
- **reliefAdmin**: Admin with full permissions
- **citizen1**: Contributor with create/read permissions
- **responder1**: Responder with create/read/update permissions

### Permissions
- **create**: Add new disasters/resources
- **read**: View all data
- **update**: Modify existing records
- **delete**: Remove records
- **verify**: Verify images and reports

## 🎨 Frontend Features

### Components
- **DisasterCard**: Rich disaster display with real-time updates
- **DisasterForm**: Comprehensive disaster reporting with geocoding
- **ConnectionStatus**: WebSocket connection indicator
- **RealTimeUpdates**: Live notification system

### Key Features
- **Responsive Design**: Mobile-first approach
- **Real-Time Updates**: Live data synchronization
- **Advanced Filtering**: Search and tag-based filtering
- **Geolocation Integration**: Automatic coordinate resolution
- **Professional UI**: Emergency response optimized design

## 🧪 Testing

### Mock Data Available
- Sample disasters with various priorities
- Mock social media reports with different platforms
- Simulated official updates from government sources
- Test resources with geospatial data

### API Testing
All endpoints include comprehensive error handling and validation.

## 🚀 Deployment

### Backend (Render/Railway)
```bash
npm run build
npm start
```

### Frontend (Vercel/Netlify)
```bash
npm run build
# Deploy dist/ folder
```

### Environment Variables
Ensure all production environment variables are configured in your deployment platform.

## 📝 Development Notes

### AI Tool Usage
This project was built with assistance from AI coding tools for:
- API route generation and optimization
- Supabase query construction
- WebSocket implementation
- Geospatial query logic
- Mock data generation

### Performance Optimizations
- **Supabase Caching**: Reduces API calls with intelligent TTL
- **Geospatial Indexing**: Fast location-based queries
- **Background Processing**: Non-blocking data updates
- **Connection Pooling**: Efficient database connections

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

For issues and questions:
1. Check the GitHub issues
2. Review the API documentation
3. Verify environment configuration
4. Check Supabase connection and migrations

---

**Built for emergency response coordination with real-time data aggregation and AI-powered insights.**