By default no mapping is required. It will be assumed that the table name will be the class name and the primary key will be 'Id' if its not specified with the attributes below.

Basic mapping is done via attributes. The most used ones are:

1. ``[TableName]``
This takes a "name" parameter which indicates the table for which the Poco class will be mapped to.

2. ``[PrimaryKey]``
This has a "columnName" parameter which takes the column name of the primary key for the table. Multiple primary keys can be specified by separating the columns with a comma. There is also an "autoIncrement" property which is used to indicate whether the primary key column is auto incremented e.g. identity column in Sql Server. By default this is true. For Oracle there is also a "sequenceName" property which will be used when inserting data with Oracle.

3. ``[Column]`` 
This is used if the column name does not match the property name. 

4. ``[Ignore]``
This property will be ignored and cannot be mapped to.

5. ``[ResultColumn]``
Properties marked with the Result column can be mapped into, however these properties will not be included in inserts or updates. Note: These columns will need to be explicitly specified in the SQL. It will not be included in the auto generated SQL.

6. ``[ComputedColumn]``
Properties with the Computed column attribute work the same way as the Result column attributes however they **will** be auto selected in the SQL.

7. ``[SerializedColumn]`` (**v3+ only**)
Properties with the Serialized column attribute will serialize their data with the default serializer unless changed by implementing a `IColumnSerializer`. There is a NPoco.JsonNet library which allows you to use the `JsonNetColumnSerializer`. These are configured once by:
```csharp 
DatabaseFactory.ColumnSerializer = new JsonNetColumnSerializer();
```

### Example
```csharp
[TableName("Users")]
[PrimaryKey("UserId")]
public class User
{
    public int UserId { get;set; }
    [Column("emailAddress")]
    public string Email { get;set; }
    [ResultColumn]
    public string ExtraInfo { get;set; }
    [Ignore]
    public int Temp { get;set; }
}
```

If you don't like attribute based mapping, the take a look at [fluent / convention based mapping](https://github.com/schotime/NPoco/wiki/Fluent-Mappings-including-Conventional)
