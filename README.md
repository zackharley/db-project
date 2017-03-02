## Parking Location

> `StreeName` length chosen based on the longest street name in the world. `City` length chosen based on the longest city name in the world. `Province` length based on the length of the longest province name in Canada, "Newfoundland and Labrador".

```sql
CREATE TABLE ParkingLocation (
    LocationID INT NOT NULL AUTO_INCREMENT,
    NumSpaces INT NOT NULL DEFAULT 1,
    StreetNum INT NOT NULL,
    StreetName VARCHAR(100) NOT NULL,
    City VARCHAR(60) NOT NULL,
    Province VARCHAR(25) NOT NULL,
    PostalCode VARCHAR(6) NOT NULL,
    PRIMARY KEY ( LocationID )
);
```



