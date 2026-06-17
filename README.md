# Airline Management System

A PostgreSQL database project built as part of our DBMS coursework at DA-IICT. Models core airline operations — flights, bookings, crew, maintenance, and reviews.

## Files

```
├── DDL_Script.sql       # table definitions
├── Sample_Data.sql      # sample INSERT records
├── Queries.sql          # 15 SQL queries
└── ER_Diagram.pdf       # entity-relationship diagram
```

## Schema

11 tables covering users, airports, aircraft, flights, crew, bookings, tickets, reviews, and maintenance.

A few design choices worth noting:
- `User` splits into `Guest_User` and `Registered_User` to avoid storing null passport numbers for guests
- `Review` uses a composite PK `(user_id, flight_id)` so each user can review a flight only once
- `Booking` and `Ticket` are separate — booking is intent, ticket is confirmation after payment

## Setup

```bash
psql -U postgres -f DDL_Script.sql -f Sample_Data.sql
```

Then open `Queries.sql` to run the queries.
