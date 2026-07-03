# Software Requirements Specification (SRS)
## Project: Warehouse Inventory & Logistics Management System

---

## 1. System Overview
The Warehouse Inventory & Logistics System is a Java Spring Boot REST API designed to automate stock tracking, warehouse bin management, and supply chain updates. The system ensures data persistence through a relational database and is optimized for cloud deployment.

---

## 2. Functional Requirements & API Mapping

Your team will implement full CRUD capabilities matching the four core HTTP methods required by the assignment:

### 📦 Inventory Management (CRUD)
*   **FR-1 (Read - GET):** The system must allow users to view current warehouse stock levels, filter items by SKU, or check specific bin locations.
*   **FR-2 (Create - POST):** Warehouse staff must be able to log incoming shipments and add new product variants to the system.
*   **FR-3 (Update - PUT):** The system must allow real-time updates to stock quantities when items are picked, packed, or relocated within the warehouse.
*   **FR-4 (Delete - DELETE):** Authorized managers must be able to remove defective, expired, or discontinued product entries from the database.

---

## 3. Scheduled Background Tasks (Automation)

To satisfy the requirement of having at least two independent automated tasks, the system runs the following background routines:

*   **FR-5 (Task 1 - Low Stock Sweeper):** A scheduled routine that runs automatically at a set interval to sweep the database for any inventory items falling below their defined safety threshold, generating a system alert log.
*   **FR-6 (Task 2 - Automated External Broadcast):** A second automated task that compiles a summary of daily warehouse activity (e.g., total items processed) and pushes/simulates an update to an external endpoint or social platform (like X.com) to notify stakeholders.

---

## 4. Non-Functional & Deployment Requirements

*   **NFR-1 (Database Persistence):** All inventory states, product metadata, and warehouse logs must be written to and read from a persistent relational database, ensuring data survives application restarts.
*   **NFR-2 (Cloud Infrastructure):** The application must be containerized or packaged as an executable JAR capable of running live on **Google Cloud Platform** or **DigitalOcean**.
