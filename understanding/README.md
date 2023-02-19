# MongoDB CRUD Operations

### Show DB

```
show dbs
```

### Create DB

```
use <db_name>
```

## CRUD BASICS

### Create

```
insertOne(data, options)
insertMany(data, options)
```

### Read

```
find(filters, options)
findOne(filters, options)
```

### Update

```
updateOne(filter, data, options)
updateMany(filter, data, options)
replaceOne(filter, data, options)
```

### Delete

```
deleteOne(filter, options)
deleteMany(filter, options)
```

## Examples Queries

```
db.flightData.deleteOne({departureAirport:"STV"})
db.flightData.insertOne({"departureAirport":"STV", arrivalAirport: "BLR", "airCraft":"Indigo",distance: 1800,"intercontinental":false})
db.flightData.updateOne({ airCraft: "Indigo" }, { $set: { marker: "delete" } })
db.flightData.updateMany({}, { $set: { marker: "delete" } })
db.flightData.deleteMany({marker: "toDelete"})
db.flightData.find()
db.flightData.insertMany([
  {
    "departureAirport": "MUC",
    "arrivalAirport": "SFO",
    "aircraft": "Airbus A380",
    "distance": 12000,
    "intercontinental": true
  },
  {
    "departureAirport": "LHR",
    "arrivalAirport": "TXL",
    "aircraft": "Airbus A320",
    "distance": 950,
    "intercontinental": false
  }
])
db.flightData.find({intercontinental: true})
db.flightData.find({distance: {$gt: 10000}})
db.flightData.findOne({distance: {$gt: 900}})
db.passengers.find({}, {name: 1})
```
