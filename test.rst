Getting Started
===============

NPoco is installed via nuget using the following command::

    PM> Install-Package NPoco 

Your first query
================

.. code-block:: csharp

  public class User 
  {
      public int UserId { get;set; }
      public string Email { get;set; }
  }
  
  using (IDatabase db = new Database("connStringName")) 
  {
      List<User> users = db.Fetch<User>("select userId, email from users");
  }


  

**Note:** `Database` needs to be disposed to close the connection (think of it as your connection object).

This works by mapping the column names to the property names on the ``User`` object. This is a case-insensitive match.  
There is no mapping setup needed for this (query only) scenario. 

Available on NuGet: |ImageLink|_
  
Also checkout the `JabbR room <https://jabbr.net/#/rooms/NPoco>`_ if you have a question.
Here are the `release notes <https://github.com/schotime/NPoco/wiki/Release-Notes>`_.



.. |ImageLink| image:: https://img.shields.io/nuget/v/NPoco.svg 
.. _ImageLink: https://www.nuget.org/packages/NPoco/
