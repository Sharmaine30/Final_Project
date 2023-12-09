# MovieMate
With its user-friendly online platform for quick ticket booking, the MovieMate movie ticket booking system modernizes movie theater operations. Encouraging movie-going experiences with comprehensive details and safe payment methods is how the system improves efficiency and revenue optimization. With a modern and effective approach to movie tickets, it seeks to slickly merge technology and entertainment.

# User Interface

* Registration/Login: New users need to register with the system by providing necessary details such as full name, email, and creating a password. Existing users can log in using their registered email and password.

* Browsing Movies: Once logged in, customers can browse the list of available movies. They can view details such as movie title, genre, release date, and price.

* Selecting Movie and Showtime: Customers choose a specific movie they want to watch. They can view the available showtimes for that movie.

* Selecting Cinema and Seats: Customers choose the preferred cinema and available seats for the selected showtime.

* Booking Tickets: After selecting seats, customers proceed to book tickets for the chosen movie, showtime, and seats.

* Payment: Customers make payment for the booked tickets using the integrated payment system. The system calculates the total amount based on the number of tickets and the movie's price.
 
* Confirmation: After successful payment, customers receive a booking confirmation with details like booking ID, movie title, showtime, and seats.

* Viewing Booking History: Customers can check their booking history to review past and upcoming movie reservations.

* Profile Management: Customers can manage their profiles, update personal information, and change passwords as needed.

* Logging Out: After completing the booking, customers can log out for security.
CREATE DATABASE MovieMate;

# Employee Interface

* Log In: Open the application and enter the employee credentials (username and password) to log in.

* Navigate to Movie Table: Instead of a dashboard, the employee directly navigates to the "Movie" section or table.

* View Movie List: Access the movie table to view a comprehensive list of all available movies, including details such as title, genre, release date, and current status.

* Check Movie Details: Select a specific movie to view detailed information like genre, release date, duration, language, description, and ticket price

* Transaction Processing: Complete the booking transaction by selecting the number of tickets, confirming seat choices, and processing the payment.

* Edit Movie Details: If there are updates to a movie's details (e.g., change in release date), the employee can access the movie table and edit relevant information.

* Delete Movie Entries: In case a movie is no longer running or has been canceled, the employee can remove the corresponding entry from the movie table.

* Customer Support: Access customer profiles, view booking history, and assist with any inquiries or issues customers may have.

* View Transaction History: Check the transaction history related to movie bookings to monitor revenue and reconcile payments.

* Log Out: Once the tasks are completed, the employee can log out of the application to secure access.

# Tables

Create the Customers table and inserting values
CREATE TABLE Customer (
    customer_id INT PRIMARY KEY,
    full_name VARCHAR(100) NOT NULL,
    password VARCHAR(50),
    email VARCHAR(100) UNIQUE
);

INSERT INTO Customer (customer_id, full_name, password, email)
VALUES
    (1, 'Sharmaine D. Abrenica', 'password123', 'sharmaineabrenica@gmail.com'),
    (2, 'Nelcy L. Cabacang', 'securepass', 'nelcycabacang@gmail.com'),
    (3, 'Clark O. Alisuag', 'bobpass', 'clarkalisuag@gmail.com'),
	(4, 'Rocky B. Porlay', 'imissu<3', 'rockyporlay@gmail.com'),
	(5, 'Alice Williams', 'alicepass', 'alicewilliams@gmail.com'),
	(6, 'Olivia Adams', 'oliviapass', 'olivia.adams@example.com'),
	(7, 'Eva Davis', 'evapass', 'evadavis@gmail.com'),
    (8, 'Frank Miller', 'frankpass', 'frankmiller@gmail.com'),
	(9, 'Grace Turner', 'gracepass', 'graceturner@gmail.com'),
    (10, 'Henry White', 'henrypass', 'henrywhite@gmail.com');

# Create the Movie table and inserting values
	
CREATE TABLE Movie (
    movie_id INT PRIMARY KEY,
    title VARCHAR(255),
    genre VARCHAR(50),
    release_date DATE, 
    duration TIME,
    language VARCHAR(50),
    description TEXT,
	price DECIMAL (8,2)
);

INSERT INTO Movie (movie_id, title, genre, release_date, duration, language, description, price)
VALUES
    (1, 'Trolls: Band Together', 'Animation, Adventure, Comedy', '2023-11-17', '01:31:00', 'English', 'Embraces the boy band era with so many references to everyone''s favorite bands.' , 312.00),
    (2, 'Marita', 'Horror', '2023-11-22', '01:46:00', 'Filipino', 'An actress commits suicide in a theatre full of people. Now she haunts the venue and those who visit.' , 312.00),
    (3, 'The Marvels', 'Action, Adventure, Fantasy', '2023-11-10', '01:45:00', 'English', 'Carol Danvers AKA Captain Marvel has reclaimed her identity from the tyrannical Kree and taken revenge on the Supreme Intelligence.', 312.00),
    (4, 'Five nights at Freddy''s', 'Horror, Mystery, Thriller', '2023-10-27', '01:49:00', 'English', 'A troubled security guard begins working at Freddy Fazbear''s Pizzeria.', 312.00),
	(5, 'Wish', 'Animation, Adventure, Comedy', '2023-11-21', '01:35:00', 'English', 'King Magnifico and his wife Queen Amaya establish the kingdom of Rosas on an island in the Mediterranean Sea.', 312.00),
    (6, 'The Hunger Games: The Ballad of Songbirds & Snakes', 'Action, Adventure, Drama', '2023-11-17', '02:37:00', 'English', 'Set 64 years before the events of the first film, its plot follows the events that lead a young Coriolanus Snow on the path to becoming the tyrannical leader of Panem, including his relationship with the Hunger Games District 12 tribute Lucy Gray Baird during the 10th Hunger Games.', 312.00),
    (7, 'Thanksgiving', 'Horror, Mystery, Thriller', '2023-11-17', '01:46:00', 'English', 'An axe-wielding maniac terrorizes residents of Plymouth, Mass., after a Black Friday riot ends in tragedy.', 312.00),
    (8, 'Freelance', 'Action, Comedy', '2023-10-27', '01:48:00', 'English', 'Stuck in a dead-end desk job, former special forces operative Mason Pettis reluctantly takes on a freelance gig to provide private security for a washed-up journalist as she interviews a ruthless dictator.', 312.00),
	(9, 'The Jack In The Box: Awakening', 'Horror', '2022-01-03', '01:33:00', 'English', 'When a vintage Jack-in-the-box is opened by a dying woman, she enters into a deal with the demon within that would see her illness cured in return for helping it claim six innocent victims.', 312.00),
    (10, 'Five Breakups and a Romance', 'Drama', '2023-10-18', '01:42:00', 'Filipino', 'Even if two people are on the opposite sides of the universe, once the connection is made, they are basically one.', 312.00);

# Create the Cinema table and inserting values

CREATE TABLE Cinema (
    cinema_id INT PRIMARY KEY,
    capacity INT,
    name VARCHAR(50)
);

INSERT INTO Cinema (cinema_id, capacity, name)
VALUES
    (1, 34, 'Cinema 1'),
    (2, 34, 'Cinema 2'),
    (3, 34, 'Cinema 3'),
	(4, 34, 'Cinema 4');
	
# Create the Show table and inserting values 

CREATE TABLE Show (
    show_id INT PRIMARY KEY,
    movie_id INT,
    cinema_id INT,
    start_time TIME,
    show_date DATE,
    FOREIGN KEY (movie_id) REFERENCES Movie(movie_id),
    FOREIGN KEY (cinema_id) REFERENCES Cinema(cinema_id)
);

INSERT INTO Show (show_id, movie_id, cinema_id, start_time, show_date)
VALUES
    (1, 1, 1, '11:45:00', '2023-11-28'),
    (2, 2, 1, '02:30:00', '2023-11-28'),
    (3, 3, 1, '04:45:00', '2023-11-28'),
    (4, 4, 2, '11:30:00', '2023-11-28'),
    (5, 5, 2, '12:30:00', '2023-11-28'),
    (6, 6, 3, '02:00:00', '2023-11-28'),
    (7, 7, 3, '01:00:00', '2023-11-28'),
    (8, 8, 3, '06:00:00', '2023-11-28'),
    (9, 9, 4, '09:00:00', '2022-11-28'),
    (10, 10, 4, '04:40:00', '2023-11-28');
	
# Create the Seat table and inserting values

CREATE TABLE Seat (
    seat_id INT PRIMARY KEY,
    cinema_id INT,
    seat_number VARCHAR(10),
    availability VARCHAR(10),
    FOREIGN KEY (cinema_id) REFERENCES Cinema(cinema_id)
);

INSERT INTO Seat (seat_id, cinema_id, seat_number, availability)
VALUES
    (1, 1, 'A1', 'Available'),
    (2, 1, 'A2', 'Available'),
    (3, 1, 'A3', 'Available'),
    (4, 1, 'A4', 'Available'),
    (5, 1, 'A5', 'Available'),
    (6, 1, 'A6', 'Available'),
    (7, 1, 'B1', 'Available'),
    (8, 1, 'B2', 'Available'),
    (9, 1, 'B3', 'Available'),
    (10, 1, 'B4', 'Available'),
    (11, 1, 'B5', 'Booked'),
    (12, 1, 'B6', 'Booked'),
    (13, 1, 'C1', 'Available'),
    (14, 1, 'C2', 'Available'),
    (15, 1, 'C3', 'Available'),
    (16, 1, 'C4', 'Available'),
    (17, 1, 'C5', 'Booked'),
    (18, 1, 'C6', 'Booked'),
    (19, 1, 'D1', 'Available'),
    (20, 1, 'D2', 'Available'),
    (21, 1, 'D3', 'Available'),
    (22, 1, 'D4', 'Booked'),
    (23, 1, 'D5', 'Available'),
    (24, 1, 'D6', 'Available'),
    (25, 1, 'E1', 'Available'),
    (26, 1, 'E2', 'Available'),
    (27, 1, 'E3', 'Available'),
    (28, 1, 'E4', 'Available'),
    (29, 1, 'E5', 'Available'),
    (30, 1, 'E6', 'Available'),
    (31, 1, 'F1', 'Available'),
    (32, 1, 'F2', 'Available'),
    (33, 1, 'F3', 'Available'),
    (34, 1, 'F4', 'Available'),
	(35, 2, 'A1', 'Available'),
    (36, 2, 'A2', 'Available'),
    (37, 2, 'A3', 'Available'),
    (38, 2, 'A4', 'Available'),
    (39, 2, 'A5', 'Available'),
    (40, 2, 'A6', 'Available'),
    (41, 2, 'B1', 'Available'),
    (42, 2, 'B2', 'Available'),
    (43, 2, 'B3', 'Available'),
    (44, 2, 'B4', 'Available'),
    (45, 2, 'B5', 'Booked'),
    (46, 2, 'B6', 'Booked'),
    (47, 2, 'C1', 'Available'),
    (48, 2, 'C2', 'Available'),
    (49, 2, 'C3', 'Available'),
    (50, 2, 'C4', 'Available'),
    (51, 2, 'C5', 'Booked'),
    (52, 2, 'C6', 'Booked'),
    (53, 2, 'D1', 'Available'),
    (54, 2, 'D2', 'Available'),
    (55, 2, 'D3', 'Available'),
    (56, 2, 'D4', 'Booked'),
    (57, 2, 'D5', 'Available'),
    (58, 2, 'D6', 'Available'),
    (59, 2, 'E1', 'Available'),
    (60, 2, 'E2', 'Available'),
    (61, 2, 'E3', 'Available'),
    (62, 2, 'E4', 'Available'),
    (63, 2, 'E5', 'Available'),
    (64, 2, 'E6', 'Available'),
    (65, 2, 'F1', 'Available'),
    (66, 2, 'F2', 'Available'),
    (67, 2, 'F3', 'Available'),
    (68, 2, 'F4', 'Available');
	
# Create the Booking table and inserting values

CREATE TABLE Booking (
    booking_id INT PRIMARY KEY,
    user_id INT,
    show_id INT,
	seat_id INT,
	employee_id INT,
    booking_date DATE,
    price DECIMAL(8, 2),
    FOREIGN KEY (user_id) REFERENCES Customer(customer_id),
    FOREIGN KEY (show_id) REFERENCES Show(show_id),
	FOREIGN KEY (seat_id) REFERENCES Seat(seat_id),
	FOREIGN KEY (employee_id) REFERENCES Employee (employee_id)
);

INSERT INTO Booking (booking_id, user_id, show_id, seat_id, employee_id, booking_date, price)
VALUES
    (1, 1, 1, 1, 1, '2023-11-24', 312.00),
    (2, 2, 1, 24, 1, '2023-11-28', 312.00),
    (3, 3, 1, 11, 1, '2023-11-25', 312.00),
    (4, 3, 1, 12, 1, '2023-11-25', 312.00),
    (5, 3, 1, 17, 1, '2023-11-25', 312.00),
    (6, 3, 1, 18, 2, '2023-11-25', 312.00),
    (7, 7, 7, 45, 2, '2023-11-08', 312.00),
    (8, 8, 8, 46, 2, '2023-11-14', 312.00),
    (9, 9, 9, 50, 2, '2022-01-02', 312.00),
    (10, 10, 10, 52, 2, '2023-10-16', 312.00);
	
# Create the Transaction table and inserting values	

CREATE TABLE Transaction (
    transaction_id INT PRIMARY KEY,
    user_id INT,
	movie_id INT,
    no_of_tickets INT,
    amount DECIMAL(10, 2),
    transaction_date DATE,
    FOREIGN KEY (user_id) REFERENCES Customer(customer_id),
	FOREIGN KEY (movie_id) REFERENCES Movie(movie_id)
);

INSERT INTO Transaction (transaction_id, user_id, movie_id, no_of_tickets, amount, transaction_date)
VALUES
    (1, 2, 1, 1, 312.00, '2023-11-25'),
    (2, 3, 1, 4, 1248.00, '2023-11-26'),
    (3, 1, 1, 1, 312.00, '2023-11-28'),
    (4, 4, 2, 4, 1248.00, '2023-11-30'),
    (5, 5, 3, 2, 624.00, '2023-11-30'),
    (6, 6, 4, 5, 1560.00, '2023-11-30'),
    (7, 7, 5, 3, 936.00, '2023-12-01'),
    (8, 8, 6, 2, 624.00, '2023-12-01'),
    (9, 9, 7, 1, 312.00, '2022-12-02'),
    (10, 8, 10, 3, 936.00, '2023-12-03');
	
# Create the Employee table and inserting values

CREATE TABLE Employee (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(100),
    employee_password VARCHAR(100),
    employee_email VARCHAR(100) UNIQUE
 
);

    INSERT INTO Employee (employee_id, employee_name, employee_password, employee_email)
VALUES
    (1, 'Admin', 'admin_password', 'admin@gmail.com'),
    (2, 'John Smith', 'john_password', 'john.smith@gmail.com'),
    (3, 'Emily Johnson', 'emily_password', 'emily.johnson@gmail.com'),
    (4, 'Michael Davis', 'michael_password', 'michael.davis@gmail.com'),
    (5, 'Sarah Brown', 'sarah_password', 'sarah.brown@gmail.com'),
    (6, 'Robert Wilson', 'robert_password', 'robert.wilson@gmail.com'),
    (7, 'Jennifer Miller', 'jennifer_password', 'jennifer.miller@gmail.com'),
    (8, 'David Taylor', 'david_password', 'david.taylor@gmail.com'),
    (9, 'Matthew Turner', 'matthew_password', 'matthew.turner@gmail.com'),
    (10, 'Laura Evans', 'laura_password', 'laura.evans@gmail.com');

# SELECT Statements

	 SELECT * FROM Customer
	 SELECT * FROM Movie
	 SELECT * FROM Cinema
	 SELECT * FROM Show
	 SELECT * FROM Booking
	 SELECT * FROM Seat
	 SELECT * FROM Transaction
	 SELECT * FROM Employee

 # Queries for different features
* Login as Customer
SELECT customer_id
FROM customer
WHERE email = 'sharmaineabrenica@gmail.com' AND password = 'password123';

* List of movies
SELECT movie_id, title, genre, release_date, duration, language, description, price
FROM Movie;

* Movie Details by movie_id
SELECT title, genre, release_date, duration, language, description
FROM Movie
WHERE movie_id = 1;

* Showtimes for a specific movie
SELECT Cinema.name AS cinema_name, Show.start_time, Show.show_date
FROM Show
INNER JOIN Cinema ON Show.cinema_id = Cinema.cinema_id
WHERE Show.movie_id = 1;

* Booking 
SELECT Seat.seat_number, Seat.availability
FROM Seat
WHERE Seat.cinema_id = 1
  AND Seat.seat_number NOT IN (
      SELECT Seat.seat_number
      FROM Booking
      INNER JOIN Show ON Booking.show_id = Show.show_id
      INNER JOIN Seat ON Booking.seat_id = Seat.seat_id
      WHERE Show.movie_id = 1
        AND Show.cinema_id = 1);
		
* Search
- By Movie Title
SELECT *
FROM Movie
WHERE title LIKE CONCAT('%The Marvels');

- By Genre
SELECT * FROM Movie
WHERE genre LIKE CONCAT('%Horror');

- By Language
SELECT * FROM Movie
WHERE language LIKE CONCAT('%English');

- By Release Date
SELECT * FROM Movie
WHERE release_date BETWEEN '2023-01-01' AND '2023-12-31';

* Booking History
SELECT Booking.booking_id, Movie.title, Show.show_date, Show.start_time, Booking.price
FROM Booking
INNER JOIN Show ON Booking.show_id = Show.show_id
INNER JOIN Movie ON Show.movie_id = Movie.movie_id
WHERE Booking.user_id = 1;

* Displaying Customer information
SELECT full_name, email, password
FROM Customer
WHERE customer_id = 1;

- Updating their information
UPDATE Customer
SET email = 'sharnewemail@gmail.com', 
    full_name = 'Shar Abrenica', 
    password = '033004'
WHERE customer_id = 1;

* Login as Admin or Employee
SELECT employee_id
FROM employee 
WHERE employee_email = 'admin@gmail.com' AND employee_password = 'admin_password';


* Movie List
  - Retrieve All Movies
SELECT title, genre, release_date, duration, language, description
FROM Movie;
  - To edit movie list
UPDATE Movie
SET
    title = 'New Movie Title',
    description = 'New movie description'
WHERE
    movie_id = 5;

 - To delete a movie
DELETE FROM Movie
WHERE movie_id = 10

 - To add a movie
INSERT INTO Movie (title, genre, release_date, duration, language, description, price)
VALUES
    ('Another Movie', 'Drama, Romance', '2023-12-15', '01:45:00', 'English', 'A beautiful love story.', 299.99);

* Schedules
SELECT
    Movie.title AS movie_title,
    Show.show_date AS show_date,
    Cinema.name AS cinema_name,
    Show.start_time AS show_time
FROM
    Show
JOIN Movie ON Show.movie_id = Movie.movie_id
JOIN Cinema ON Show.cinema_id = Cinema.cinema_id;

 - Adding Schedules
INSERT INTO Show (movie_id, cinema_id, start_time, show_date)
VALUES
    (1, 1, '14:30:00', '2023-12-20');
	
 - Updating a schedule
UPDATE Show
SET
    start_time = '15:00:00',
    show_date = '2023-12-21'
WHERE
    show_id = 6;

 - Deleting a Show Schedule
DELETE FROM Show
WHERE show_id = 8;

* Transactions
SELECT
    Transaction.transaction_id,
    Customer.full_name AS customer_name,
    Movie.title AS movie_title,
    Transaction.amount,
    Transaction.transaction_date AS date_of_purchase,
    Employee.employee_name AS employee_name
FROM
    Transaction
JOIN
    Customer ON Transaction.user_id = Customer.customer_id
JOIN
    Movie ON Transaction.movie_id = Movie.movie_id
JOIN
    Booking ON Transaction.user_id = Booking.user_id
JOIN
    Employee ON Booking.employee_id = Employee.employee_id;

* Customer
 - Retrieve all customers
SELECT * FROM Customer;

 - Update customer information
UPDATE Customer
SET full_name = 'Updated Name', email = 'updatedemail@example.com'
WHERE customer_id = customer_id_to_update;

 - Delete a customer
DELETE FROM Customer WHERE customer_id = customer_id_to_delete;
