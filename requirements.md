%% Airbnb ERD -
erDiagram
    USER {
        int user_id PK
        string first_name
        string last_name
        string email UNIQUE
        string password_hash
        string phone_number
        string role
        datetime created_at
    }

    PROPERTY {
        int property_id PK
        int host_id FK
        string name
        string description
        string location
        decimal price_per_night
        int max_guests
        datetime created_at
        datetime updated_at
    }

    BOOKING {
        int booking_id PK
        int property_id FK
        int user_id FK
        date start_date
        date end_date
        decimal total_price
        string status
        datetime created_at
    }

    PAYMENT {
        int payment_id PK
        int booking_id FK
        decimal amount
        datetime payment_date
        string payment_method
        string status
    }

    REVIEW {
        int review_id PK
        int property_id FK
        int user_id FK
        int rating
        string comment
        datetime created_at
    }

    MESSAGE {
        int message_id PK
        int sender_id FK
        int recipient_id FK
        string message_body
        datetime sent_at
    }

    %% relations
    USER ||--o{ PROPERTY : "hosts"
    USER ||--o{ BOOKING : "books"
    PROPERTY ||--o{ BOOKING : "has"
    BOOKING ||--o{ PAYMENT : "pays"
    USER ||--o{ REVIEW : "writes"
    PROPERTY ||--o{ REVIEW : "receives"
    USER ||--o{ MESSAGE : "sends"
    USER ||--o{ MESSAGE : "receives"
