
Features
--------

- **Local Authentication** using Email and Password
- MVC Project Structure
- GraphQL Mutations, Queries, Resolvers
- **Account Management**
     - Register
     - Login
     - Update profile
     - Profile Details
     - Add user address
     - Update Address
     - Remove Address
- Cron job scheduler
- JSON Web Token (JWT) Sign in

Query & Mutation
----------------

### ADD USER

```
mutation {
  addUser(name: "Sunil Kumar", email: "sunilkumar707@yahoo.in", mobileNumber:"8867371492", password: "123567"){
    id
    name
    email
    mobileNumber
  }
}
```

### UPDATE

```
mutation {
  updateUser(name: "Ravi Sanker"){
    id
    name
    email
    mobileNumber
  }
}
```

### LOGIN

```
mutation {
  loginUser(mobileNumber: "8867371492", password:"1234567") {
    id
    token
    name
    email
  }
}
```

### ADD ADDRESS

```
mutation {
  addUserAddress(street: ["s1", "s2"], 
    city:"Dehradun", 
    countryId: "IN", 
    addressType: "home",
    postcode:"23455"
  ) {
    id
    street
    city
    countryId
    landmark
    locality
    addressType
    postcode
  }
}
```

### UPDATE ADDRESS

```
mutation {
  updateUserAddress(id: "59e4d803d3528728b99b3c53",
    street: ["Nesh", "Indra Road"], 
    city:"Dehradun", 
    countryId: "IN", 
    addressType: "home",
    postcode:"234551"
  ) {
    id
    street
    city
    countryId
    landmark
    locality
    addressType
    postcode
  }
}
```

### DELETE ADDRESS

```
mutation {
  deleteUserAddress(
   id: "59e4dc6b875e8829539b20d7"
  ){
    message
  }
}
```

### ALL ADDRESS

```
query {
  me{
    address{
      street
      city
    }
  }
}
```


### ADDRESS BY ID

```
query {
  userAddress(id: "59e4d803d3528728b99b3c53"){
    id
    city
    street
    countryId
  }
}
}
```