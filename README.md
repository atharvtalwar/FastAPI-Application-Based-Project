# Campus Event Reservation API

A FastAPI-based REST API for managing campus events and student seat reservations. The application allows users to create, view, update, and delete events, make reservations, check seat availability, and cancel reservations.

The project uses SQLite for database storage and SQLModel for database models and operations.

## Technologies Used

* Python
* FastAPI
* SQLModel
* SQLite
* Uvicorn
* Pydantic / Email Validation
* REST API
* Swagger UI

## Installation

1. Make sure Python is installed.

2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Start the FastAPI application:

```bash
uvicorn main:app --reload
```

## Swagger UI

After starting the application, open:

```text
http://127.0.0.1:8000/docs
```

The Swagger UI can be used to test all available API endpoints.

## Available Endpoints

### Event Endpoints

**POST `/events`**
Creates a new campus event.

**GET `/events`**
Returns a list of all events.

**GET `/events/{event_id}`**
Returns details of a specific event using its ID.

**PUT `/events/{event_id}`**
Updates an existing event. The capacity cannot be reduced below the number of existing reservations.

**DELETE `/events/{event_id}`**
Deletes an event and its associated reservations.

### Reservation Endpoints

**POST `/events/{event_id}/reserve`**
Creates a reservation for an event. It checks that the event exists, is open, and has available seats before creating the reservation.

**GET `/events/{event_id}/reservations`**
Returns all reservations made for a particular event.

**DELETE `/reservations/{reservation_id}`**
Cancels an existing reservation.

**GET `/events/{event_id}/availability`**
Returns the total capacity, number of booked seats, and remaining seats for an event.

## Database

The application uses SQLite. The database file is:

```text
event_reservation.db
```

Database tables are created automatically when the FastAPI application starts.

## Project Structure

```text
campus-event-reservation-api/
│
├── main.py
├── requirements.txt
├── event_reservation.db
├── README.md
├── .gitignore
│
└── screenshots/
    ├── 01.Post-event.png.png
    ├── 02.Get-Events.png.png
    ├── 03.Get-events_id.png.png
    ├── 04.Reservation Successful.png
    ├── 05. Event Availability.png
    ├── 06. No Seats Available.png
    ├── 07.Get Event Reservations.png
    ├── 08.Reservation Cancelled.png
    └── 09.Event Deleted.png
```

# Campus Lost & Found API

A FastAPI-based REST API for managing lost and found items on a college campus. The application allows users to report items, view item details, update item information, delete reports, and filter items by status or category.

The project uses SQLite for database storage and SQLModel for database models and operations.

## Technologies Used

* Python
* FastAPI
* SQLModel
* SQLite
* Uvicorn
* REST API
* Swagger UI

## Installation

1. Make sure Python is installed.

2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Start the FastAPI application:

```bash
uvicorn main:app --reload
```

## Swagger UI

After starting the application, open:

```text
http://127.0.0.1:8000/docs
```

The Swagger UI can be used to test all available API endpoints.

## Available Endpoints

### Item Endpoints

**POST `/items`**
Creates a new lost or found item report.

**GET `/items`**
Returns all reported items.

**GET `/items/{item_id}`**
Returns details of a specific item using its ID.

**PUT `/items/{item_id}`**
Updates the details and status of an existing item.

**DELETE `/items/{item_id}`**
Deletes an item report.

### Filter Endpoints

**GET `/items/status/{status}`**
Returns items filtered by status such as `Lost`, `Found`, or `Returned`.

**GET `/items/category/{category}`**
Returns items filtered by their category.

## Database

The application uses SQLite. The database file is:

```text
database.db
```

Database tables are created automatically when the FastAPI application starts.

## Project Structure

```text
campus-lost-found-api/
│
├── main.py
├── requirements.txt
├── database.db
├── README.md
├── .gitignore
│
└── Screenshots/
    ├── 01-post-item.png.png
    ├── 02-get-items.png.png
    ├── 03-get-item-by-id.png.png
    ├── 04-put-item.png.png
    ├── 05-delete-item.png.png
    ├── 06-status-filter.png.png
    ├── 07-category-filter.png.png
    └── 08-validation-error.png.png
```
