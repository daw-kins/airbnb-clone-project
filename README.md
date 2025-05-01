# airbnb-clone-project
#The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security.

## Team Roles
### Backend Developer
Responsible for building the server-side logic, APIs, and database interactions. Ensures data is processed correctly and securely.

### Frontend Developer
Implements the user interface based on the design. Works closely with the UI/UX Designer and connects frontend components to backend APIs.

### Database Administrator (DBA)
Manages database setup, performance, backups, and security. Ensures data is structured efficiently and is accessible to the backend.

### Project Manager
Oversees the project timeline, team coordination, and communication. Ensures that milestones are met and tasks are aligned with project goals.

### QA Engineer
Tests the software to identify bugs and verify functionality. Works to ensure the final product meets quality standards.

### UI/UX Designer
Designs intuitive and appealing user interfaces. Focuses on user experience, usability, and layout of the application.

### DevOps Engineer
Manages the deployment pipeline, infrastructure, and automation tools. Ensures continuous integration and delivery (CI/CD) is in place.


## Technology Stack

- **Django**: A high-level Python web framework used to build robust and scalable backend APIs. It supports rapid development and clean, pragmatic design, making it ideal for RESTful services.

- **MySQL**: A widely-used open-source relational database management system used for storing, retrieving, and managing structured application data.

- **Docker**: A containerization platform that allows the application and its services to run in isolated environments, ensuring consistency across different development and production setups.

- **GitHub Actions**: A CI/CD tool integrated with GitHub used to automate workflows such as testing, building, and deploying the backend application. It helps maintain code quality and streamline the release process.

- **CI/CD (Continuous Integration/Continuous Deployment)**: A development practice integrated using tools like GitHub Actions to automatically build, test, and deploy code, ensuring frequent and reliable software delivery.

- **Security Best Practices**: Backend development incorporates security considerations such as authentication, data validation, encryption, and protection against common web vulnerabilities (e.g., SQL injection, XSS).

- **Database Design**: Proper schema design and normalization are applied to ensure efficient data storage, retrieval, and relationships between entities.

## Database Design

The database is designed to support core features such as user authentication, property listings, bookings, payments, and user-generated reviews. Below are the main entities and their key fields:

### Users
- `id` (Primary Key)
- `name`
- `email`
- `password_hash`
- `is_host` (Boolean to differentiate between guests and property owners)

### Properties
- `id` (Primary Key)
- `user_id` (Foreign Key → Users)
- `title`
- `description`
- `location`
- `price_per_night`

### Bookings
- `id` (Primary Key)
- `user_id` (Foreign Key → Users)
- `property_id` (Foreign Key → Properties)
- `start_date`
- `end_date`
- `status` (e.g., pending, confirmed, cancelled)

### Reviews
- `id` (Primary Key)
- `user_id` (Foreign Key → Users)
- `property_id` (Foreign Key → Properties)
- `rating` (e.g., 1–5 stars)
- `comment`

### Payments
- `id` (Primary Key)
- `booking_id` (Foreign Key → Bookings)
- `amount`
- `payment_method`
- `payment_status` (e.g., paid, refunded, pending)

### Entity Relationships
- A **User** can list multiple **Properties** (if they are a host).
- A **User** can make multiple **Bookings**.
- A **Booking** belongs to one **Property** and one **User**.
- A **Review** is written by a **User** for a **Property**.
- A **Payment** is linked to a specific **Booking**.

