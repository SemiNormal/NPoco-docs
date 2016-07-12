These helpers allow you to map a query to an object that has nested objects.
Given the following classes:

```csharp
    public class User
    {
        public int UserId { get; set; }
        public string Name { get; set; }
        public Address Address { get; set; }
    }

    public class Address
    {
        public string Street { get; set; }
        public string City { get; set; }
    }
```
and the following query:

```csharp
IDatabase db = new Database("connStringName");
var users = db.Fetch<User, Address>("select u.UserId, u.Name, u.Street, u.City from Users");
```

This will give you a list of `User` objects with the nested class `Address` mapped.

**Note:**

1. The order of the columns is extremely important. The columns in the query need to be specified in the same order as the generic parameters are specified. eg. The `User` columns are specified first, then the `Address` columns next.
2. If you are mapping to objects that are also used for inserting data then you will need to make sure you ignore the `Address` property using the [`[ResultColumn]`](https://github.com/schotime/NPoco/wiki/Mapping) attribute. From v3, you will additionally need the `[ComplexMapping]` attribute.
