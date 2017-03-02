## Parking Location
```sql
CREATE TABLE ParkingLocation (
    LocationID INT NOT NULL AUTO_INCREMENT,
    NumSpaces INT NOT NULL,
    StreetNum INT NOT NULL,
    StreetName VARCHAR(100) NOT NULL,
    City VARCHAR(60) NOT NULL,
    Province VARCHAR(25) NOT NULL,
    PostalCode VARCHAR(6) NOT NULL,
    PRIMARY KEY ( LocationID )
);
```



