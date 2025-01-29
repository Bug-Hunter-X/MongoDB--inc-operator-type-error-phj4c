# MongoDB $inc operator type error
This example demonstrates an incorrect use of the `$inc` operator in a MongoDB update operation. The `$inc` operator is used to increment a numerical field by a given value, but in this case a string is provided which will lead to an error.

## Bug
The following code attempts to increment the `age` field by 1 but will fail due to type mismatch.
```javascript
db.collection.updateOne({name: "John"}, {$inc: {age: "1"}});
```
## Solution
The correct way to use the `$inc` operator is to provide a numerical value:
```javascript
db.collection.updateOne({name: "John"}, {$inc: {age: 1}});
```