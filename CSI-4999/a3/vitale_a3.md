1. `db.students.find()`
   ![[Pasted image 20250727203359.png]]
2. `db.students.find({ age: { $gt: 21 } })`
   ![[Pasted image 20250727203335.png]]
3. `db.students.find({}, { name: 1, major: 1 })`
   ![[Pasted image 20250727204123.png]]
4. `db.students.updateOne({ name: "Bob" }, { $set: { major: "Statistics" } })`
   ![[Pasted image 20250727204439.png]]
5. `db.students.updateOne({ name: "Alice"}, { $inc: { age: 1 } })`
   ![[Pasted image 20250727204619.png]]
6. `db.students.deleteOne({ name: "Charlie" })`
   ![[Pasted image 20250727204648.png]]
