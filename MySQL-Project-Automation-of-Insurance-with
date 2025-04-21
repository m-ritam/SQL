CREATE database AutomationofInsurance;  -- creating database
USE AutomationofInsurance;
CREATE TABLE Customer (
    CustomerId INT PRIMARY KEY,
    CustomerFirstName VARCHAR(50),
    CustomerLastName VARCHAR(50),
    CustomerEmail VARCHAR(100),
    CustomerPhone VARCHAR(20),
    CustomerAddress VARCHAR(255)
);
INSERT INTO Customer (CustomerId, CustomerFirstName, CustomerLastName, CustomerEmail, CustomerPhone, CustomerAddress)
VALUES
(1, 'John', 'Doe', 'john@exauto.com', '123-456-7890', '123 Main St'),
(2, 'Alice', 'Smith', 'alice@exauto.com', '987-654-3210', '456 Elm St'),
(3, 'Bob', 'Johnson', 'bob@exauto.com', '555-123-4567', '789 Oak St'),
(4, 'Mary', 'Williams', 'mary@exauto.com', '444-888-2222', '567 Pine St'),
(5, 'David', 'Brown', 'david@exauto.com', '777-999-3333', '678 Maple St');

CREATE TABLE Agent (
    AgentId INT PRIMARY KEY,
    AgentFirstName VARCHAR(50),
    AgentLastName VARCHAR(50),
    AgentEmail VARCHAR(100),
    AgentPhone VARCHAR(20)
);
INSERT INTO Agent (AgentId, AgentFirstName, AgentLastName, AgentEmail, AgentPhone)
VALUES
(101, 'Phill', 'Hughes', 'phill@exauto.com', '111-111-1111'),
(102, 'Randy', 'Orton', 'randy@exauto.com', '222-222-2222'),
(103, 'Bobby', 'Lashley', 'bobby@exauto.com', '333-333-3333'),
(104, 'Tom', 'Williams', 'tom@exauto.com', '444-444-4444'),
(105, 'Alice', 'Johnson', 'alice@exauto.com', '555-555-5555');


CREATE TABLE Policy (
    PolicyNo INT PRIMARY KEY,
    CustomerId INT,
    PolicyType VARCHAR(50),
    PremiumAmount DECIMAL(18, 2),
    PaymentFrequency VARCHAR(20)
);
ALTER TABLE Policy
ADD FOREIGN KEY (CustomerId) REFERENCES Customer(CustomerId);
INSERT INTO Policy (PolicyNo, CustomerId, PolicyType, PremiumAmount, PaymentFrequency)
VALUES
(1001, 1, 'Life', 1000.00, 'Annual'),
(1002, 2, 'Health', 500.00, 'Monthly'),
(1003, 3, 'Vehicle', 800.00, 'Quarterly'),
(1004, 4, 'Asset', 1200.00, 'Annual'),
(1005, 5, 'Life', 950.00, 'Annual');


CREATE TABLE Claim (
    ClaimId INT PRIMARY KEY,
    CustomerId INT,
    PolicyNo INT,
    ClaimRequestDate DATE,
    ClaimAmount DECIMAL(18, 2),
    ClaimStatus VARCHAR(20)
);
ALTER TABLE Claim
ADD FOREIGN KEY (CustomerId) REFERENCES Customer(CustomerId);
ALTER TABLE Claim
ADD FOREIGN KEY (PolicyNo) REFERENCES Policy(PolicyNo);
INSERT INTO Claim (ClaimId, CustomerId, PolicyNo, ClaimRequestDate, ClaimAmount, ClaimStatus)
VALUES
(2001, 1, 1001, '2023-01-15', 500.00, 'Pending'),
(2002, 2, 1002, '2023-02-20', 200.00, 'Approved'),
(2003, 3, 1003, '2023-03-10', 1000.00, 'Pending'),
(2004, 4, 1004, '2023-04-05', 800.00, 'Approved'),
(2005, 5, 1005, '2023-05-15', 300.00, 'Pending');

CREATE TABLE Employee (
    EmployeeId INT PRIMARY KEY,
    EmployeeFirstName VARCHAR(50),
    EmployeeLastName VARCHAR(50),
    EmployeeEmail VARCHAR(100),
    EmployeePhone VARCHAR(20),
    Role VARCHAR(50)
);
INSERT INTO Employee (EmployeeId, EmployeeFirstName, EmployeeLastName, EmployeeEmail, EmployeePhone, Role)
VALUES
(301, 'Henry', 'Puerto', 'employeeX@exauto.com', '111-222-3333', 'Claims Processor'),
(302, 'Vicky', 'Bansal', 'vicky@exauto.com', '444-555-6666', 'Underwriter'),
(303, 'Shrey', 'Parker', 'shrey@exauto.com', '777-888-9999', 'Agent Support'),
(304, 'Peter', 'Phillip', 'peter@exauto.com', '111-333-4444', 'Claims Processor'),
(305, 'Sanjay', 'Daruwala', 'sanjay@exauto.com', '555-666-7777', 'Underwriter');


CREATE TABLE Manager (
    ManagerId INT PRIMARY KEY,
    ManagerFirstName VARCHAR(50),
    ManagerLastName VARCHAR(50),
    ManagerEmail VARCHAR(100),
    ManagerPhone VARCHAR(20)
);
INSERT INTO Manager (ManagerId, ManagerFirstName, ManagerLastName, ManagerEmail, ManagerPhone)
VALUES
(401, 'Michael', 'Smith', 'manager1@example.com', '111-111-1111'),
(402, 'Maria', 'Garcia', 'manager2@example.com', '222-222-2222'),
(403, 'Mary', 'Smith', 'manager3@example.com', '333-333-3333'),
(404, 'James', 'Johnson', 'manager4@example.com', '444-444-4444'),
(405, 'Robert', 'Smith', 'manager5@example.com', '555-555-5555');


CREATE TABLE PremiumPayment (
    PaymentId INT PRIMARY KEY,
    CustomerId INT,
    PolicyNo INT,
    PremiumPaymentDate DATE,
    PremiumAmount DECIMAL(18, 2),
    PremiumPaymentStatus VARCHAR(20),
    PremiumUpdated_date DATETIME,
    PremiumUpdated_user VARCHAR(50)
);
ALTER TABLE PremiumPayment
ADD FOREIGN KEY (CustomerId) REFERENCES Customer(CustomerId);
ALTER TABLE PremiumPayment
ADD FOREIGN KEY (PolicyNo) REFERENCES Policy(PolicyNo);
INSERT INTO PremiumPayment (PaymentId, CustomerId, PolicyNo, PremiumPaymentDate, PremiumAmount, PremiumPaymentStatus, PremiumUpdated_date, PremiumUpdated_user)
VALUES
(501, 1, 1001, '2023-02-01', 1000.00, 'Paid', '2023-02-01 12:00:00', 'Admin'),
(502, 2, 1002, '2023-02-05', 200.00, 'Paid', '2023-02-05 14:30:00', 'AgentA'),
(503, 3, 1003, '2023-03-15', 800.00, 'Pending', '2023-03-15 10:45:00', 'AgentB'),
(504, 4, 1004, '2023-04-10', 1200.00, 'Paid', '2023-04-10 09:15:00', 'Admin'),
(505, 5, 1005, '2023-05-01', 950.00, 'Paid', '2023-05-01 16:20:00', 'Manager1');


CREATE TABLE PolicyRenewal (
    RenewalId INT PRIMARY KEY,
    PolicyNo INT,
    RenewalDate DATE,
    DiscountApplied BIT
);
ALTER TABLE PolicyRenewal
ADD FOREIGN KEY (PolicyNo) REFERENCES Policy(PolicyNo);
INSERT INTO PolicyRenewal (RenewalId, PolicyNo, RenewalDate, DiscountApplied)
VALUES
(601, 1001, '2023-01-15', 1),
(602, 1002, '2023-02-20', 0),
(603, 1003, '2023-03-10', 1),
(604, 1004, '2023-04-05', 0),
(605, 1005, '2023-05-15', 1);

CREATE TABLE PremiumPaymentSchedule (
    ScheduleId INT PRIMARY KEY,
    CustomerId INT,
    PolicyNo INT,
    SchedulePaymentDueDate DATE,
    SchedulePenaltyAmount DECIMAL(18, 2)
);
ALTER TABLE PremiumPaymentSchedule
ADD FOREIGN KEY (CustomerId) REFERENCES Customer(CustomerId);
ALTER TABLE PremiumPaymentSchedule
ADD FOREIGN KEY (PolicyNo) REFERENCES Policy(PolicyNo);
INSERT INTO PremiumPaymentSchedule (ScheduleId, CustomerId, PolicyNo, PremiumPaymentDueDate, PremiumPenaltyAmount)
VALUES
(701, 1, 1001, '2023-02-01', 0.00),
(702, 2, 1002, '2023-03-01', 10.00),
(703, 3, 1003, '2023-04-01', 20.00),
(704, 4, 1004, '2023-05-01', 0.00),
(705, 5, 1005, '2023-06-01', 5.00);

CREATE TABLE PolicyClaimLimits (
    PolicyType VARCHAR(50) PRIMARY KEY,
    MaxClaimsPerYear INT
);
INSERT INTO PolicyClaimLimits (PolicyType, MaxClaimsPerYear)
VALUES
('Life', 4),
('Health', 3),
('Vehicle', 2),
('Asset', 4),
('Property', 5);

CREATE TABLE CustomerHistory (
    CustomerHistoryId INT PRIMARY KEY,
    CustomerId INT,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100),
    Phone VARCHAR(20),
    Address VARCHAR(255),
    DeletionDate DATETIME
);
ALTER TABLE CustomerHistory
ADD FOREIGN KEY (CustomerId) REFERENCES Customer(CustomerId);
INSERT INTO CustomerHistory (CustomerHistoryId, CustomerId, FirstName, LastName, Email, Phone, Address, DeletionDate)
VALUES
(3001, 1, 'Sarah', 'Johnson', 'sarah@exauto.com', '999-888-7777', '123 Hill St', '2023-08-10 14:25:00'),
(3002, 2, 'Michael', 'Brown', 'michael@exauto.com', '555-777-3333', '789 Valley Rd', '2023-08-12 09:45:00'),
(3003, 3, 'Emily', 'Davis', 'emily@exauto.com', '333-666-9999', '456 Lake Dr', '2023-08-14 16:10:00'),
(3004, 4, 'James', 'Wilson', 'james@exauto.com', '222-444-1111', '890 Mountain Ave', '2023-08-16 11:30:00'),
(3005, 5, 'Sophia', 'Lee', 'sophia@exauto.com', '777-555-2222', '567 Ocean Blvd', '2023-08-18 13:55:00');


-- To list customer details for a given customer (IN: CustomerId): - 
DELIMITER //
CREATE PROCEDURE GetCustomerDetails(IN Customer_Id INT)
BEGIN
    SELECT * FROM Customer WHERE Customer_Id = CustomerId;
END//
DELIMITER ;

call GetCustomerDetails(3);

-- To calculate policy amount at the time of renewal (IN: Customer id, Policy No)
DELIMITER //
CREATE FUNCTION CalculatePolicyRenewalAmount(Customer_Id INT, Policy_No INT) RETURNS DECIMAL(18, 2)
DETERMINISTIC
BEGIN
    DECLARE RenewalAmount DECIMAL(18, 2);
    
    SELECT PremiumAmount INTO RenewalAmount
    FROM Policy
    WHERE CustomerId = Customer_Id AND PolicyNo = Policy_No;
    
    IF RenewalAmount IS NULL THEN
        SET RenewalAmount = 0.00;
    END IF;
    
    RETURN RenewalAmount;
END//
DELIMITER ;


-- To list all policy details owned by a customer (IN : Customer Id)

DELIMITER //
CREATE PROCEDURE GetCustomerPolicyDetails(IN CustomerId INT)
BEGIN
    SELECT P.PolicyNo, P.PolicyType, P.PremiumAmount, P.PaymentFrequency
    FROM Policy P
    WHERE P.CustomerId = CustomerId;
END//
DELIMITER ;

call GetCustomerPolicyDetails(2);

--  For every record deletion in Customer table, for future reference,  insert all details in Customer_history table

DELIMITER //
CREATE TRIGGER CustomerDeletionTrigger BEFORE DELETE ON Customer
FOR EACH ROW
BEGIN
    INSERT INTO CustomerHistory (CustomerId, FirstName, LastName, Email, Phone, Address, DeletionDate)
    VALUES (OLD.CustomerId, OLD.CustomerFirstName, OLD.CustomerLastName, OLD.CustomerEmail, OLD.CustomerPhone, OLD.CustomerAddress, NOW());
END;
//
DELIMITER ;

-- Update / insert the following fields in Premium payment Table for all insertion and updations with system date and logged in user (Fields : Updated_date, updated_user)

DELIMITER //
CREATE TRIGGER PremiumPaymentUpdateTrigger BEFORE INSERT ON PremiumPayment
FOR EACH ROW
BEGIN
    SET NEW.PremiumUpdated_date = NOW();
    SET NEW.PremiumUpdated_user = USER();
END;
//
DELIMITER ;

--  Ensure that number of claims are regulated while creating a claim request.

DELIMITER //
CREATE TRIGGER ClaimRegulationTrigger BEFORE INSERT ON Claim
FOR EACH ROW
BEGIN
    DECLARE CustomerClaimCount INT;
    DECLARE MaxClaimsPerYear INT;
    
    -- Get the maximum number of claims allowed for the policy type
    SELECT MaxClaimsPerYear INTO MaxClaimsPerYear
    FROM PolicyClaimLimits
    WHERE PolicyType = (
        SELECT PolicyType
        FROM Policy
        WHERE PolicyNo = NEW.PolicyNo
    );
    
    -- Get the number of claims made by the customer in the current year
    SELECT COUNT(*) INTO CustomerClaimCount
    FROM Claim
    WHERE CustomerId = NEW.CustomerId
    AND YEAR(ClaimRequestDate) = YEAR(NOW());
    
    -- Check if the number of claims exceeds the maximum allowed
    IF CustomerClaimCount >= MaxClaimsPerYear THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Maximum number of claims exceeded for this policy type in the current year.';
    END IF;
END;
//
DELIMITER ;
