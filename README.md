# wk17-hw-workout-tracker





<!-- creates and changes to classroomdb -->
use classroomdb

<!-- insert one -->
db.students.insert({"name": "Cynthia", "rownumber": "1", "os": "Mac", "hobbies": "music"})

<!-- insert many -->
db.students.insertMany([
  {name: 'Jane', row:1, os:'Mac', hobbies:['Coding', 'Sleeping', 'Karate'] },
  {name: 'Mary', row:2, os:'Mac', hobbies:['Baseball', 'Basketball', 'Tai Chi'] },
  {name: 'Alexis', row:3, os:'Lin', hobbies:['Gaming', 'Reading', 'Gardening'] },
  {name: 'Gary', row:4, os:'Mac', hobbies:['Walking', 'Reading', 'Mountain Climbing'] },
  {name: 'Ed', row:5, os:'Win', hobbies:['Coding', 'Karate', 'Scuba Diving'] }
]);


db.students.find().pretty()
db.students.find("name": "Cynthia").pretty()
db.students.find("os": "Mac").pretty()



<!-- update -->
db.places.update({“country”: “Morocco”}, {$set: {“continent”: “Africa”}}) 
<!-- update all -->
db.places.update({“country”: “Morocco”}, {$set: {“continent”: “Africa”}}, {multi: true})

<!-- $set  -->
new column and existing

<!-- $push -->
new array

<!-- removing a particular row / document-->
 db.places.remove({“country”: “Morocco”}) 
<!-- removing everything within the table -->
 db.places.remove({})

<!-- push new column -->
db.places.update({“country”: “Morocco”}, {$push: {“new column”: “new row”}})

<!-- drop table  -->
db.places.drop() 

<!-- drop database -->
db.dropDatabase()

<!-- ascending order to whatever column you use, in this case numlegs-->
> db.students.find().sort({numlegs: 1}))
<!-- descending -->
> db.students.find().sort({numlegs: -1}))
