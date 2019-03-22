# user

### create user:
```graphql
mutation {
  createUser(user:{name:"gul",age:20,email:"test@live.cn"}) {
    name
    age
    email
  }
}
```
### query users:
```graphql
{
  users{
    _id
    name
    age
    email
  }
}
```
### query user with ID:
```graphql
{
  user(_id: "5c937c9e6b1e7720104bb8aa"){
    _id
    name
    email
    age
  }
}
```
### mutation update user
upate user name from id
```graphql
mutation{
  updateUser(_id: "5c937eb2d2a2722988b39573",user:{name: "gulber"}){
    name
  }
}
```

# post

### mutation create post
```graphql
mutation{
  createPost(post:
    { title: "First Post",
      body: "Body of my Post",
      published: true,
      author: "5c937eb2d2a2722988b39573"
    })
  	{
      title
      body
      published
      author{
       _id
       name
       email
    	}
    }
}
```
### query posts
```graphql
query{
  posts{
    title
    body
    author{
      name
    }
  }
}
```

# comment

### mutation create comment
```graphql
mutation{
  createComment(comment:{
    text: "hello men",
    author: "5c937eb2d2a2722988b39573"
    post: "5c9445c8e591800340da8d17",
  })
  {
    text
    author{
      _id
    }
  }
}
```
### query comments
```graphql
query{
  comments{
    text
    author{
      name
    }
  }
}
```
### mutation delete comment
```graphql
mutation{
  deleteComment(_id:"5c944a842bc8d92e78c6d7b8"){
    _id
  }
}
```
