# Mongo-DB-task-1
//  use products // create database

// db.createCollection("cart") // create a collection

// db.carts.insertMany(product.json) // insert data

// acknowledged: true,
// insertedIds: {
//   '0': ObjectId("64383e6e08302387acea4d15"),
//   '1': ObjectId("64383e6e08302387acea4d16"),
//   '2': ObjectId("64383e6e08302387acea4d17"),
//   '3': ObjectId("64383e6e08302387acea4d18"),
//   '4': ObjectId("64383e6e08302387acea4d19"),
//   '5': ObjectId("64383e6e08302387acea4d1a"),
//   '6': ObjectId("64383e6e08302387acea4d1b"),
//   '7': ObjectId("64383e6e08302387acea4d1c"),
//   '8': ObjectId("64383e6e08302387acea4d1d"),
//   '9': ObjectId("64383e6e08302387acea4d1e"),
//   '10': ObjectId("64383e6e08302387acea4d1f"),
//   '11': ObjectId("64383e6e08302387acea4d20"),
//   '12': ObjectId("64383e6e08302387acea4d21"),
//   '13': ObjectId("64383e6e08302387acea4d22"),
//   '14': ObjectId("64383e6e08302387acea4d23"),
//   '15': ObjectId("64383e6e08302387acea4d24"),
//   '16': ObjectId("64383e6e08302387acea4d25"),
//   '17': ObjectId("64383e6e08302387acea4d26"),
//   '18': ObjectId("64383e6e08302387acea4d27"),
//   '19': ObjectId("64383e6e08302387acea4d28"),
//   '20': ObjectId("64383e6e08302387acea4d29"),
//   '21': ObjectId("64383e6e08302387acea4d2a"),
//   '22': ObjectId("64383e6e08302387acea4d2b"),
//   '23': ObjectId("64383e6e08302387acea4d2c"),
//   '24': ObjectId("64383e6e08302387acea4d2d")
// }
// }


//1) Find all the information about each products

// db.carts.find()        // show all inforamtion

// 2)Find the product price which are between 400 to 800

// products> db.carts.find({product_price: {$gte: 400, $lte: 800}})
// [
//   {
//     _id: ObjectId("64383e6e08302387acea4d15"),
//     id: '1',
//     product_name: 'Intelligent Fresh Chips',
//     product_price: 655,
//     product_material: 'Concrete',
//     product_color: 'mint green'
//   },
//   {
//     _id: ObjectId("64383e6e08302387acea4d17"),
//     id: '3',
//     product_name: 'Refined Steel Car',
//     product_price: 690,
//     product_material: 'Rubber',
//     product_color: 'gold'
//   },
//   {
//     _id: ObjectId("64383e6e08302387acea4d18"),
//     id: '4',
//     product_name: 'Gorgeous Plastic Pants',
//     product_price: 492,
//     product_material: 'Soft',
//     product_color: 'plum'
//   },
//   {
//     _id: ObjectId("64383e6e08302387acea4d1a"),
//     id: '6',
//     product_name: 'Awesome Wooden Towels',
//     product_price: 474,
//     product_material: 'Plastic',
//     product_color: 'orange'
//   },
//   {
//     _id: ObjectId("64383e6e08302387acea4d1b"),
//     id: '7',
//     product_name: 'Practical Soft Shoes',
//     product_price: 500,
//     product_material: 'Rubber',
//     product_color: 'pink'
//   }
// ]


// 3) Find the product price which are not between 400 to 600
//products> db.carts.find( { product_price: { $not: {$gte: 400, $lte: 600} } } )


//4) List the four product which are grater than 500 in price

//db.carts.find({product_price: {$gt: 500}}).limit(4)


//5)Find the product name and product material of each products


//products> db.carts.find({}, { product_name: 1,product_material:1 });

// 6) Find the product with a row id of 10

//products> db.carts.find( { "id": "10" } )
// [
//     {
//       _id: ObjectId("64383e6e08302387acea4d1e"),
//       id: '10',
//       product_name: 'Generic Wooden Pizza',
//       product_price: 84,
//       product_material: 'Frozen',
//       product_color: 'indigo'
//     }
//   ]


// 7) Find only the product name and product material
//// db.carts.find({},{_id:0,id:0,product_price:0,product_color:0})


//8) Find all products which contain the value of soft in product material 

//db.carts.find({"product_material": "Soft"});

//9)Find products which contain product color indigo  and product price 492.00

// db.carts.find({"product_color": "indigo","product_price":492});

// 10) Delete the products which product price value are same
