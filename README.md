###Get a list of all products
GET http://ec2-18-175-206-111.eu-west-2.compute.amazonaws.com/products

### Create a product
POST http://ec2-18-175-206-111.eu-west-2.compute.amazonaws.com/products
Content-Type: application/json

{
  "name": "iMac Pro",
  "price": 4999
}

### GET a product by id
GET http://ec2-18-175-206-111.eu-west-2.compute.amazonaws.com/products/5df118b3c86e5826958b661a

### Update a product by id
PATCH  http://ec2-18-175-206-111.eu-west-2.compute.amazonaws.com/products/5df118b3c86e5826958b661a
Content-Type: application/json

{
  "price": 5999
}


### Delete a product by id
DELETE  http://ec2-18-175-206-111.eu-west-2.compute.amazonaws.com/products/5df118b3c86e5826958b661a

### 404 route Not Found
GET http://ec2-18-175-206-111.eu-west-2.compute.amazonaws.com/abc_xyz



































#hrXWgw4Q127uqZJ3
