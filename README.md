Restaurant Review System

This is a simple restaurant review system implemented in Python using the SQLAlchemy library for database management. The system allows users to create restaurants, customers, and reviews, and provides functionality to perform operations like adding reviews, finding the favorite restaurant of a customer, deleting reviews, and identifying the fanciest restaurant.
Installation

    Clone the repository:

    bash

git clone https://github.com/hazelnjoki/restaurant-review-system.git
cd restaurant-review-system

Install the required dependencies:

bash

pip install -r requirements.txt

Run the script:

bash

    python restaurant_review_system.py

Features
Classes
1. Restaurant

    Represents a restaurant entity.
    Attributes:
        id: Primary key.
        name: Name of the restaurant.
        price: Price level of the restaurant.
    Relationships:
        reviews: One-to-Many relationship with the Review class.
        customers: Many-to-Many relationship with the Customer class through the reviews association table.
    Class methods:
        fanciest(): Retrieve the fanciest restaurant based on the price level.

2. Customer

    Represents a customer entity.
    Attributes:
        id: Primary key.
        first_name: First name of the customer.
        last_name: Last name of the customer.
    Relationships:
        reviews: One-to-Many relationship with the Review class.
        restaurants: Many-to-Many relationship with the Restaurant class through the reviews association table.
    Methods:
        full_name(): Return the full name of the customer.
        favorite_restaurant(): Return the favorite restaurant of the customer based on the highest-rated review.
        add_review(restaurant, rating): Add a new review for a restaurant with a specified rating.
        delete_reviews(restaurant): Delete all reviews for a specific restaurant.

3. Review

    Represents a review entity.
    Attributes:
        id: Primary key.
        star_rating: Rating given in the review.
    Relationships:
        restaurant: Many-to-One relationship with the Restaurant class.
        customer: Many-to-One relationship with the Customer class.
    Methods:
        full_review(): Return a formatted string representing the full review.

Usage

The system can be used to create, manage, and query restaurants, customers, and reviews. Examples of usage can be found in the if __name__ == "__main__": block at the end of the script.
Database

The system uses SQLite as the database, and the database file is named cutetime.db.
Contributing

Feel free to contribute to the project by opening issues or submitting pull requests.
License

This project is licensed under the MIT License - see the LICENSE file for details.
