## Parking Location

> `StreetName` length chosen based on the longest street name in the world. `City` length chosen based on the longest city name in the world. `Province` length based on the length of the longest province name in Canada, "Newfoundland and Labrador".

```sql
CREATE TABLE ParkingLocation (
    LocationID INT UNSIGNED NOT NULL AUTO_INCREMENT,
    NumSpaces INT UNSIGNED NOT NULL DEFAULT 0,
    StreetNum INT UNSIGNED NOT NULL,
    StreetName VARCHAR(100) NOT NULL,
    City VARCHAR(60) NOT NULL,
    Province VARCHAR(25) NOT NULL,
    PostalCode VARCHAR(6) NOT NULL,
    PRIMARY KEY ( LocationID )
);
```

## Member

> `StreetName` length chosen based on the longest street name in the world. `City` length chosen based on the longest city name in the world. `Province` length based on the length of the longest province name in Canada, "Newfoundland and Labrador".

```sql
CREATE TABLE Member (
    MemberID Int UNSIGNED NOT NULL AUTO_INCREMENT,
    FirstName VARCHAR(50) NOT NULL,
    MiddleInit CHAR(1),
    LastName VARCHAR(50) NOT NULL,
    SteetNum INT UNSIGNED NOT NULL,
    StreetName VARCHAR(100) NOT NULL,
    City VARCHAR(60) NOT NULL,
    Province VARCHAR(25) NOT NULL,
    PostalCode VARCHAR(6) NOT NULL,
    CountryCode VARCHAR(20) NOT NULL DEFAULT 1,
    AreaCode VARCHAR(20) NOT NULL,
    PhoneNumber VARCHAR(50) NOT NUll,
    Email VARCHAR(200),
    LicenseNumber VARCHAR(100) NOT NULL,
    MonthlyFee FLOAT(5,2) NOT NULL,
    PRIMARY KEY ( MemberID )
);
```

## Car

```sql
    CREATE TABLE CAR (
    VIN VARCHAR(100) NOT NULL,
    Make VARCHAR(100) NOT NULL,
    Model VARCHAR(100) NOT NULL,
    Year YEAR NOT NULL,
    Odometer INT UNSIGNED NOT NULL DEFAULT 0,
    Location INT UNSIGNED NOT NULL,
    DailyFee FLOAT(13,2) NOT NULL,
    CarStatus VARCHAR(100) NOT NULL,
    CurrentlyRented BOOLEAN NOT NULL DEFAULT 0,
    PRIMARY KEY ( VIN ),
    FOREIGN KEY ( Location ) REFERENCES ParkingLocation(LocationID)
);
```

## Reservation

```sql
CREATE TABLE Reservation (
    ReservationID INT UNSIGNED NOT NULL AUTO_INCREMENT,
    MemberID INT UNSIGNED NOT NULL,
    VIN VARCHAR(100) NOT NULL,
    AccessCode VARCHAR(100) NOT NULL,
    Completed BOOLEAN NOT NULL,
    PickupDate DATE NOT NULL,
    DropOffDate DATE NOT NULL,
    PRIMARY KEY ( ReservationID ),
    FOREIGN KEY ( MemberID ) REFERENCES Member(MemberID),
    FOREIGN KEY ( VIN ) REFERENCES Car(VIN)
);
```

## MaintenanceHist

```sql
CREATE TABLE MaintenanceHist (
    RepairID INT UNSIGNED NOT NULL AUTO_INCREMENT,
    Date DATE NOT NULL,
    Odometer INT UNSIGNED NOT NULL,
    Type VARCHAR(100) NOT NULL,
    Description TEXT,
    VIN VARCHAR(100) NOT NULL,
    PRIMARY KEY ( RepairID, VIN ),
    FOREIGN KEY ( VIN ) REFERENCES Car(VIN)
);
```

## Pickup
```sql
CREATE TABLE Pickup (
    ReservationID INT UNSIGNED NOT NULL,
    Odometer INT UNSIGNED NOT NULL,
    Time TIME NOT NULL,
    Status VARCHAR(10) NOT NULL,
    PRIMARY KEY ( ReservationID ),
    FOREIGN KEY ( ReservationID ) REFERENCES Reservation(ReservationID)
);
```

## Dropoff
```sql
CREATE TABLE DropOff (
    ReservationID INT UNSIGNED NOT NULL,
    Odometer INT UNSIGNED NOT NULL,
    Time TIME NOT NULL,
    Status VARCHAR(10) NOT NULL,
    PRIMARY KEY ( ReservationID ),
    FOREIGN KEY ( ReservationID ) REFERENCES Reservation(ReservationID)
);
```

## RentalComments

```sql
CREATE TABLE RentalComments (
    ReservationID INT UNSIGNED NOT NULL,
    MemberID INT UNSIGNED NOT NULL,
    Rating TINYINT UNSIGNED NOT NULL,
    Comment Text,
    PRIMARY KEY ( ReservationID ),
    FOREIGN KEY ( ReservationID ) REFERENCES Reservation(ReservationID),
    FOREIGN KEY ( MemberID ) REFERENCES Member(MemberID)
);
```


