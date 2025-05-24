-- phpMyAdmin SQL Dump
-- version 5.2.1
-- https://www.phpmyadmin.net/
--
-- Host: 127.0.0.1
-- Generation Time: May 24, 2025 at 08:03 PM
-- Server version: 10.4.32-MariaDB
-- PHP Version: 8.2.12

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `galactic_rentals_db`
--

-- --------------------------------------------------------

--
-- Table structure for table `rentals`
--

CREATE TABLE `rentals` (
  `rental_id` int(11) NOT NULL,
  `customer` varchar(50) NOT NULL CHECK (`customer` <> ''),
  `costume` varchar(50) NOT NULL CHECK (`costume` <> ''),
  `rent_date` datetime NOT NULL,
  `return_date` datetime DEFAULT NULL CHECK (`return_date` is null or `return_date` >= `rent_date`),
  `daily_rate` decimal(10,2) NOT NULL CHECK (`daily_rate` > 0),
  `created_at` timestamp NOT NULL DEFAULT current_timestamp(),
  `updated_at` timestamp NOT NULL DEFAULT current_timestamp() ON UPDATE current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

--
-- Dumping data for table `rentals`
--

INSERT INTO `rentals` (`rental_id`, `customer`, `costume`, `rent_date`, `return_date`, `daily_rate`, `created_at`, `updated_at`) VALUES
(1, 'Alice Johnson', 'Imperial Officer', '2025-04-01 10:00:00', '2025-04-03 15:30:00', 25.00, '2025-05-24 16:21:08', '2025-05-24 16:21:08'),
(2, 'Bob Smith', 'Galaxy Explorer', '2025-04-02 09:15:00', '2025-04-05 11:00:00', 30.00, '2025-05-24 16:21:08', '2025-05-24 16:21:08'),
(3, 'Carol Lee', 'Time Traveler', '2025-04-05 14:45:00', '2025-04-06 16:00:00', 20.00, '2025-05-24 16:21:08', '2025-05-24 16:21:08'),
(4, 'Dave Martinez', 'Robot Droid', '2025-04-07 13:00:00', '2025-04-12 13:00:00', 28.50, '2025-05-24 16:21:08', '2025-05-24 16:21:08'),
(5, 'Eva Wang', 'Alien Monarch', '2025-04-10 12:10:00', '2025-04-11 18:20:00', 22.00, '2025-05-24 16:21:08', '2025-05-24 16:21:08'),
(6, 'Frank Davis', 'Imperial Officer', '2025-04-12 08:00:00', '2025-04-15 09:00:00', 25.00, '2025-05-24 16:21:08', '2025-05-24 16:21:08'),
(7, 'Grace Kim', 'Galaxy Explorer', '2025-04-15 10:20:00', '2025-04-17 12:35:00', 30.00, '2025-05-24 16:21:08', '2025-05-24 16:21:08'),
(8, 'Henry Brown', 'Robot Droid', '2025-04-18 11:00:00', '2025-04-19 14:15:00', 28.50, '2025-05-24 16:21:08', '2025-05-24 16:21:08'),
(9, 'Isabel Clark', 'Time Traveler', '2025-04-20 09:30:00', '2025-04-23 10:00:00', 20.00, '2025-05-24 16:21:08', '2025-05-24 16:21:08'),
(10, 'John Doe', 'Alien Monarch', '2025-04-22 14:00:00', NULL, 22.00, '2025-05-24 16:21:08', '2025-05-24 16:21:08');

--
-- Triggers `rentals`
--
DELIMITER $$
CREATE TRIGGER `validate_rent_date_before_insertion` BEFORE INSERT ON `rentals` FOR EACH ROW BEGIN -- Start definning body for the trigger
	IF NEW.rent_date > NOW() THEN
    	SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'Rent date cannot be in the future';
    END IF;
END
$$
DELIMITER ;
DELIMITER $$
CREATE TRIGGER `validate_rent_date_before_update` BEFORE UPDATE ON `rentals` FOR EACH ROW BEGIN
    IF NEW.rent_date > NOW() THEN
        SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'Rent date cannot be in the future';
    END IF;
END
$$
DELIMITER ;

--
-- Indexes for dumped tables
--

--
-- Indexes for table `rentals`
--
ALTER TABLE `rentals`
  ADD PRIMARY KEY (`rental_id`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `rentals`
--
ALTER TABLE `rentals`
  MODIFY `rental_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=11;
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
