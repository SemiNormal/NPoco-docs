Welcome to the NPoco wiki! NPoco is a fork of PetaPoco with a handful of extra features.

### Getting Started: Your first query

```csharp
public class User 
{
    public int UserId { get;set; }
    public string Email { get;set; }
}

using (IDatabase db = new Database("connStringName")) 
{
    List<User> users = db.Fetch<User>("select userId, email from users");
}
```

**Note:** `Database` needs to be disposed to close the connection (think of it as your connection object).

This works by mapping the column names to the property names on the ``User`` object. This is a case-insensitive match.  
There is no mapping setup needed for this (query only) scenario. 

Available on NuGet: [![Nuget](https://img.shields.io/nuget/v/NPoco.svg)](https://www.nuget.org/packages/NPoco/)  
Also checkout the [JabbR room](https://jabbr.net/#/rooms/NPoco) if you have a question.
Here are the [release notes](https://github.com/schotime/NPoco/wiki/Release-Notes).

### Standard Features

1.  [Mapping](https://github.com/schotime/NPoco/wiki/Mapping)  
2.  [Query Single Object](https://github.com/schotime/NPoco/wiki/Query-Single-Object)
3.  [Create Read Update Delete](https://github.com/schotime/NPoco/wiki/Create-Read-Update-Delete)
4.  [Query List](https://github.com/schotime/NPoco/wiki/Query-List)
5.  [Paging](https://github.com/schotime/NPoco/wiki/Query-Paging)
6.  [SQL Transaction Support](https://github.com/schotime/NPoco/wiki/SQL-Transaction-Support)

### Extras

1.  [Query onto an existing object](https://github.com/schotime/NPoco/wiki/Map-to-an-Existing-Object)  
2.  [One-to-Many query helpers](https://github.com/schotime/NPoco/wiki/One-to-Many-Query-Helpers)
3.  [Mapping to Nested Objects query helpers](https://github.com/schotime/NPoco/wiki/Mapping-to-Nested-Objects)
4.  [Dictionary&lt;string, object&gt; and object[] queries for dynamic results](https://github.com/schotime/NPoco/wiki/Dictionary-and-Object-Array-Queries)
5.  [Change tracking for updates](https://github.com/schotime/NPoco/wiki/Change-Tracking-for-Updates)
6.  [Composite Primary Key support](https://github.com/schotime/NPoco/wiki/Composite-Primary-Keys)
7.  [Queries that returns Multiple Result Sets](https://github.com/schotime/NPoco/wiki/Multiple-Result-Sets)
8.  [Fluent Mappings including Conventional based mappings](https://github.com/schotime/NPoco/wiki/Fluent-Mappings-including-Conventional)
9.  [Simple LINQ Queries](https://github.com/schotime/NPoco/wiki/Simple-LINQ-Queries) v2+
10. [Query Provider](https://github.com/schotime/NPoco/wiki/Query-Provider)
11. [Version column support](https://github.com/schotime/NPoco/wiki/Version-column-support)
12. IDatabase interface
13. [Sql Templating](https://github.com/schotime/NPoco/wiki/Sql-Templating)
14. [Debugging/Profiling](https://github.com/schotime/NPoco/wiki/Debugging-and-Profiling) (MiniProfiler/Glimpse)

Each of these features will be explained in their own page.
