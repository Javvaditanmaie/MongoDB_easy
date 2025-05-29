# MongoDB_easy
**1. List All Products in the "Electronics" Category:**

- **Task:** Write an aggregation query to find all documents where the `category` is "Electronics".
- **Hint:** Use the `$match` stage.
- **Expected Output (structure, `_id` will vary):**

- <Pre>db.products.aggregate([{
$match:{
category:"Electronics"

}
},{
$project:{
_id:1,
name:1,
category:1,
price:1,
quantity:1}
}]).pretty()</Pre>

![image](https://github.com/user-attachments/assets/82f7c119-3afe-48c3-8a15-8d72b62233ba)

**2. Count Products per Category:**

- **Task:** Write an aggregation query to count how many products belong to each `category`.
- **Hint:** Use the `$group` stage with the `$sum` accumulator.
- **Expected Output (order might vary):**
<pre>
  db.products.aggregate([
  {
    $group: {
      _id: "$category",
      count: { $sum: 1 }
    }
  }
]).pretty()
</pre>

![image](https://github.com/user-attachments/assets/b9cea459-5371-49c2-9878-fa69f4fc0db3)

**3. Product Names and Prices, Sorted by Price (Descending):**

- **Task:** Write an aggregation query to display only the `name` and `price` of each product, sorted by `price` from highest to lowest. Do not include the `_id` field.
- **Hint:** Use `$project` and `$sort`.

<pre> 
  db.products.aggregate([{
$project:{
_id:0,
name:1,
price:1
}
  },{
$sort:{price:-1}
}
]).pretty();
</pre>

![image](https://github.com/user-attachments/assets/6c69597a-5117-47bd-a1dd-e1689abd8140)
![image](https://github.com/user-attachments/assets/eec52e32-4122-485b-a66f-56c83e10fc28)

