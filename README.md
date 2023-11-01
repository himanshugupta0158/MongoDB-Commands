# MongoDB-Commands

MongoDB Commands :
1. Database Commands
- View all databases
```bash
show dbs
```

- Create a new or switch databases 
```bash
use dbName
```

- View current Database
```bash
db
```

- Delete Database 
```bash
db.dropDatabase()
```

2. Collection Commands
- Show Collections
```bash
show collections
```

- Create a collection named 'comments'
```bash
db.createCollection('comments')
```

- Drop a collection named 'comments'
```db.comments.drop()```

3. Row(Document) Commands
- Show all Rows in a Collection 
```bash
db.comments.find()
```

- Show all Rows in a Collection (Prettified)
```bash
db.comments.find().pretty()
```

- Find the first row matching the object
```bash
db.comments.findOne({name: 'Jake'})
```

- Insert One Row
```bash
db.comments.insert({
    'name': 'Jake',
    'lang': 'JavaScript',
    'member_since': 5
 })
```

- Insert many Rows
```bash
db.comments.insertMany([{
    'name': 'Jake',
    'lang': 'JavaScript',
    'member_since': 5
    }, 
    {'name': 'Ramesh',
    'lang': 'Python',
    'member_since': 3
    },
    {'name': 'Komal',
    'lang': 'Java',
    'member_since': 4
}])
```

- Search in a MongoDb Database
```bash
db.comments.find({lang:'Python'})
```
- Limit the number of rows in output
```bash
db.comments.find().limit(2)
```
- Count the number of rows in the output
```bash
db.comments.find().count()
```
- Update a row
```bash
db.comments.updateOne({name: 'Shubham'},
{$set: {'name': 'Kush',
    'lang': 'JavaScript',
    'member_since': 51
}}, {upsert: true})
```
- Mongodb Increment Operator
```bash
db.comments.update({name: 'Ramesh'},
{$inc:{
    member_since: 2
}})
```
- Mongodb Rename Operator
```bash
db.comments.update({name: 'Ramesh'},
{$rename:{
    member_since: 'member'
}})
```
- Delete Row 
```bash
db.comments.remove({name: 'Jake'})
```
- Less than/Greater than/ Less than or Eq/Greater than or Eq
```bash
db.comments.find({member_since: {$lt: 90}})
```
```bash
db.comments.find({member_since: {$lte: 90}})
```
```bash
db.comments.find({member_since: {$gt: 90}})
```
db.comments.find({member_since: {$gte: 90}})

