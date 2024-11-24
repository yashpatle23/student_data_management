# Student Management System - Database Operations Guide

## Table Structure

The `app_stud` table contains the following fields:

```sql
- Reg (varchar(10)) - Primary Key
- Name (varchar(50))
- Class (varchar(2))
- Section (varchar(1))
- Rollno (int)
- Gender (varchar(1))
- Percentage (decimal(4,1))
- Phone (varchar(10))
- Address (varchar(100))
```

## Common Database Operations

### 1. Basic Select Queries

```sql
-- Get all students
SELECT * FROM app_stud;

-- Get specific student by registration number
SELECT * FROM app_stud WHERE Reg = 'REG2024001';

-- Get students by section
SELECT * FROM app_stud WHERE Section = 'A';
```

### 2. Performance Analysis

```sql
-- Get top 10 performers
SELECT Name, Percentage
FROM app_stud
ORDER BY Percentage DESC
LIMIT 10;

-- Get average percentage by section
SELECT Section, AVG(Percentage) as avg_percentage
FROM app_stud
GROUP BY Section;

-- Get students above 90%
SELECT Name, Percentage
FROM app_stud
WHERE Percentage >= 90.0
ORDER BY Percentage DESC;
```

### 3. Data Base Creation

```sql
-- To Delete the app_student table
DROP TABLE IF EXISTS app_stud;
-- To Create the app_student table
CREATE TABLE app_stud (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    Reg TEXT,
    Name TEXT,
    Class TEXT,
    Section TEXT,
    Rollno INTEGER,
    Gender TEXT,
    Percentage REAL,
    Phone TEXT,
    Address TEXT
);
```

### 4. Adding Synthetic Data

```sql
    INSERT INTO app_stud (id, Reg, Name, Class, Section, Rollno, Gender, Percentage, Phone, Address)
VALUES
(1, 'REG2024001', 'Aarav Mehta', '10', 'A', 1, 'M', 85.6, '9876543210', '123 MG Road, Pune'),
(2, 'REG2024002', 'Ishita Gupta', '10', 'A', 2, 'F', 89.3, '9876543211', '456 Shivaji Nagar, Mumbai'),
(3, 'REG2024003', 'Rohan Sharma', '10', 'B', 3, 'M', 92.4, '9876543212', '789 Bandra West, Nagpur'),
(4, 'REG2024004', 'Diya Verma', '10', 'C', 4, 'F', 77.5, '9876543213', '101 Andheri East, Delhi'),
(5, 'REG2024005', 'Aryan Joshi', '9', 'A', 5, 'M', 80.2, '9876543214', '102 Viman Nagar, Pune'),
(6, 'REG2024006', 'Ananya Desai', '9', 'B', 6, 'F', 91.1, '9876543215', '103 Koregaon Park, Mumbai'),
(7, 'REG2024007', 'Kunal Patil', '9', 'C', 7, 'M', 72.4, '9876543216', '104 MG Road, Nashik'),
(8, 'REG2024008', 'Priya Kumar', '9', 'A', 8, 'F', 95.3, '9876543217', '105 Marine Drive, Goa'),
(9, 'REG2024009', 'Sahil Jain', '8', 'B', 9, 'M', 88.2, '9876543218', '106 Churchgate, Pune'),
(10, 'REG2024010', 'Sneha Shah', '8', 'C', 10, 'F', 93.0, '9876543219', '107 Lokhandwala, Mumbai'),
(11, 'REG2024011', 'Vivaan Reddy', '7', 'A', 11, 'M', 85.7, '9876543220', '108 Sector 17, Nagpur'),
(12, 'REG2024012', 'Meera Nair', '7', 'B', 12, 'F', 89.8, '9876543221', '109 Khar Road, Delhi'),
(13, 'REG2024013', 'Aditya Singh', '7', 'C', 13, 'M', 91.2, '9876543222', '110 Powai, Mumbai'),
(14, 'REG2024014', 'Riya Ghosh', '6', 'A', 14, 'F', 79.1, '9876543223', '111 Versova, Pune'),
(15, 'REG2024015', 'Kabir Choudhary', '6', 'B', 15, 'M', 83.4, '9876543224', '112 Peddar Road, Bangalore'),
(16, 'REG2024016', 'Ayesha Khan', '6', 'C', 16, 'F', 88.9, '9876543225', '113 Connaught Place, Nagpur'),
(17, 'REG2024017', 'Nikhil Malhotra', '5', 'A', 17, 'M', 74.6, '9876543226', '114 Hiranandani, Mumbai'),
(18, 'REG2024018', 'Tara Dixit', '5', 'B', 18, 'F', 82.3, '9876543227', '115 Panjim, Goa'),
(19, 'REG2024019', 'Arjun Iyer', '5', 'C', 19, 'M', 91.7, '9876543228', '116 Baner Road, Pune'),
(20, 'REG2024020', 'Shruti Rane', '4', 'A', 20, 'F', 90.4, '9876543229', '117 MG Road, Bangalore'),
(21, 'REG2024021', 'Ishan Pandey', '4', 'B', 21, 'M', 84.2, '9876543230', '118 Shivaji Park, Nagpur'),
(22, 'REG2024022', 'Sanya Kapur', '4', 'C', 22, 'F', 76.5, '9876543231', '119 Juhu Beach, Mumbai'),
(23, 'REG2024023', 'Raghav Trivedi', '3', 'A', 23, 'M', 86.9, '9876543232', '120 Hauz Khas, Delhi'),
(24, 'REG2024024', 'Neha Kulkarni', '3', 'B', 24, 'F', 94.7, '9876543233', '121 Dadar, Mumbai'),
(25, 'REG2024025', 'Yash Dubey', '3', 'C', 25, 'M', 82.1, '9876543234', '122 CST, Pune'),
(26, 'REG2024026', 'Pooja Bhatt', '2', 'A', 26, 'F', 93.3, '9876543235', '123 Mira Road, Bangalore'),
(27, 'REG2024027', 'Rahul Khatri', '2', 'B', 27, 'M', 81.5, '9876543236', '124 Malad West, Nagpur'),
(28, 'REG2024028', 'Kriti Tiwari', '2', 'C', 28, 'F', 78.8, '9876543237', '125 Colaba, Mumbai'),
(29, 'REG2024029', 'Varun Vyas', '1', 'A', 29, 'M', 75.4, '9876543238', '126 Tardeo, Pune'),
(30, 'REG2024030', 'Sonal Patil', '1', 'B', 30, 'F', 85.3, '9876543239', '127 Chinchwad, Goa'),
(31, 'REG2024031', 'Krishna Deshmukh', '1', 'C', 31, 'M', 77.9, '9876543240', '128 MG Road, Bangalore'),
(32, 'REG2024032', 'Anjali Sharma', '10', 'A', 32, 'F', 87.5, '9876543241', '129 FC Road, Nagpur'),
(33, 'REG2024033', 'Aman Rathore', '10', 'B', 33, 'M', 92.1, '9876543242', '130 KP Road, Mumbai'),
(34, 'REG2024034', 'Simran Bedi', '10', 'C', 34, 'F', 79.6, '9876543243', '131 Nehru Place, Delhi'),
(35, 'REG2024035', 'Karan Sehgal', '9', 'A', 35, 'M', 90.2, '9876543244', '132 MG Road, Pune'),
(36, 'REG2024036', 'Ritika Yadav', '9', 'B', 36, 'F', 86.7, '9876543245', '133 Shivaji Park, Nagpur'),
(37, 'REG2024037', 'Harsh Arora', '9', 'C', 37, 'M', 83.5, '9876543246', '134 Juhu Beach, Mumbai'),
(38, 'REG2024038', 'Sara Naik', '8', 'A', 38, 'F', 88.9, '9876543247', '135 MG Road, Bangalore'),
(39, 'REG2024039', 'Manav Pillai', '8', 'B', 39, 'M', 91.0, '9876543248', '136 Shivaji Road, Delhi'),
(40, 'REG2024040', 'Trisha Roy', '8', 'C', 40, 'F', 89.5, '9876543249', '137 MG Road, Nagpur'),
(41, 'REG2024041', 'Vivek Dutta', '7', 'A', 41, 'M', 83.3, '9876543250', '138 Shivaji Park, Mumbai'),
(42, 'REG2024042', 'Nisha Bose', '7', 'B', 42, 'F', 86.2, '9876543251', '139 Colaba, Delhi'),
(43, 'REG2024043', 'Arnav Das', '7', 'C', 43, 'M', 92.8, '9876543252', '140 Andheri West, Pune'),
(44, 'REG2024044', 'Tina Sen', '6', 'A', 44, 'F', 75.9, '9876543253', '141 KP Road, Mumbai'),
(45, 'REG2024045', 'Jayant Sharma', '6', 'B', 45, 'M', 78.4, '9876543254', '142 Nehru Place, Nagpur'),
(46, 'REG2024046', 'Maya Sinha', '6', 'C', 46, 'F', 91.5, '9876543255', '143 Vashi, Bangalore'),
(47, 'REG2024047', 'Kabir Banerjee', '5', 'A', 47, 'M', 89.4, '9876543256', '144 Bandra West, Delhi'),
(48, 'REG2024048', 'Rhea Dasgupta', '5', 'B', 48, 'F', 84.7, '9876543257', '145 Koregaon Park, Mumbai'),
(49, 'REG2024049', 'Parth Singh', '5', 'C', 49, 'M', 80.3, '9876543258', '146 Colaba, Nagpur'),
(50, 'REG2024050', 'Shreya Jain', '4', 'A', 50, 'F', 90.8, '9876543259', '147 MG Road, Pune')

('024001', 'Aarav Mehta', '10', 'A', 1, 'M', 85.6, '9876543210', '123 MG Road, Pune'),
('024002', 'Ishita Gupta', '10', 'A', 2, 'F', 89.3, '9876543211', '456 Shivaji Nagar, Mumbai'),
('024003', 'Rohan Sharma', '10', 'B', 3, 'M', 92.4, '9876543212', '789 Bandra West, Nagpur'),
('024004', 'Priya Patel', '10', 'A', 4, 'F', 88.7, '9876543213', '234 FC Road, Pune'),
('024005', 'Arjun Singh', '10', 'B', 5, 'M', 90.1, '9876543214', '567 Koregaon Park, Pune'),
('024006', 'Ananya Kumar', '10', 'A', 6, 'F', 94.5, '9876543215', '890 Deccan, Pune'),
('024007', 'Vihan Reddy', '10', 'B', 7, 'M', 87.8, '9876543216', '123 Kalyani Nagar, Pune'),
('024008', 'Zara Sheikh', '10', 'A', 8, 'F', 91.2, '9876543217', '456 Camp Area, Mumbai'),
('024009', 'Advait Joshi', '10', 'B', 9, 'M', 86.9, '9876543218', '789 Viman Nagar, Pune'),
('024010', 'Myra Kapoor', '10', 'A', 10, 'F', 93.4, '9876543219', '234 Aundh, Pune'),
('024011', 'Vivaan Malhotra', '10', 'B', 11, 'M', 88.5, '9876543220', '567 Kothrud, Pune'),
('024012', 'Aisha Khan', '10', 'A', 12, 'F', 90.8, '9876543221', '890 Hadapsar, Pune'),
('024013', 'Reyansh Das', '10', 'B', 13, 'M', 85.9, '9876543222', '123 Wakad, Pune'),
('024014', 'Saanvi Verma', '10', 'A', 14, 'F', 92.7, '9876543223', '456 Baner, Pune'),
('024015', 'Kabir Saxena', '10', 'B', 15, 'M', 87.3, '9876543224', '789 Hinjewadi, Pune'),
('024016', 'Avni Chopra', '10', 'A', 16, 'F', 91.6, '9876543225', '234 Wagholi, Pune'),
('024017', 'Krish Iyer', '10', 'B', 17, 'M', 89.4, '9876543226', '567 Pimpri, Pune'),
('024018', 'Riya Banerjee', '10', 'A', 18, 'F', 93.8, '9876543227', '890 Chinchwad, Pune'),
('024019', 'Aditya Nair', '10', 'B', 19, 'M', 86.2, '9876543228', '123 Akurdi, Pune'),
('024020', 'Kiara Mehra', '10', 'A', 20, 'F', 90.5, '9876543229', '456 Nigdi, Pune'),
('024021', 'Ved Rajput', '10', 'B', 21, 'M', 88.9, '9876543230', '789 Bhosari, Pune'),
('024022', 'Aadhya Bhat', '10', 'A', 22, 'F', 92.1, '9876543231', '234 Warje, Pune'),
('024023', 'Arnav Menon', '10', 'B', 23, 'M', 87.5, '9876543232', '567 Sinhagad Road, Pune'),
('024024', 'Mira Sinha', '10', 'A', 24, 'F', 91.9, '9876543233', '890 Market Yard, Pune'),
('024025', 'Yash Mathur', '10', 'B', 25, 'M', 85.3, '9876543234', '123 Karve Road, Pune'),
('024026', 'Anika Rao', '10', 'A', 26, 'F', 93.2, '9876543235', '456 JM Road, Pune'),
('024027', 'Dhruv Chadha', '10', 'B', 27, 'M', 89.7, '9876543236', '789 Tilak Road, Pune'),
('024028', 'Sara Ahmed', '10', 'A', 28, 'F', 90.4, '9876543237', '234 Laxmi Road, Pune'),
('024029', 'Aryan Desai', '10', 'B', 29, 'M', 86.8, '9876543238', '567 Senapati Bapat Road, Pune'),
('024030', 'Tara Gill', '10', 'A', 30, 'F', 92.6, '9876543239', '890 Law College Road, Pune'),
('024031', 'Neil Shah', '10', 'B', 31, 'M', 88.2, '9876543240', '123 Model Colony, Pune'),
('024032', 'Aria Khanna', '10', 'A', 32, 'F', 91.5, '9876543241', '456 Boat Club Road, Pune'),
('024033', 'Shaurya Chauhan', '10', 'B', 33, 'M', 87.9, '9876543242', '789 Range Hills, Pune'),
('024034', 'Liya Thomas', '10', 'A', 34, 'F', 93.7, '9876543243', '234 College Road, Pune'),
('024035', 'Ishan Bhatia', '10', 'B', 35, 'M', 85.8, '9876543244', '567 Ganeshkhind Road, Pune'),
('024036', 'Eva Malik', '10', 'A', 36, 'F', 90.9, '9876543245', '890 University Road, Pune'),
('024037', 'Veer Oberoi', '10', 'B', 37, 'M', 89.1, '9876543246', '123 Bremen Road, Mumbai'),
('024038', 'Kyra Hegde', '10', 'A', 38, 'F', 92.3, '9876543247', '456 Hill Road, Mumbai'),
('024039', 'Dev Agarwal', '10', 'B', 39, 'M', 87.1, '9876543248', '789 Carter Road, Mumbai'),
('024040', 'Amara Sethi', '10', 'A', 40, 'F', 91.8, '9876543249', '234 Peddar Road, Mumbai'),
('024041', 'Ryan D''Souza', '10', 'B', 41, 'M', 86.4, '9876543250', '567 Nepean Sea Road, Mumbai'),
('024042', 'Nyra Walia', '10', 'A', 42, 'F', 93.1, '9876543251', '890 Marine Drive, Mumbai'),
('024043', 'Zain Qureshi', '10', 'B', 43, 'M', 88.6, '9876543252', '123 Malabar Hill, Mumbai'),
('024044', 'Ira Bajaj', '10', 'A', 44, 'F', 90.7, '9876543253', '456 Worli Sea Face, Mumbai'),
('024045', 'Aarush Mehta', '10', 'B', 45, 'M', 87.4, '9876543254', '789 Juhu Beach, Mumbai'),
('024046', 'Shanaya Kumar', '10', 'A', 46, 'F', 92.8, '9876543255', '234 Versova, Mumbai'),
('024047', 'Virat Suri', '10', 'B', 47, 'M', 85.7, '9876543256', '567 Andheri West, Mumbai'),
('024048', 'Ahana Rastogi', '10', 'A', 48, 'F', 91.4, '9876543257', '890 Goregaon East, Mumbai'),
('024049', 'Ayaan Chawla', '10', 'B', 49, 'M', 89.8, '9876543258', '123 Powai, Mumbai'),
('024050', 'Misha Bhalla', '10', 'A', 50, 'F', 93.5, '9876543259', '456 Chembur, Mumbai'),
('024051', 'Ahan Ranjan', '10', 'B', 51, 'M', 86.7, '9876543260', '789 Ghatkopar, Mumbai'),
('024052', 'Navya Arora', '10', 'A', 52, 'F', 90.2, '9876543261', '234 Mulund, Mumbai'),
('024053', 'Rudra Khurana', '10', 'B', 53, 'M', 88.4, '9876543262', '567 Thane West, Mumbai'),
('024054', 'Diya Ahuja', '10', 'A', 54, 'F', 92.9, '9876543263', '890 Vashi, Navi Mumbai'),
('024055', 'Kabir Ranganathan', '10', 'B', 55, 'M', 87.2, '9876543264', '123 Belapur, Navi Mumbai'),
('024056', 'Anvi Bhargava', '10', 'A', 56, 'F', 91.7, '9876543265', '456 Kharghar, Navi Mumbai'),
('024057', 'Shaan Mistry', '10', 'B', 57, 'M', 85.5, '9876543266', '789 Panvel, Navi Mumbai'),
('024058', 'Anya Talwar', '10', 'A', 58, 'F', 93.6, '9876543267', '234 Airoli, Navi Mumbai'),
('024059', 'Armaan Grewal', '10', 'B', 59, 'M', 89.5, '9876543268', '567 Seawoods, Navi Mumbai'),
('024060', 'Amaira Basu', '10', 'A', 60, 'F', 90.6, '9876543269', '890 Nerul, Navi Mumbai'),
('024061', 'Vihaan Venkatesh', '10', 'B', 61, 'M', 86.5, '9876543270', '123 Sanpada, Navi Mumbai'),
('024062', 'Mishka Rathore', '10', 'A', 62, 'F', 92.2, '9876543271', '456 Kopar Khairane, Navi Mumbai'),
('024063', 'Aayan Pradhan', '10', 'B', 63, 'M', 88.1, '9876543272', '789 Ghansoli, Navi Mumbai'),
('024064', 'Ivana Sundaram', '10', 'A', 64, 'F', 91.3, '9876543273', '234 Turbhe, Navi Mumbai'),
('024065', 'Shiv Gopal', '10', 'B', 65, 'M', 87.6, '9876543274', '567 Rabale, Navi Mumbai'),
('024066', 'Kyra Sood', '10', 'A', 66, 'F', 93.3, '9876543275', '890 Mahape, Navi Mumbai'),
('024067', 'Rehan Mittal', '10', 'B', 67, 'M', 85.4, '9876543276', '123 CBD Belapur, Navi Mumbai'),
('024068', 'Yaashi Nathani', '10', 'A', 68, 'F', 90.3, '9876543277', '456 Kalamboli, Navi Mumbai'),
('024069', 'Advaith Sengupta', '10', 'B', 69, 'M', 89.2, '9876543278', '789 Kamothe, Navi Mumbai'),
('024070', 'Miraya Kulkarni', '10', 'A', 70, 'F', 92.5, '9876543279', '890 Ulwe, Navi Mumbai');
```
