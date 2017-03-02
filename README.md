## Parking Location
```sql
CREATE TABLE ParkingLocation (
    LocationID INT NOT NULL AUTO_INCREMENT,
    NumSpaces INT NOT NULL,
    StreetNum INT NOT NULL,
    StreetName VARCHAR(100),
    City VARCHAR(60),
    Province VARCHAR(25),
    PostalCode VARCHAR(6),
    PRIMARY KEY ( LocationID )
);
```



