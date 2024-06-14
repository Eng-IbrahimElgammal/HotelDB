# HotelDB - Hotel Management Database with MongoDB

## Overview

HotelDB is a comprehensive hotel management database system developed using MongoDB. It features collections for Rooms, Guests, Employees, Services, and Rooster (event scheduling). The project ensures efficient data organization and retrieval.

## Requirements

- MongoDB installed and running on localhost.
- Python 3.x installed.

## Setup

1. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/your-username/HotelDB.git
    ```

2. Navigate to the cloned directory:

    ```bash
    cd HotelDB
    ```

3. Install the required Python packages:

    ```bash
    pip install pymongo
    ```

4. Import the JSON files into your MongoDB database:

    ```bash
    mongoimport --db HotelDB --collection Rooms --file Rooms.json
    mongoimport --db HotelDB --collection Guests --file Guests.json
    mongoimport --db HotelDB --collection Employees --file Employees.json
    mongoimport --db HotelDB --collection Services --file Services.json
    mongoimport --db HotelDB --collection Rooster --file Rooster.json
    ```

## Usage

1. Ensure that MongoDB is running.
2. Interact with the database using MongoDB queries or a Python script to manage and retrieve data efficiently.

## Collections

- **Rooms:** Contains room details such as room number, type, availability, price, and amenities.
- **Guests:** Stores guest information including name, contact details, and stay duration.
- **Employees:** Includes employee details such as name, position, contact, and work schedule.
- **Services:** Lists services offered by the hotel, including service name, description, and cost.
- **Rooster:** Manages event scheduling with event names, dates, times, and locations.

## Example

Querying the Rooms collection for available rooms:

```python
from pymongo import MongoClient

client = MongoClient("mongodb://localhost:27017/")
db = client['HotelDB']
rooms = db['Rooms']

available_rooms = rooms.find({"available": True})
for room in available_rooms:
    print(room)
```
## Contribution
Contributions are welcome! Feel free to submit issues, feature requests, or pull requests to improve this project.
## License
This project is licensed under the MIT License.
