# airbnb-clone-project
AirBnB Clone project ProDev Backend


Team Roles

Backend Developer
Responsible for building and maintaining the server-side logic, APIs, and database interactions. Ensures that the application functions correctly, efficiently, and securely.

Frontend Developer
Handles the user interface and user experience. Implements the design, ensures responsiveness, and connects the front end to backend APIs.

Database Administrator (DBA)
Manages the database structure, ensures data integrity, performance, and security. Designs schemas and oversees backups and migrations.

DevOps Engineer
Responsible for CI/CD pipelines, deployment, and server infrastructure. Ensures smooth integration, automated testing, and reliable deployment processes.

Project Manager
Coordinates tasks, timelines, and communication between team members. Ensures that the project stays on track and meets milestones.

Quality Assurance (QA) Engineer
Tests features for bugs, functionality, and usability. Ensures that the project meets quality standards before release.

Technology Stack

Django – A high-level Python web framework used to build the backend logic, RESTful APIs, and manage server-side operations efficiently.

PostgreSQL – A powerful, open-source relational database system used to store and manage all application data securely.

GraphQL– A query language for APIs that allows clients to request only the data they need, improving performance and flexibility.

HTML/CSS/JavaScript – Used for creating and styling the frontend interface, ensuring a responsive and user-friendly experience.

Docker– A containerization tool used to create consistent development and deployment environments across systems.

Git & GitHub – Used for version control, collaboration, and continuous integration.

GitHub Actions – Automates testing and deployment processes within the CI/CD pipeline.


Database Design

The database for the AirBnB Clone project is designed to manage users, property listings, bookings, reviews, and payments efficiently. It follows a relational model using **PostgreSQL**.

Key Entities and Relationships

1. User
Represents registered users who can list properties or make bookings.  
- `id` (Primary Key)  
- `name`  
- `email`  
- `password` (hashed)  
- `role` (e.g., host or guest)  
> A user can list multiple properties and make multiple bookings.

2. Property
Represents an accommodation listed by a host.  
- `id` (Primary Key)  
- `user_id` (Foreign Key to User)  
- `title`  
- `description`  
- `price_per_night`  
- `location`  
> A property belongs to one user (host) but can have many bookings and reviews.

3. Booking
Represents a reservation made by a user for a property.  
- `id` (Primary Key)  
- `user_id` (Foreign Key to User)  
- `property_id` (Foreign Key to Property)  
- `check_in_date`  
- `check_out_date`  
- `total_price`  
> A booking belongs to one user and one property.

4. Review
Represents feedback left by a guest about a property.  
- `id` (Primary Key)  
- `user_id` (Foreign Key to User)  
- `property_id` (Foreign Key to Property)  
- `rating` (1–5)  
- `comment`  
> A property can have multiple reviews, each written by different users.

5. Payment
Represents transactions for bookings.  
- `id` (Primary Key)  
- `booking_id` (Foreign Key to Booking)  
- `amount`  
- `payment_method`  
- `status` (e.g., pending, completed)  
> Each payment is linked to one booking.

Relationships Summary
- One User → Many Properties 
- One User → Many Bookings  
- One Property → Many Bookings
- One Property → Many Reviews
- One Booking → One Payment

Feature Breakdown

User Management
Allows users to sign up, log in, and manage their profiles. Handles authentication and differentiates between hosts and guests.

Property Management
Hosts can list new properties, update details, and manage availability. Includes functionality for adding images, pricing, and location details.

Booking System
Enables guests to search for properties, check availability, and make bookings. The system prevents double bookings and calculates total price based on stay duration.

Review System
Allows guests to leave reviews and ratings for properties after their stay. Helps maintain trust and transparency among users.

Payment Integration
Handles secure payments for bookings. Tracks payment status and ensures that transactions are completed safely.

Search and Filter
Provides users with search and filtering options (e.g., by location, price, or property type) for a better user experience.

API Security

Security is a critical part of the Airbnb Clone project to protect user data and ensure safe transactions.

Authentication: Verifies user identity using secure login credentials or tokens (e.g., JWT). Prevents unauthorized access.

Authorization: Ensures users can only perform actions allowed by their role (e.g., guests can’t edit other users’ properties).

Data Encryption: Protects sensitive information like passwords and payment data both in storage and during transfer.

Rate Limiting: Prevents abuse by limiting the number of API requests from a single source within a time frame.

Validation and Sanitization: Ensures all input data is clean and secure, preventing SQL injection or cross-site scripting attacks.

CI/CD Pipeline

The project uses Continuous Integration and Continuous Deployment (CI/CD) to automate testing, building, and deployment.

CI/CD ensures that code changes are tested automatically and deployed quickly without manual steps.
This helps maintain project stability and improves collaboration among developers.

Tools Used:

GitHub Actions for automation of builds and tests

Docker for consistent deployment environments

Git for version control and collaboration





