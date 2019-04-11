---
id: HRcoreDevDoc
title: HRcore Developer Document
sidebar_label: HRcore Developer Document
---


## INTRODUCTION

HRcore is a flexible software that helps with the day-to-day activities of the company. It includes leave management, appraisal management, requisition system, audit system.
The URL to register as an admin is for HRcore is https://www.hrcore.ng/admin_register   while the URL to register as a staff is https://www.hrcore.ng/register .

## SETTINGS

In HRcore, the settings are a very important part of the HRcore. In the settings, the admin is first required to setup the system according to their company system specification by filling all fields correctly to enable easy flow of work. 

### admin settings

![alt-text](assets/shoot/admin_settings.png)
![alt-text](assets/shoot/admin_setting2.png)
![alt-text](assets/shoot/admin_setting3.png)

### staff settings
![alt-text](assets/shoot/staff_setting.png)
![alt-text](assets/shoot/staff_settings2.png)
 
Also the staff is also required to fill all fields on the settings for easy flow of request.


## TASK STATUS

Modules	                 |     Status
------------------------ |-------------	
Leave management system  |	completed
Appraisal system	       |   completed
Requisition system	     |   completed
Employee information	   |  completed
ID card request          |	completed
Staff audit	             |   completed
Staff Directory	         |   completed
Payroll                  |	completed
Permission	             |   completed
Dashboard	               |   completed
KSS Board	               |   completed


##  Code breakdown with language used

Programming language: PHP, JavaScript, JQuery
Database: MySQL
Version: 1.0.0
System requirement: 
      Browser compatibility: chrome, safari, internet explorer
Processor Speed (i.e. Pentium 4, 3.2 GHz or Power PC G5, 2.0 GHz)
Memory, a.k.a. RAM (i.e. 512 MB).

## Database Structure

Table structure for table `appraisal`

CREATE TABLE `appraisal` (
  `id` int(11) NOT NULL,
  `date_created` varchar(50) NOT NULL,
  `period` varchar(50) NOT NULL,
  `year` varchar(50) NOT NULL,
  `replies` int(200) NOT NULL,
  `document_name` varchar(255) NOT NULL,
  `document` varchar(255) NOT NULL,
  `department` varchar(255) NOT NULL,
  `appraisal_data` text NOT NULL,
  `admin_id` varchar(255) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--------------------------------------------------------

Table structure for table `appraisal_replies`

CREATE TABLE `appraisal_replies` (
  `id` int(11) NOT NULL,
  `staff_remarks` varchar(255) NOT NULL DEFAULT '',
  `staff_justifications` text,
  `lManager_remarks` varchar(255) NOT NULL DEFAULT '',
  `lManager_justification` text,
  `bManager_justification` text,
  `bManager_remarks` varchar(255) NOT NULL DEFAULT '',
  `stage` varchar(100) NOT NULL DEFAULT '',
  `date_created` varchar(20) NOT NULL DEFAULT '',
  `appraisal_id` varchar(50) NOT NULL DEFAULT '',
  `staff_id` varchar(100) NOT NULL DEFAULT '',
  `document_uploaded_by_staff` varchar(255) NOT NULL DEFAULT '',
  `admin_id` varchar(255) NOT NULL DEFAULT '',
  `comments_flow` text NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `branches`
--

CREATE TABLE `branches` (
  `id` int(11) NOT NULL,
  `name` varchar(255) NOT NULL DEFAULT '',
  `address` text NOT NULL,
  `phone_number` varchar(250) NOT NULL DEFAULT '',
  `email` varchar(255) NOT NULL,
  `date_created` varchar(255) NOT NULL,
  `admin_id` varchar(255) NOT NULL,
  `insert_by` varchar(255) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `certifications`
--

CREATE TABLE `certifications` (
  `id` int(11) NOT NULL,
  `certification_name` varchar(100) NOT NULL,
  `date_cert` varchar(100) NOT NULL,
  `staff_id` varchar(100) NOT NULL,
  `admin_id` varchar(255) NOT NULL,
  `date_created` varchar(255) NOT NULL,
  `document` varchar(255) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `company`
--

CREATE TABLE `company` (
  `id` int(11) NOT NULL,
  `company_name` varchar(50) NOT NULL,
  `admin_id` varchar(20) DEFAULT NULL,
  `department` varchar(255) DEFAULT NULL,
  `branch` varchar(255) DEFAULT NULL,
  `appraisal_flow` text,
  `requisition_flow` text NOT NULL,
  `leave_flow` text,
  `date_created` varchar(255) NOT NULL,
  `address` varchar(255) NOT NULL,
  `image` varchar(255) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `departments`
--

CREATE TABLE `departments` (
  `id` int(255) NOT NULL,
  `branch_id` varchar(255) NOT NULL DEFAULT '',
  `dept` varchar(255) NOT NULL DEFAULT '',
  `date_created` varchar(255) NOT NULL DEFAULT '',
  `admin_id` varchar(255) NOT NULL,
  `insert_by` varchar(255) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `employee_info`
--

CREATE TABLE `employee_info` (
  `id` int(50) NOT NULL,
  `branch_id` varchar(50) NOT NULL DEFAULT '',
  `department_id` varchar(50) DEFAULT '',
  `first_name` varchar(255) NOT NULL DEFAULT '',
  `last_name` varchar(255) NOT NULL DEFAULT '',
  `date_of_birth` varchar(255) NOT NULL DEFAULT '',
  `status` varchar(255) NOT NULL DEFAULT '',
  `gender` varchar(50) NOT NULL DEFAULT '',
  `blood_type` varchar(255) NOT NULL DEFAULT '',
  `citizenship` varchar(255) NOT NULL DEFAULT '',
  `place_of_birth` varchar(255) NOT NULL DEFAULT '',
  `religion` varchar(255) NOT NULL DEFAULT '',
  `date_created` varchar(255) NOT NULL DEFAULT '',
  `middle_name` varchar(255) NOT NULL DEFAULT '',
  `employee_ID` varchar(255) NOT NULL DEFAULT '',
  `admin_id` varchar(255) NOT NULL DEFAULT '',
  `updated_by` varchar(255) NOT NULL DEFAULT '',
  `insert_by` varchar(255) NOT NULL DEFAULT '',
  `date_updated` varchar(255) NOT NULL DEFAULT ''
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `employee_payroll_data`
--

CREATE TABLE `employee_payroll_data` (
  `id` int(255) NOT NULL,
  `basic_salary` varchar(255) NOT NULL DEFAULT '',
  `employee_info_id` varchar(255) NOT NULL,
  `housing` varchar(255) NOT NULL DEFAULT '',
  `transport` varchar(255) NOT NULL DEFAULT '',
  `lunch` varchar(255) NOT NULL DEFAULT '',
  `utility` varchar(255) NOT NULL DEFAULT '',
  `education` varchar(255) NOT NULL DEFAULT '',
  `entertainment` varchar(255) NOT NULL DEFAULT '',
  `HMO` varchar(255) NOT NULL DEFAULT '',
  `leave_bonus` varchar(255) NOT NULL DEFAULT '',
  `xmas` varchar(255) NOT NULL DEFAULT '',
  `pension_company` varchar(255) NOT NULL DEFAULT '',
  `pension_earning` varchar(255) NOT NULL DEFAULT '',
  `tax` varchar(255) NOT NULL DEFAULT '',
  `gross` varchar(255) NOT NULL DEFAULT '',
  `service_charge` varchar(255) NOT NULL DEFAULT '',
  `VAT` varchar(255) NOT NULL DEFAULT '',
  `NET` varchar(255) NOT NULL DEFAULT '',
  `account_number` varchar(255) NOT NULL DEFAULT '',
  `bank_name` varchar(255) NOT NULL DEFAULT '',
  `insert_by` varchar(255) NOT NULL DEFAULT '',
  `date_created` varchar(255) NOT NULL DEFAULT '',
  `updated_by` varchar(255) NOT NULL DEFAULT '',
  `furniture` varchar(255) NOT NULL DEFAULT '',
  `q_allowance` varchar(255) NOT NULL DEFAULT '',
  `medical` varchar(250) NOT NULL DEFAULT '',
  `GLI` varchar(250) NOT NULL DEFAULT '',
  `ECA` varchar(255) NOT NULL DEFAULT '',
  `ITF` varchar(255) NOT NULL DEFAULT '',
  `NHF` varchar(255) NOT NULL DEFAULT ''
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `id_card`
--

CREATE TABLE `id_card` (
  `IID` int(11) NOT NULL,
  `staff_id` varchar(100) NOT NULL,
  `admin_id` varchar(250) DEFAULT NULL,
  `date_created` varchar(250) DEFAULT NULL,
  `signature` varchar(250) DEFAULT NULL,
  `status` varchar(250) DEFAULT NULL,
  `remark` varchar(250) DEFAULT NULL,
  `history` varchar(250) DEFAULT NULL,
  `cancel_request` varchar(50) NOT NULL DEFAULT '',
  `justification` text NOT NULL,
  `comment` text NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1 COMMENT='ID Card Table';

-- --------------------------------------------------------

--
-- Table structure for table `items`
--

CREATE TABLE `items` (
  `id` int(11) NOT NULL,
  `item_category` varchar(50) NOT NULL,
  `item_cost` varchar(150) NOT NULL,
  `item_name` varchar(250) NOT NULL,
  `item_quantity` varchar(50) NOT NULL,
  `admin_id` varchar(50) NOT NULL,
  `date_created` varchar(50) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `kss`
--

CREATE TABLE `kss` (
  `id` int(11) NOT NULL,
  `information` text,
  `staff_id` int(255) NOT NULL,
  `admin_id` int(255) NOT NULL,
  `date_created` varchar(255) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `leaves`
--

CREATE TABLE `leaves` (
  `id` int(11) NOT NULL,
  `company_name` varchar(20) NOT NULL,
  `leave_type` varchar(20) NOT NULL,
  `start_date` varchar(20) NOT NULL,
  `end_date` varchar(20) NOT NULL,
  `justification` varchar(255) NOT NULL,
  `require_reliever` varchar(4) NOT NULL,
  `reliever_source` varchar(10) NOT NULL,
  `reliever_name` varchar(100) NOT NULL,
  `reliever_email` varchar(20) NOT NULL,
  `reliever_phone` varchar(20) NOT NULL,
  `lManager_remark` varchar(50) NOT NULL,
  `bManager_remark` varchar(50) NOT NULL,
  `stage` varchar(20) NOT NULL,
  `status` varchar(20) NOT NULL,
  `date_created` varchar(20) NOT NULL,
  `staff_id` varchar(20) NOT NULL,
  `admin_id` varchar(20) NOT NULL,
  `fstage` varchar(20) NOT NULL,
  `flow` text NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `open_information_portal`
--

CREATE TABLE `open_information_portal` (
  `id` int(11) NOT NULL,
  `opening_date` varchar(50) NOT NULL,
  `closing_date` varchar(50) NOT NULL,
  `open_for` varchar(255) NOT NULL,
  `date_created` varchar(50) NOT NULL,
  `admin_id` varchar(20) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `personal_information`
--

CREATE TABLE `personal_information` (
  `id` int(10) NOT NULL,
  `surname` varchar(20) NOT NULL,
  `firstname` varchar(20) NOT NULL,
  `middlename` varchar(20) NOT NULL,
  `gender` varchar(20) NOT NULL,
  `DOB` varchar(20) NOT NULL,
  `town` varchar(50) NOT NULL,
  `state` varchar(50) NOT NULL,
  `country` varchar(50) NOT NULL,
  `staff_id` varchar(11) NOT NULL,
  `admin_id` varchar(255) NOT NULL,
  `date_created` varchar(255) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `qualifications`
--

CREATE TABLE `qualifications` (
  `id` int(11) NOT NULL,
  `qualification_name` varchar(50) NOT NULL,
  `grade` varchar(50) NOT NULL,
  `institution` varchar(100) NOT NULL,
  `course_of_study` varchar(50) NOT NULL,
  `date_obtained` varchar(50) NOT NULL,
  `specialization` varchar(255) NOT NULL,
  `staff_id` varchar(100) NOT NULL,
  `admin_id` varchar(255) NOT NULL,
  `document` varchar(250) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

## COPYRIGHT

All titles, source codes, and other intellectual property rights in and to the SOFTWARE (including but not limited to any images, icons, button, design elements, video, audio, text and incorporated into the SOFTWARE), the accompanying printed materials, and any copies of the SOFTWARE, are owned by ICS outsourcing Limited.


