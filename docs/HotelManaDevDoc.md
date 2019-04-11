---
id: HotelManaDevDoc
title: Hotel Management Developer Document
sidebar_label: Hotel Management Developer Document
---

## INTRODUCTION

Hotel management system is a platform that brings hotels around the world together for easy access to customers. https://www.hotelanywhere.com/login

## TASK STATUS

Modules	                 |     Status
------------------------ |-------------	
Landing  page            |	completed
Profile	                 |   completed
Dashboard                |   completed
Staff                    |  completed
Room                     |	completed
Booking	                 |   completed
maintanance management   |   in progress
account management       |  in progress
inventory management     |	in progress

##  Code breakdown with language used

Programming language: PHP, JavaScript, JQuery
Database: MySQL
Version: 1.0.0
System requirement: 
      Browser compatibility: chrome, safari, internet explorer
Processor Speed (i.e. Pentium 4, 3.2 GHz or Power PC G5, 2.0 GHz)
Memory, a.k.a. RAM (i.e. 512 MB).


## Database Structure

CREATE TABLE `accounts` (
  `id` int(10) UNSIGNED NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `amenities`
--

CREATE TABLE `amenities` (
  `id` int(10) UNSIGNED NOT NULL,
  `branchID` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `placesAround` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `amenity` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `wifi` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `swimmingpool` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `restaurant` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `bar` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `cinema` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT ''
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Dumping data for table `amenities`
--

INSERT INTO `amenities` (`id`, `branchID`, `placesAround`, `amenity`, `created_at`, `updated_at`, `wifi`, `swimmingpool`, `restaurant`, `bar`, `cinema`) VALUES
(1, '8', 'Banks, cinema, Beach', '', '2019-03-18 20:01:35', '2019-03-18 20:25:54', 'Yes', 'Yes', 'Yes', 'Yes', 'Yes');

-- --------------------------------------------------------

--
-- Table structure for table `branches`
--

CREATE TABLE `branches` (
  `branchID` int(10) NOT NULL,
  `branchName` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `branchEmail` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `branchPhone` varchar(50) COLLATE utf8mb4_unicode_ci NOT NULL,
  `branchLoc` varchar(50) COLLATE utf8mb4_unicode_ci NOT NULL,
  `branchAdd` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `branch_image` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `aboutThebranch` mediumtext COLLATE utf8mb4_unicode_ci NOT NULL,
  `sadmin_id` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--

----------------------------------------------------------------------------------------
-- Table structure for table `contact_infos`
--

CREATE TABLE `contact_infos` (
  `id` int(10) UNSIGNED NOT NULL,
  `name` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `email` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `phone_number` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `message` mediumtext COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `customer_reviews`
--

CREATE TABLE `customer_reviews` (
  `id` int(10) UNSIGNED NOT NULL,
  `comment` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `roomID` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `rating` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `date_created` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
-- --------------------------------------------------------

--
-- Table structure for table `deals`
--

CREATE TABLE `deals` (
  `id` int(10) UNSIGNED NOT NULL,
  `discount` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `deal_closingdate` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `branchID` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `sadmin_id` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

CREATE TABLE `guests` (
  `gID` int(10) NOT NULL,
  `gfname` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `glname` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `gemail` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `gphone` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `ggender` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `gaddress` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `gcity` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `gcountry` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `gIdNumber` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `gBranch` int(9) DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `special_request` mediumtext COLLATE utf8mb4_unicode_ci
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
-- --------------------------------------------------------

--
-- Table structure for table `housekeepings`
--

CREATE TABLE `housekeepings` (
  `id` int(10) UNSIGNED NOT NULL,
  `status` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `assigned_to` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `date_assigned` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `inventories`
--

CREATE TABLE `inventories` (
  `id` int(10) UNSIGNED NOT NULL,
  `item_name` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `description` mediumtext COLLATE utf8mb4_unicode_ci,
  `quantity` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `location` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `price` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `purchase_year` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `date_created` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `sadmin_id` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `updated_by` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `information` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `branch` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `maintenances`
--

CREATE TABLE `maintenances` (
  `id` int(10) UNSIGNED NOT NULL,
  `category` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `work_assigned_to` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `priority` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `date_assigned` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `description` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `deadline` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `status` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL,
  `room` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `branch` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `migrations`
--

CREATE TABLE `migrations` (
  `id` int(10) UNSIGNED NOT NULL,
  `migration` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `batch` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

## COPYRIGHT

All titles, source codes, and other intellectual property rights in and to the SOFTWARE (including but not limited to any images, icons, button, design elements, video, audio, text and incorporated into the SOFTWARE), the accompanying printed materials, and any copies of the SOFTWARE, are owned by ICS outsourcing Limited.
