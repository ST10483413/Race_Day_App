[![Validate Repository Structure](https://github.com/ST10483413/Race_Day_App/actions/workflows/blank.yml/badge.svg)](https://github.com/ST10483413/Race_Day_App/actions/workflows/blank.yml)

# Race_Day_App

## Project Overview

RaceDay is a comprehensive event management system designed to streamline the organization and participation in running, cycling, and multi-sport events. The system serves two primary user roles and provides a complete solution for event creation, participant enrollment, and results management.

## System Description

The RaceDay system is a web-based application that enables event organizers to create and manage races while allowing participants to discover, register for, and track their performance in various events. The system handles everything from event creation and categorization to participant enrollment and result recording.

### Key Features
- User authentication and role-based access control
- Event creation and management with categories
- Participant registration and enrollment
- Results tracking and leaderboards
- Comprehensive API for frontend integration

## User Roles

### Organiser
- **Purpose**: Create and manage events
- **Capabilities**:
  - Create new events with details (date, location, description)
  - Define event categories (e.g., 5km, 10km, Half-Marathon)
  - Set maximum participant limits
  - View enrolled participants
  - Add and manage event results
  - Update and delete events

### Participant
- **Purpose**: Discover events and track participation
- **Capabilities**:
  - Browse upcoming events with search and filter
  - View event details and category information
  - Enroll in event categories
  - Track enrollment history
  - View personal results and positions
  - Cancel enrollments

## System Architecture

### Database Design
The system uses a relational database with the following entities:
- **Users**: Stores user authentication and role information
- **Organisers**: Extended profile for event organizers
- **Participants**: Extended profile for event participants
- **Events**: Core event information
- **Categories**: Event categories and divisions
- **Enrollments**: Participant registrations
- **Results**: Performance tracking and leaderboard data

### API Structure
All API endpoints follow RESTful conventions and are prefixed with `/api/`. The system provides comprehensive endpoints for authentication, user management, events, categories, enrollments, and results.

## Technology Stack

- **Database**: SQL Server (SSMS)
- **Backend**: C# / .NET Core (planned for Part 2)
- **Frontend**: TBD (HTML/CSS/JavaScript or React)
- **Version Control**: Git with GitHub
- **CI/CD**: GitHub Actions

## Repository Structure

```
RaceDay/
├── docs/
│   ├── ERD.png                    # Entity Relationship Diagram
│   ├── API_Endpoint_Plan.md       # Complete API endpoint specifications
│   └── RaceDay_Schema.sql         # Database creation and seed script
├── src/                           # Application source code (Part 2)
├── .github/workflows/
│   └── validate.yml              # CI/CD workflow
└── README.md                     # This file
```

## Database Setup Instructions

### Prerequisites
- SQL Server (2016 or later recommended)
- SQL Server Management Studio (SSMS)

### Setup Steps

1. **Open SQL Server Management Studio**
   - Connect to your SQL Server instance
   - Open a new query window

2. **Run the Database Script**
   - Navigate to `docs/RaceDay_Schema.sql`
   - Copy the entire script or open the file
   - Execute the script in SSMS
   - The database will be created and populated with sample data

3. **Verify Installation**
   ```sql
   USE RaceDayDB;
   SELECT * FROM Users;
   SELECT * FROM Events;
   SELECT * FROM Enrollments;
   ```

## API Documentation

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login and receive JWT token

### User Management
- `GET /api/users/profile` - Get current user profile
- `PUT /api/users/profile` - Update user profile

### Events
- `GET /api/events` - List all events (with filters)
- `POST /api/events` - Create new event (Organiser only)
- `GET /api/events/{id}` - Get event details
- `PUT /api/events/{id}` - Update event (Organiser only)
- `DELETE /api/events/{id}` - Delete event (Organiser only)

### Categories
- `GET /api/events/{id}/categories` - Get event categories
- `POST /api/categories` - Create new category (Organiser only)
- `DELETE /api/categories/{id}` - Delete category (Organiser only)

### Enrollments
- `POST /api/enrollments` - Enroll in event category
- `GET /api/enrollments/me` - Get user's enrollments
- `PUT /api/enrollments/{id}` - Update enrollment status

### Results
- `POST /api/enrollments/{id}/results` - Add result (Organiser only)
- `GET /api/events/{id}/results` - Get event results

## CI/CD Pipeline

The project uses GitHub Actions for continuous integration to validate repository structure and ensure required files are present.

### Workflow Status
[![Validate Repository Structure](https://github.com/ST10483413/Race_Day_App/actions/workflows/blank.yml/badge.svg)](https://github.com/ST10483413/Race_Day_App/actions/workflows/blank.yml)

### Automated Checks
The workflow validates:
- `/docs` folder existence
- ERD file presence (PNG or PDF)
- API endpoint plan document
- SQL database script
- Required documentation

## Getting Started

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/RaceDay.git
   cd RaceDay
   ```

2. **Set Up the Database**
   - Run the SQL script in SSMS as described above

3. **Review Documentation**
   - Examine `docs/ERD.png` for database structure
   - Review `docs/API_Endpoint_Plan.md` for API details
   - Check the SQL script for data relationships

4. **Plan Your Development**
   - Part 2 will focus on implementing the API using .NET Core
   - Ensure your code matches the endpoint specifications
   - Use the database schema as your data layer

## Video Walkthrough

📺 **Planning and Setup Video**: [Watch on YouTube](https://youtu.be/your-video-link)

The video covers:
1. ERD design decisions and entity relationships
2. API endpoint planning and choices
3. SQL script demonstration
4. Live execution in SSMS
5. System overview and key features

## Development Notes

### Important Considerations
- The system uses role-based access control with JWT authentication
- All foreign key constraints ensure data integrity
- The database follows normalization principles
- API design follows RESTful best practices

### Future Enhancements
- Payment integration for paid events
- Email notifications for registration confirmations
- Advanced filtering and search capabilities
- Participant performance analytics

## Contributors

- Student Name: Thato Maleka
- Student Number: ST10483413
- Module: PROG6212 Programming 2B


## Quick Links

- 📊 [ERD Diagram](docs/ERD.png)
- 📋 [API Endpoint Plan](docs/API_Endpoint_Plan.md)
- 🗄️ [Database Script](docs/RaceDay_Schema.sql)
- 🎥 [Video Walkthrough](https://youtu.be/your-video-link)

---

*Last Updated: September 2026*
