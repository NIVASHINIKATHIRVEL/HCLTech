# Fleet & Driver Management System

A Java Full Stack web application for managing vehicles, drivers, trips, fuel records, maintenance schedules, and document expiry in a logistics/transport company.

## 📌 Project Overview

The **Fleet & Driver Management System** helps transport companies manage their fleet operations digitally.

The system allows fleet managers to register vehicles and drivers, assign trips, track odometer readings and fuel usage, schedule preventive maintenance, monitor document expiry, and generate cost-per-kilometre reports.

The application provides separate access for **Admin, Fleet Manager, and Driver**.

---

## 🎯 Objectives

* Manage vehicle and driver information in one centralized system.
* Assign trips to available vehicles and drivers.
* Track trip start/end details and odometer readings.
* Record fuel consumption and expenses.
* Schedule vehicle maintenance based on kilometres or dates.
* Monitor insurance, permit, and licence expiry.
* Generate fleet performance and cost-per-kilometre reports.
* Reduce manual record keeping and improve fleet visibility.

---

## 👥 User Roles

### Admin

* Manage users and roles.
* View fleet and driver information.
* Monitor trips and reports.
* View alerts and maintenance status.

### Fleet Manager

* Register and manage vehicles.
* Register and manage drivers.
* Add vehicle documents.
* Assign trips.
* Manage maintenance schedules.
* Monitor fuel records.
* View fleet reports and alerts.

### Driver

* View assigned trips.
* Start trips with odometer readings.
* End trips with odometer readings.
* Record fuel usage.

---

## 🚀 Core Features

### 1. Vehicle Management

* Add, update, view, and manage vehicles.
* Store vehicle number, type, model, fuel type, and status.
* Track vehicle availability.
* Mark vehicles as available, assigned, on-trip, or under maintenance.

### 2. Driver Management

* Register driver profiles.
* Store licence details and expiry date.
* Track driver availability.
* Prevent drivers from being assigned to multiple active trips.

### 3. Trip Management

* Create and assign trips.
* Assign available vehicles and drivers.
* Record trip source and destination.
* Start and end trips.
* Track starting and ending odometer readings.
* Automatically calculate distance travelled.

### 4. Fuel Management

* Record fuel quantity and cost.
* Store fuel date and odometer reading.
* Track vehicle fuel consumption.
* Use fuel records for cost analysis.

### 5. Maintenance Management

* Schedule preventive maintenance.
* Support maintenance based on kilometres or dates.
* Identify vehicles due for maintenance.
* Record maintenance history.
* Block vehicles during maintenance.

### 6. Document Management

Track important documents such as:

* Vehicle Insurance
* Registration
* Permit
* Pollution Certificate
* Driver Licence

The system monitors expiry dates and generates alerts.

### 7. Alerts

The system provides alerts for:

* Expiring vehicle documents
* Expiring driver licences
* Upcoming maintenance
* Overdue maintenance

A scheduled background job checks expiry dates automatically.

### 8. Reports

The system provides reports such as:

* Vehicle mileage
* Fuel usage
* Trip statistics
* Maintenance costs
* Cost per kilometre

---

## 📋 Functional Requirements

| ID  | Requirement                                                 |
| --- | ----------------------------------------------------------- |
| FR1 | Manager can register vehicles and documents.                |
| FR2 | Manager can register drivers.                               |
| FR3 | Manager can assign trips to available vehicles and drivers. |
| FR4 | Driver can start/end trips with odometer readings.          |
| FR5 | Driver can log fuel usage.                                  |
| FR6 | System schedules maintenance by kilometres/date.            |
| FR7 | System alerts users about document expiry.                  |
| FR8 | Admin can view cost-per-kilometre reports.                  |

---

## 📖 User Stories

### US-01 — Vehicle & Document Management

**5 Story Points**

> As a Fleet Manager, I want to register vehicles and their documents so that I can maintain accurate vehicle records and track document validity.

### US-02 — Driver Management

**3 Story Points**

> As a Fleet Manager, I want to register drivers and their licence details so that I can maintain driver records and monitor licence expiry.

### US-03 — Trip Assignment

**5 Story Points**

> As a Fleet Manager, I want to assign trips to available vehicles and drivers so that trips can be planned without assigning unavailable resources.

### US-04 — Trip Start & End

**5 Story Points**

> As a Driver, I want to start and end my assigned trip with odometer readings so that the system can record trip distance accurately.

### US-05 — Fuel Logging

**3 Story Points**

> As a Driver, I want to record fuel usage for my vehicle so that fuel consumption and mileage can be tracked.

### US-06 — Maintenance Scheduling

**5 Story Points**

> As a Fleet Manager, I want the system to schedule vehicle maintenance based on kilometres or dates so that vehicles can be serviced on time.

### US-07 — Document Expiry Alerts

**5 Story Points**

> As a Fleet Manager, I want the system to alert me about expiring vehicle and driver documents so that I can renew them before they expire.

### US-08 — Cost per KM Reports

**5 Story Points**

> As an Admin, I want to view cost-per-kilometre reports so that I can analyse vehicle operating costs and make better fleet decisions.

**Total Story Points: 36**

---

## 🔐 Non-Functional Requirements

* Driver cannot be assigned to two active trips.
* Odometer values must be monotonically increasing.
* Document and licence information should be protected.
* Daily scheduled jobs should check document expiry.
* Application should be responsive for drivers using mobile devices.
* APIs should validate user input.
* Role-based access should restrict unauthorized operations.
* Important status changes should be auditable.

---

## 🏗️ System Architecture

```text
                    ┌─────────────────────┐
                    │       React UI      │
                    │  HTML/CSS/JS        │
                    └──────────┬──────────┘
                               │
                         REST API / JSON
                               │
                    ┌──────────▼──────────┐
                    │   Spring Boot API   │
                    ├─────────────────────┤
                    │ Authentication      │
                    │ Vehicle Management  │
                    │ Driver Management   │
                    │ Trip Management     │
                    │ Fuel Management     │
                    │ Maintenance         │
                    │ Reports & Alerts    │
                    └──────────┬──────────┘
                               │
                         JPA / Hibernate
                               │
                    ┌──────────▼──────────┐
                    │     PostgreSQL      │
                    └─────────────────────┘
```

---

## 🛠️ Technology Stack

### Frontend

* React.js
* JavaScript
* HTML5
* CSS3
* Bootstrap
* Axios
* Chart.js / Recharts

### Backend

* Java
* Spring Boot
* Spring Web
* Spring Data JPA
* Spring Security
* JWT
* Maven
* Bean Validation

### Database

* PostgreSQL

### Development & Testing

* Git
* GitHub
* GitHub Projects
* Postman
* JUnit
* Mockito
* IntelliJ IDEA / Eclipse / VS Code

---

## 📂 Project Structure

```text
fleet-driver-management/
│
├── backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/example/fleet/
│   │   │   │       ├── auth/
│   │   │   │       ├── vehicle/
│   │   │   │       ├── driver/
│   │   │   │       ├── trip/
│   │   │   │       ├── fuel/
│   │   │   │       ├── maintenance/
│   │   │   │       ├── report/
│   │   │   │       └── alert/
│   │   │   │
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   │
│   │   └── test/
│   │
│   └── pom.xml
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── context/
│   │   └── App.js
│   │
│   └── package.json
│
├── README.md
└── .gitignore
```

---

## 🗄️ Database Design

Main entities:

```text
app_user
role
vehicle
driver
document
trip
fuel_log
maintenance_schedule
maintenance_record
alert
```

### Main Relationships

```text
Driver ──────────── Trip
                      │
                      │
Vehicle ──────────── Trip
   │
   ├── Document
   ├── Fuel Log
   ├── Maintenance Schedule
   └── Maintenance Record
```

---

## 🔄 Trip Workflow

```text
AVAILABLE VEHICLE
        │
        ▼
TRIP CREATED
        │
        ▼
DRIVER + VEHICLE ASSIGNED
        │
        ▼
     ASSIGNED
        │
        ▼
    START TRIP
        │
        ▼
   IN PROGRESS
        │
        ▼
     END TRIP
        │
        ▼
    COMPLETED
        │
        ▼
VEHICLE AVAILABLE
```

---

## 🔧 Maintenance Workflow

```text
Vehicle
   │
   ▼
Check KM / Date
   │
   ├── Maintenance not due
   │        ↓
   │     Continue
   │
   └── Maintenance due
            ↓
       Generate Alert
            ↓
      Schedule Service
            ↓
       Vehicle Blocked
            ↓
      Service Completed
            ↓
       Vehicle Available
```

---

## 📊 Cost per Kilometre

The system calculates vehicle operating cost using trip, fuel, and maintenance data.

```text
Distance Travelled =
Ending Odometer - Starting Odometer

Total Cost =
Fuel Cost + Maintenance Cost

Cost per KM =
Total Cost / Distance Travelled
```

Example:

```text
Distance = 1,000 km
Fuel Cost = ₹9,000
Maintenance Cost = ₹3,000

Total Cost = ₹12,000

Cost per KM = ₹12,000 / 1,000
            = ₹12/km
```

---

## 🔗 Sample REST APIs

### Vehicles

```http
POST /api/v1/vehicles
GET /api/v1/vehicles
GET /api/v1/vehicles/{id}
PUT /api/v1/vehicles/{id}
DELETE /api/v1/vehicles/{id}
```

### Drivers

```http
POST /api/v1/drivers
GET /api/v1/drivers
GET /api/v1/drivers/{id}
```

### Trips

```http
POST /api/v1/trips
GET /api/v1/trips
PATCH /api/v1/trips/{id}/start
PATCH /api/v1/trips/{id}/end
```

### Fuel

```http
POST /api/v1/fuel-logs
GET /api/v1/fuel-logs
```

### Maintenance

```http
POST /api/v1/maintenance
GET /api/v1/maintenance/due
```

### Reports

```http
GET /api/v1/reports/mileage
GET /api/v1/reports/cost-per-km
```

---

## 🧩 Java Design Patterns & Features

The project uses the Java features specified in the project catalog.

### Strategy Pattern

`MaintenanceTrigger` can support different maintenance conditions:

```text
KM Based
Time Based
```

### Factory Pattern

`AlertFactory` creates alerts for different conditions:

```text
Document Expiry
Licence Expiry
Maintenance Due
```

### Builder Pattern

`TripSheet` can be constructed using the Builder pattern.

### Sealed Classes

`TripStatus` can restrict valid trip states.

```text
ASSIGNED
IN_PROGRESS
COMPLETED
CANCELLED
```

### Java Records

Records can be used for immutable DTOs.

### Streams

Java Streams can be used for:

* Mileage calculations
* Fuel summaries
* Vehicle statistics
* Cost calculations

### Scheduled Tasks

Spring `@Scheduled` can be used for daily document expiry checks.

### Feign Client

If microservices are implemented, the Trip Service can communicate with Fleet Service using OpenFeign.

---

## 🧪 Testing

The project will be tested using:

* JUnit
* Mockito
* Postman
* Frontend integration testing

Important test cases include:

* Duplicate vehicle number
* Invalid odometer value
* Driver already on active trip
* Vehicle under maintenance
* Expired documents
* Invalid fuel quantity
* Cost-per-kilometre calculation
* Unauthorized API access

---

## 📋 Definition of Done

A user story is considered **Done** when:

* [ ] React frontend is implemented.
* [ ] Spring Boot REST API is implemented.
* [ ] PostgreSQL integration is completed.
* [ ] Required validations are implemented.
* [ ] Business rules are implemented.
* [ ] Role-based access is applied.
* [ ] API is tested using Postman.
* [ ] Frontend and backend are integrated.
* [ ] Unit/integration tests pass.
* [ ] No critical bugs remain.
* [ ] Code is committed and pushed to GitHub.
* [ ] Acceptance criteria are satisfied.

---

## 📅 Development Plan

### Sprint 1

* Project setup
* Database design
* Authentication
* User roles

### Sprint 2

* Vehicle management
* Driver management

### Sprint 3

* Trip creation
* Vehicle/driver assignment

### Sprint 4

* Trip start/end
* Odometer validation

### Sprint 5

* Fuel management
* Mileage calculation

### Sprint 6

* Maintenance
* Document management
* Expiry alerts

### Sprint 7

* Reports
* Dashboard
* Cost per kilometre

### Sprint 8

* Testing
* Bug fixing
* Deployment
* Documentation
* Final demonstration

---

## 📌 Future Enhancements

* GPS-based vehicle tracking
* Google Maps integration
* Real-time vehicle location
* Email/SMS notifications
* Fuel efficiency prediction
* Driver performance analytics
* Mobile application
* Advanced fleet analytics
* Docker containerization
* Microservices deployment

---

## 👩‍💻 Project Status

**Status:** In Development

**Project Type:** Java Full Stack

**Domain:** Logistics / Transportation

**Duration:** 2 Months

**Architecture:** React + Spring Boot + PostgreSQL

---

## 📄 License

This project is developed for academic and educational purposes.
