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

## MaintenanceHist

```sql

```

## Pickup
# NOT GOOD
```sql
CREATE TABLE Pickup (
    ReservationID INT NOT NULL AUTO_INCREMENT,
    Odometer FLOAT(20, 4) NOT NULL DEFAULT 0,
    Date DATE NOT NULL DEFAULT CURRENT_DATE,
    Status VARCHAR(10) NOT NULL,
    FOREIGN KEY ( ReservationID ) REFERENCES Reservation( ReservationID ),
    PRIMARY KEY ( ReservationID )
);
```


