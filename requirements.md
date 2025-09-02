+-----------+        +------------+        +----------+
|   User    |        |   Property |        |  Booking |
+-----------+        +------------+        +----------+
| user_id   |        | property_id|        | booking_id|
| first_name|        |   host_id  |        | property_id|
|  last_name|        |     name   |        |   user_id |
|    email  |        | description|        | start_date|
| password_hash|     |  location  |        |  end_date |
| phone_number|     | pricepernight|       | total_price|
|     role   |        | created_at |        |   status  |
| created_at |        | updated_at |        | created_at|
+-----------+        +------------+        +----------+
     |                      |                     |
     |                      |                     |
     |                      |                     |
+----------+        +------------+        +----------+
|  Payment |        |   Review   |        |  Message  |
+----------+        +------------+        +----------+
| payment_id|        |  review_id |        | message_id|
| booking_id|        | property_id|        |  sender_id|
|   amount  |        |   user_id  |        | recipient_id|
|payment_date|       |   rating   |        | message_body|
|payment_method|     |   comment  |        |   sent_at |
+----------+        | created_at  |        +----------+
                    +------------+