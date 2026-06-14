# 📚 BCA Semester - 5

## 💻 Web Development Using ASP.NET

> **Subject Code:** BCA-101  
> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 5

---

# 📑 Unit 4 : Advanced ASP.NET Concepts

## _Topics_

### Caching in ASP.NET

- Page Output Caching
- Partial Page Caching
- Absolute Cache Expiration
- Sliding Cache Expiration
- Data Caching

---

### XML and Data Handling

- Reading DataSets From XML
- Writing DataSets With XML

---

### Web Services

- Introduction to Web Services
- HTTP Protocol
- SOAP (Simple Object Access Protocol)
- UDDI (Universal Description, Discovery and Integration)
- XML in Web Services
- Creating a Web Service

---

### Web Configuration

- Introduction to Web.Config File
- Common Configuration Sections
- AppSettings Section

---

### Diagnostics and Debugging

- Tracing in ASP.NET
- Custom Errors Handling

---

### Security in ASP.NET

- Authentication
- Authorization

---

### Deployment

- Deployment of ASP.NET Application in Web Server

# ASP.NET Caching

## Page Output Caching and Partial Page Caching (In-Depth Explanation)

---

# Introduction to Caching

Caching is a technique used to improve the performance of a web application by storing frequently used data, pages, or parts of pages in memory so that the server does not need to regenerate them every time a user requests them.

Without caching:

1. User requests page.
2. Server executes code.
3. Database is accessed.
4. HTML is generated.
5. Response is sent.

With caching:

1. User requests page.
2. Cached content is returned directly.
3. No database call.
4. No page regeneration.
5. Faster response.

---

# Why Caching is Important

## Advantages

### Improved Performance

Cached content is delivered much faster.

### Reduced Server Load

The server does not need to process the same request repeatedly.

### Reduced Database Access

Database queries are minimized.

### Better Scalability

More users can be handled efficiently.

### Improved User Experience

Pages load quickly.

---

# Types of Caching in ASP.NET

ASP.NET provides several caching mechanisms:

1. Page Output Caching
2. Partial Page Caching
3. Data Caching
4. Fragment Caching
5. Application Caching

This chapter focuses on:

- Page Output Caching
- Partial Page Caching

---

# Page Output Caching

## Definition

Page Output Caching stores the entire rendered output of a web page in memory.

When another user requests the same page, ASP.NET sends the cached page instead of executing the page again.

---

# Working of Page Output Caching

Without Cache:

Request
↓
ASP.NET Page
↓
Database
↓
Generate HTML
↓
Send Response

Every request repeats this process.

---

With Cache:

First Request

Request
↓
Generate Page
↓
Store in Cache
↓
Send Response

Subsequent Requests

Request
↓
Return Cached HTML
↓
Send Response

No database access.

---

# OutputCache Directive

Page Output Caching is enabled using:

```asp
<%@ OutputCache Duration="60" VaryByParam="None" %>
```

---

# Attributes of OutputCache

## Duration

Specifies cache lifetime in seconds.

Example:

```asp
<%@ OutputCache Duration="30" VaryByParam="None" %>
```

Cache remains valid for 30 seconds.

---

## VaryByParam

Specifies caching behavior based on query string parameters.

Example:

```asp
<%@ OutputCache Duration="60"
VaryByParam="ProductID" %>
```

Different cache versions are created for different ProductID values.

Example:

```text
Product.aspx?ProductID=1
Product.aspx?ProductID=2
Product.aspx?ProductID=3
```

Three separate cache entries are stored.

---

## VaryByParam="None"

```asp
<%@ OutputCache Duration="60"
VaryByParam="None" %>
```

Only one cache version is created.

---

## VaryByParam="\*"

```asp
<%@ OutputCache Duration="60"
VaryByParam="*" %>
```

Creates separate cache entries for every parameter combination.

---

# Example of Page Output Caching

## ASPX Page

```asp
<%@ Page Language="C#" %>
<%@ OutputCache Duration="30" VaryByParam="None" %>

<!DOCTYPE html>
<html>
<head>
<title>Output Cache Example</title>
</head>
<body>

<h2>Current Time</h2>

<%= DateTime.Now.ToString() %>

</body>
</html>
```

---

# Execution

First Request:

```text
Current Time

10:15:05 AM
```

After Refresh:

```text
Current Time

10:15:05 AM
```

Still same because cached version is returned.

After 30 seconds:

```text
Current Time

10:15:37 AM
```

New cache generated.

---

# Real-Life Example

Suppose an e-commerce website has:

```text
Home Page
Today's Offers
Top Products
Advertisements
```

This content changes rarely.

Caching the entire page:

```asp
<%@ OutputCache Duration="300"
VaryByParam="None" %>
```

Cache valid for 5 minutes.

---

# Benefits of Page Output Caching

## Very Fast

Entire page served from cache.

## Minimal Processing

No page execution.

## No Database Calls

Database traffic reduced.

## Easy Implementation

Only one directive needed.

---

# Limitations of Page Output Caching

## Dynamic Content Issue

Suppose page contains:

```text
Welcome Rohan
Current Time
Shopping Cart Count
```

Different users need different values.

Caching entire page may display incorrect information.

Example:

```text
Welcome Rohan
```

Another user may also see:

```text
Welcome Rohan
```

This is incorrect.

To solve this issue, Partial Page Caching is used.

---

# Partial Page Caching

## Definition

Partial Page Caching caches only specific portions of a page instead of caching the entire page.

Also known as:

```text
Fragment Caching
User Control Caching
```

---

# Why Partial Page Caching?

A page may contain:

```text
Header
Menu
News
Advertisements
Footer
```

These sections rarely change.

But page may also contain:

```text
User Name
Cart Count
Current Balance
```

These change frequently.

Instead of caching entire page:

Cache only static sections.

---

# Partial Page Caching Architecture

Page

├── Header (Cached)
├── Menu (Cached)
├── Advertisement (Cached)
├── User Details (Not Cached)
└── Footer (Cached)

Only selected portions are stored in cache.

---

# User Control in ASP.NET

Partial caching is generally applied to:

```text
.ascx
```

User controls.

Example:

```text
Header.ascx
Menu.ascx
Offers.ascx
```

---

# Creating Cached User Control

## Step 1

Create User Control

```text
Offers.ascx
```

---

## Step 2

Add OutputCache Directive

```asp
<%@ Control Language="C#" %>
<%@ OutputCache Duration="60"
VaryByParam="None" %>
```

---

## Step 3

Display Dynamic Data

```asp
<h2>Today's Offer</h2>

<%= DateTime.Now.ToString() %>
```

---

## Complete Offers.ascx

```asp
<%@ Control Language="C#" %>
<%@ OutputCache Duration="60"
VaryByParam="None" %>

<h2>Today's Offer Time</h2>

<%= DateTime.Now.ToString() %>
```

---

# Using User Control in Page

Default.aspx

```asp
<%@ Register Src="Offers.ascx"
TagName="Offers"
TagPrefix="uc" %>

<!DOCTYPE html>
<html>
<body>

<h1>Welcome User</h1>

<uc:Offers runat="server" />

</body>
</html>
```

---

# Execution

Page refreshes:

```text
Welcome User

Today's Offer Time
10:00:15
```

Refresh again:

```text
Welcome User

Today's Offer Time
10:00:15
```

Offer section remains cached.

After 60 seconds:

```text
Today's Offer Time
10:01:20
```

New cached version generated.

---

# Partial Page Caching vs Output Caching

| Feature                 | Output Caching | Partial Page Caching |
| ----------------------- | -------------- | -------------------- |
| Cache Entire Page       | Yes            | No                   |
| Cache Specific Section  | No             | Yes                  |
| Performance             | Very High      | High                 |
| Dynamic Content Support | Limited        | Better               |
| User Specific Content   | Difficult      | Easier               |
| Flexibility             | Low            | High                 |

---

# Real World Example

E-Commerce Website

Page Components:

```text
Header
Navigation Menu
Product Categories
Advertisements
Shopping Cart
User Profile
```

Cache:

```text
Header ✓
Menu ✓
Advertisements ✓
Categories ✓
```

Do Not Cache:

```text
Cart Count
User Profile
Order Details
```

This improves speed while maintaining personalization.

---

# Cache Duration Guidelines

| Content Type   | Recommended Duration |
| -------------- | -------------------- |
| News           | 60 Seconds           |
| Products       | 300 Seconds          |
| Advertisements | 600 Seconds          |
| Static Pages   | 1800 Seconds         |
| FAQ Pages      | 3600 Seconds         |

---

# Best Practices

## Use Output Caching

When:

- Entire page rarely changes.
- Same page shown to all users.

Examples:

- Home Page
- FAQ Page
- About Us

---

## Use Partial Page Caching

When:

- Only some sections are static.
- User-specific content exists.

Examples:

- E-commerce websites
- Social media dashboards
- Banking portals

---

# ASP.NET Data Caching

## Absolute Cache Expiration, Sliding Cache Expiration and Data Caching (In-Depth Explanation)

---

# Introduction to Data Caching

Data Caching is a technique used to store frequently used data in server memory so that it can be reused without repeatedly accessing the database or performing expensive operations.

Instead of:

```text
User Request
      ↓
Database Query
      ↓
Process Data
      ↓
Display Result
```

Every time a user makes a request.

We can use:

```text
User Request
      ↓
Cache Check
      ↓
Data Found
      ↓
Display Result
```

This significantly improves application performance.

---

# What is Data Caching?

Data Caching stores application data inside ASP.NET Cache Memory.

Examples:

- Product List
- Employee Records
- Configuration Settings
- News Articles
- Frequently Accessed Reports

---

# Why Data Caching?

Without Caching:

```text
100 Users
     ↓
100 Database Queries
```

With Caching:

```text
100 Users
     ↓
1 Database Query
     ↓
99 Cache Reads
```

Result:

- Faster Execution
- Less Database Load
- Better Scalability
- Improved User Experience

---

# ASP.NET Cache Object

ASP.NET provides a built-in Cache object.

Syntax:

```csharp
Cache["KeyName"] = Value;
```

Example:

```csharp
Cache["Message"] = "Welcome to ASP.NET";
```

Retrieve Data:

```csharp
string msg = Cache["Message"].ToString();
```

---

# Data Caching Architecture

```text
                Database
                    │
                    ▼
              Fetch Data
                    │
                    ▼
                 Cache
                    │
      ┌─────────────┴─────────────┐
      ▼                           ▼
  User 1                     User 2
```

Database is accessed only once.

---

# Types of Cache Expiration

ASP.NET provides two major expiration policies:

1. Absolute Cache Expiration
2. Sliding Cache Expiration

---

# Absolute Cache Expiration

## Definition

Absolute Expiration removes cached data automatically after a fixed amount of time, regardless of how often the data is accessed.

---

# Working

Suppose:

```text
Cache Duration = 60 Seconds
```

Timeline:

```text
10:00:00  Data Added
10:00:20  Accessed
10:00:40  Accessed
10:00:55  Accessed
10:01:00  Removed
```

Even though data is used repeatedly, it expires exactly after 60 seconds.

---

# Visual Representation

```text
Data Added
    │
    ▼
60 Seconds Fixed Lifetime
    │
    ▼
Data Removed
```

Access frequency does not matter.

---

# Syntax

```csharp
Cache.Insert(
    "Products",
    data,
    null,
    DateTime.Now.AddMinutes(5),
    System.Web.Caching.Cache.NoSlidingExpiration
);
```

---

# Parameters

```csharp
Cache.Insert(
    Key,
    Value,
    Dependency,
    AbsoluteExpiration,
    SlidingExpiration
);
```

---

# Example

```csharp
Cache.Insert(
    "Message",
    "Welcome User",
    null,
    DateTime.Now.AddMinutes(1),
    System.Web.Caching.Cache.NoSlidingExpiration
);
```

Meaning:

```text
Current Time = 10:00 AM

Expiration = 10:01 AM
```

After 10:01 AM data is automatically removed.

---

# Real-Life Example

Weather Information

```text
Weather data changes every 30 minutes.
```

Cache:

```csharp
DateTime.Now.AddMinutes(30)
```

After 30 minutes:

```text
Cache Removed
Fresh Weather Data Loaded
```

---

# Advantages of Absolute Expiration

### Predictable

Fixed expiration time.

### Fresh Data

Data is refreshed regularly.

### Easy Management

Simple implementation.

---

# Disadvantages

### May Expire Too Soon

Frequently used data is still removed.

### More Database Requests

Popular data may need to be reloaded.

---

# Sliding Cache Expiration

## Definition

Sliding Expiration removes cached data only if it is not accessed for a specified time period.

Each access resets the expiration timer.

---

# Working

Suppose:

```text
Sliding Time = 60 Seconds
```

Timeline:

```text
10:00:00 Added
10:00:30 Accessed
10:01:00 Accessed
10:01:30 Accessed
10:02:00 Accessed
```

Expiration keeps moving forward.

Cache remains alive.

---

# Visual Representation

```text
Added
  │
  ▼
60 Seconds
  │
Accessed
  │
Reset Timer
  │
60 Seconds
  │
Accessed
  │
Reset Timer
```

Timer continuously restarts.

---

# Syntax

```csharp
Cache.Insert(
    "Products",
    data,
    null,
    System.Web.Caching.Cache.NoAbsoluteExpiration,
    TimeSpan.FromMinutes(2)
);
```

---

# Example

```csharp
Cache.Insert(
    "UserList",
    users,
    null,
    Cache.NoAbsoluteExpiration,
    TimeSpan.FromMinutes(1)
);
```

Meaning:

```text
If data is not accessed for 1 minute
→ Remove Cache
```

---

# Practical Example

Suppose:

```text
Cache Added : 10:00
Sliding Time : 1 Minute
```

Case 1:

```text
10:00 Added
10:01 Not Accessed
Removed
```

Cache expires.

---

Case 2:

```text
10:00 Added
10:00:40 Accessed
10:01:20 Accessed
10:02:00 Accessed
```

Cache remains active.

---

# Real-Life Example

Online Shopping Website

Popular Product List

Users continuously access:

```text
Trending Products
Best Sellers
Today's Deals
```

Sliding Expiration keeps these items cached as long as users are actively viewing them.

---

# Advantages of Sliding Expiration

### Efficient Memory Usage

Unused data automatically removed.

### Keeps Popular Data Available

Frequently used data remains cached.

### Reduces Database Queries

Popular items stay in memory.

---

# Disadvantages

### Less Predictable

Expiration time changes dynamically.

### Stale Data Risk

Frequently accessed data may remain cached for a long time.

---

# Absolute vs Sliding Expiration

| Feature              | Absolute Expiration | Sliding Expiration |
| -------------------- | ------------------- | ------------------ |
| Expiration Time      | Fixed               | Dynamic            |
| Access Resets Timer  | No                  | Yes                |
| Frequently Used Data | Removed on Schedule | Remains Cached     |
| Data Freshness       | Better              | Lower              |
| Database Load        | Higher              | Lower              |
| Predictability       | High                | Medium             |

---

# Data Caching Example

## Storing Data

```csharp
protected void Page_Load(object sender, EventArgs e)
{
    if(Cache["UserName"] == null)
    {
        Cache["UserName"] = "Rohan";
    }
}
```

---

# Retrieving Data

```csharp
string name = Cache["UserName"].ToString();

Response.Write(name);
```

Output:

```text
Rohan
```

---

# Complete Data Cache Example

```csharp
protected void Page_Load(object sender, EventArgs e)
{
    if(Cache["CurrentTime"] == null)
    {
        Cache.Insert(
            "CurrentTime",
            DateTime.Now.ToString(),
            null,
            DateTime.Now.AddMinutes(2),
            Cache.NoSlidingExpiration
        );
    }

    Response.Write(Cache["CurrentTime"]);
}
```

---

# Execution

First Request:

```text
10:15:00 AM
```

Second Request:

```text
10:15:00 AM
```

Still cached.

After 2 Minutes:

```text
10:17:10 AM
```

New cache created.

---

# When to Use Absolute Expiration?

Use for:

- Weather Information
- Stock Prices
- News Updates
- Exchange Rates
- Time-Sensitive Data

Because data must refresh after a fixed interval.

---

# When to Use Sliding Expiration?

Use for:

- Product Catalog
- Frequently Viewed Pages
- User Preferences
- Popular Reports
- Search Results

Because frequently used data should remain cached.

---

# XML and Data Handling in ASP.NET

## Reading DataSets From XML and Writing DataSets With XML (In-Depth Explanation)

---

# Introduction to XML

## What is XML?

XML stands for:

```text
eXtensible Markup Language
```

XML is a text-based format used to store, transport, and exchange data between different applications and platforms.

---

## Example of XML

```xml
<?xml version="1.0"?>

<Students>
    <Student>
        <Id>101</Id>
        <Name>Rohan</Name>
        <City>Rajkot</City>
    </Student>

    <Student>
        <Id>102</Id>
        <Name>Rahul</Name>
        <City>Ahmedabad</City>
    </Student>
</Students>
```

---

# Why XML?

XML is platform independent.

It can be used between:

```text
ASP.NET
Java
PHP
Python
Android
Windows Applications
```

---

# Advantages of XML

### Easy to Read

Both humans and machines can read it.

### Platform Independent

Works on all operating systems.

### Data Exchange

Used to exchange information between systems.

### Self Descriptive

Tags describe data clearly.

Example:

```xml
<Name>Rohan</Name>
```

Tag itself explains the data.

---

# XML and ADO.NET

ADO.NET provides direct support for XML.

Data can be:

```text
Database
    ↓
DataSet
    ↓
XML File
```

or

```text
XML File
    ↓
DataSet
    ↓
Application
```

---

# DataSet and XML

## What is DataSet?

A DataSet is an in-memory collection of tables.

It can:

```text
Store Data
Read XML
Write XML
Store Relations
Store Constraints
```

---

# XML Support in DataSet

DataSet provides methods:

| Method           | Purpose          |
| ---------------- | ---------------- |
| ReadXml()        | Read XML File    |
| WriteXml()       | Write XML File   |
| ReadXmlSchema()  | Read XML Schema  |
| WriteXmlSchema() | Write XML Schema |

---

# Reading DataSets From XML

## Definition

Reading DataSet from XML means loading XML data into a DataSet object.

---

# Process

```text
XML File
    ↓
ReadXml()
    ↓
DataSet
    ↓
Application
```

---

# XML File Example

Student.xml

```xml
<?xml version="1.0"?>

<Students>

    <Student>
        <Id>101</Id>
        <Name>Rohan</Name>
        <City>Rajkot</City>
    </Student>

    <Student>
        <Id>102</Id>
        <Name>Rahul</Name>
        <City>Ahmedabad</City>
    </Student>

</Students>
```

---

# Reading XML Using ReadXml()

## Syntax

```csharp
DataSet ds = new DataSet();

ds.ReadXml("Student.xml");
```

---

# Explanation

```csharp
DataSet ds = new DataSet();
```

Creates empty DataSet.

---

```csharp
ds.ReadXml("Student.xml");
```

Loads XML data into DataSet.

---

# Complete Example

```csharp
using System;
using System.Data;

class Program
{
    static void Main()
    {
        DataSet ds = new DataSet();

        ds.ReadXml("Student.xml");

        foreach(DataRow row in ds.Tables[0].Rows)
        {
            Console.WriteLine(
                row["Id"] + " " +
                row["Name"] + " " +
                row["City"]);
        }
    }
}
```

---

# Output

```text
101 Rohan Rajkot
102 Rahul Ahmedabad
```

---

# How ReadXml Works

XML:

```xml
<Student>
    <Id>101</Id>
    <Name>Rohan</Name>
    <City>Rajkot</City>
</Student>
```

Converted into:

| Id  | Name  | City   |
| --- | ----- | ------ |
| 101 | Rohan | Rajkot |

inside DataSet.

---

# Reading XML From Server Path

ASP.NET Example

```csharp
DataSet ds = new DataSet();

string path =
Server.MapPath("Student.xml");

ds.ReadXml(path);
```

---

# Reading XML Schema

## What is XML Schema?

Schema defines:

```text
Data Types
Columns
Structure
Constraints
```

---

# Example

```csharp
DataSet ds = new DataSet();

ds.ReadXmlSchema("Student.xsd");
```

---

# Reading XML Using XmlReader

```csharp
XmlReader reader =
XmlReader.Create("Student.xml");

DataSet ds = new DataSet();

ds.ReadXml(reader);
```

---

# Writing DataSets With XML

## Definition

Writing DataSet with XML means saving DataSet data into an XML file.

---

# Process

```text
Database
    ↓
DataSet
    ↓
WriteXml()
    ↓
XML File
```

---

# Why Write XML?

Used for:

```text
Backup
Data Exchange
Offline Storage
Web Services
Data Migration
```

---

# Syntax

```csharp
ds.WriteXml("Student.xml");
```

---

# Example

Create DataSet manually.

```csharp
DataSet ds = new DataSet();

DataTable dt = new DataTable("Student");

dt.Columns.Add("Id");
dt.Columns.Add("Name");
dt.Columns.Add("City");

dt.Rows.Add("101","Rohan","Rajkot");
dt.Rows.Add("102","Rahul","Ahmedabad");

ds.Tables.Add(dt);

ds.WriteXml("Student.xml");
```

---

# Generated XML

```xml
<?xml version="1.0"?>

<NewDataSet>

  <Student>
      <Id>101</Id>
      <Name>Rohan</Name>
      <City>Rajkot</City>
  </Student>

  <Student>
      <Id>102</Id>
      <Name>Rahul</Name>
      <City>Ahmedabad</City>
  </Student>

</NewDataSet>
```

---

# Writing XML Schema

## Syntax

```csharp
ds.WriteXmlSchema("Student.xsd");
```

---

# Generated XSD Example

```xml
<xs:schema>

 <xs:element name="Student">

  <xs:complexType>

   <xs:sequence>

    <xs:element name="Id"/>

    <xs:element name="Name"/>

    <xs:element name="City"/>

   </xs:sequence>

  </xs:complexType>

 </xs:element>

</xs:schema>
```

---

# Write XML With Schema

## Syntax

```csharp
ds.WriteXml(
    "Student.xml",
    XmlWriteMode.WriteSchema
);
```

---

# Explanation

This saves:

```text
Data
+
Schema
```

inside one XML file.

---

# ASP.NET Example

```csharp
protected void Button1_Click(
object sender,
EventArgs e)
{
    DataSet ds = new DataSet();

    SqlDataAdapter da =
    new SqlDataAdapter(
    "select * from Student",
    connection);

    da.Fill(ds);

    string path =
    Server.MapPath("Student.xml");

    ds.WriteXml(path);

    Response.Write(
    "XML File Created Successfully");
}
```

---

# XML Data Flow in ASP.NET

```text
SQL Server
      ↓
DataSet
      ↓
WriteXml()
      ↓
XML File
```

---

# Reverse Flow

```text
XML File
      ↓
ReadXml()
      ↓
DataSet
      ↓
GridView
```

---

# Display XML Data in GridView

```csharp
DataSet ds = new DataSet();

ds.ReadXml(
Server.MapPath("Student.xml"));

GridView1.DataSource =
ds.Tables[0];

GridView1.DataBind();
```

---

# ReadXml vs WriteXml

| Feature   | ReadXml()     | WriteXml()    |
| --------- | ------------- | ------------- |
| Purpose   | Read XML      | Write XML     |
| Input     | XML File      | DataSet       |
| Output    | DataSet       | XML File      |
| Data Flow | XML → DataSet | DataSet → XML |

---

# ReadXmlSchema vs WriteXmlSchema

| Method           | Purpose             |
| ---------------- | ------------------- |
| ReadXmlSchema()  | Read XSD Schema     |
| WriteXmlSchema() | Generate XSD Schema |

---

# Real-Life Example

School Management System

Database:

```text
Students
Teachers
Courses
```

Export Data:

```text
Database
    ↓
DataSet
    ↓
WriteXml()
    ↓
SchoolData.xml
```

Transfer XML file to another application.

Import:

```text
SchoolData.xml
    ↓
ReadXml()
    ↓
DataSet
    ↓
Display Data
```

---

# Advantages of XML Data Handling

### Platform Independent

Works everywhere.

### Easy Data Exchange

Transfer data between applications.

### Human Readable

Easy to understand.

### Built-In ADO.NET Support

No extra libraries required.

### Data Backup

Can store database data as XML.

---

# Limitations of XML

### Large File Size

More storage than JSON.

### Slower Parsing

Compared to JSON.

### Complex Structure

Nested XML can become difficult.

---

# ASP.NET Web Services

# Introduction to Web Services, HTTP Protocol, SOAP, UDDI, XML in Web Services and Creating a Web Service (Complete In-Depth Guide)

---

# What is a Web Service?

## Definition

A Web Service is a software component that allows two applications to communicate with each other over a network (usually the Internet) regardless of the programming language, operating system, or platform being used.

Simply speaking:

```text
Application A
      ↔
 Web Service
      ↔
Application B
```

A Web Service acts as a bridge between applications.

---

# Real World Example

Suppose:

```text
Amazon Website
```

needs to calculate shipping charges.

Instead of creating its own shipping system, Amazon can use:

```text
FedEx Web Service
```

Process:

```text
Amazon
   ↓
Send Package Details
   ↓
FedEx Web Service
   ↓
Returns Shipping Cost
   ↓
Amazon Displays Cost
```

---

# Why Web Services?

Before Web Services:

```text
Java Application
      X
.NET Application
```

Communication was difficult.

Different:

```text
Programming Languages
Operating Systems
Platforms
Technologies
```

created compatibility problems.

---

# Solution

Web Services use:

```text
HTTP
XML
SOAP
WSDL
UDDI
```

which are platform-independent standards.

---

# Advantages of Web Services

## Platform Independent

Works with:

```text
Java
.NET
PHP
Python
Node.js
Android
iOS
```

---

## Reusable

Same service can be used by multiple applications.

---

## Interoperability

Different systems can communicate easily.

---

## Cost Effective

No need to redevelop existing functionality.

---

## Easy Integration

Applications can be connected quickly.

---

# Web Service Architecture

```text
Client
   │
   ▼
Web Service
   │
   ▼
Database
```

---

# Complete Communication Flow

```text
Client Application
       │
       ▼
HTTP Request
       │
       ▼
Web Service
       │
       ▼
Database
       │
       ▼
XML/SOAP Response
       │
       ▼
Client Application
```

---

# Components of Web Services

```text
HTTP
SOAP
XML
WSDL
UDDI
```

All work together.

---

# HTTP Protocol

---

# What is HTTP?

HTTP stands for:

```text
HyperText Transfer Protocol
```

It is the communication protocol used by Web Services.

---

# Purpose of HTTP

Used to transfer:

```text
Web Pages
Images
Files
SOAP Messages
XML Documents
```

between client and server.

---

# HTTP Communication Model

```text
Client
   │
HTTP Request
   ▼
Server
   │
HTTP Response
   ▼
Client
```

---

# Example

Browser requests:

```text
https://example.com
```

HTTP Request:

```http
GET / HTTP/1.1
Host: example.com
```

Server Response:

```http
HTTP/1.1 200 OK
Content-Type: text/html
```

---

# Common HTTP Methods

| Method | Purpose       |
| ------ | ------------- |
| GET    | Retrieve Data |
| POST   | Send Data     |
| PUT    | Update Data   |
| DELETE | Remove Data   |

---

# HTTP in Web Services

Client sends:

```text
SOAP Request
```

using HTTP.

Server returns:

```text
SOAP Response
```

using HTTP.

---

# SOAP (Simple Object Access Protocol)

---

# What is SOAP?

SOAP stands for:

```text
Simple Object Access Protocol
```

SOAP is an XML-based messaging protocol used to exchange information between applications.

---

# Purpose of SOAP

Allows applications to:

```text
Send Requests
Receive Responses
Call Remote Methods
Exchange Data
```

---

# SOAP Characteristics

### XML-Based

Uses XML format.

### Platform Independent

Works everywhere.

### Language Independent

Supports all languages.

### Protocol Independent

Can use:

```text
HTTP
SMTP
TCP
```

---

# SOAP Architecture

```text
Client
   │
SOAP Request
   ▼
Web Service
   │
SOAP Response
   ▼
Client
```

---

# SOAP Message Structure

```xml
<soap:Envelope>

    <soap:Header>

    </soap:Header>

    <soap:Body>

    </soap:Body>

</soap:Envelope>
```

---

# SOAP Envelope

Root element.

```xml
<soap:Envelope>
</soap:Envelope>
```

Contains entire SOAP message.

---

# SOAP Header

Contains:

```text
Authentication
Security
Transactions
Routing Information
```

Example:

```xml
<soap:Header>

    <Auth>User123</Auth>

</soap:Header>
```

---

# SOAP Body

Contains actual request or response.

Example:

```xml
<soap:Body>

    <GetStudent/>

</soap:Body>
```

---

# SOAP Request Example

```xml
<soap:Envelope>

 <soap:Body>

  <GetStudent>

    <Id>101</Id>

  </GetStudent>

 </soap:Body>

</soap:Envelope>
```

---

# SOAP Response Example

```xml
<soap:Envelope>

 <soap:Body>

  <GetStudentResponse>

   <Name>Rohan</Name>

   <City>Rajkot</City>

  </GetStudentResponse>

 </soap:Body>

</soap:Envelope>
```

---

# Advantages of SOAP

### Secure

Supports security standards.

### Reliable

Well-defined protocol.

### Standardized

Industry standard.

### Platform Independent

Works across technologies.

---

# Disadvantages of SOAP

### Complex

Large XML messages.

### Slow

More processing required.

### Verbose

Large message size.

---

# UDDI (Universal Description Discovery and Integration)

---

# What is UDDI?

UDDI stands for:

```text
Universal Description,
Discovery and Integration
```

UDDI is a directory service used to publish and discover Web Services.

---

# Real World Example

Think of UDDI as:

```text
Phone Directory
```

For Web Services.

---

# Example

Business publishes:

```text
Currency Service
Weather Service
Payment Service
```

into UDDI.

Applications can search and find these services.

---

# UDDI Architecture

```text
Service Provider
        │
 Publish Service
        ▼
      UDDI
        ▲
 Search Service
        │
Service Consumer
```

---

# Functions of UDDI

### Publish Services

Companies register services.

### Discover Services

Clients search services.

### Describe Services

Provides service details.

### Integrate Services

Allows easy integration.

---

# Information Stored in UDDI

```text
Business Name
Service Name
Service Description
WSDL Location
Contact Information
```

---

# XML in Web Services

---

# Why XML?

Different systems need a common language.

XML provides:

```text
Standard Format
Readable Data
Structured Data
Platform Independence
```

---

# Example

```xml
<Student>

    <Id>101</Id>

    <Name>Rohan</Name>

    <City>Rajkot</City>

</Student>
```

---

# XML Communication Process

```text
Client Data
      ↓
Convert to XML
      ↓
Send Through HTTP
      ↓
Server Reads XML
      ↓
Process Request
      ↓
Generate XML Response
```

---

# XML Advantages

### Human Readable

Easy to understand.

### Platform Independent

Universal support.

### Self Describing

Tags explain data.

### Extensible

Custom tags possible.

---

# XML vs Traditional Data

Traditional:

```text
101,Rohan,Rajkot
```

XML:

```xml
<Student>
   <Id>101</Id>
   <Name>Rohan</Name>
   <City>Rajkot</City>
</Student>
```

XML is more descriptive.

---

# Creating a Web Service in ASP.NET

---

# Step 1: Create ASP.NET Website

```text
File
 ↓
New Website
 ↓
ASP.NET Web Service
```

---

# Step 2: Web Service File Created

Example:

```text
Service1.asmx
```

---

# Structure

```csharp
using System.Web.Services;

[WebService]
public class Service1 : WebService
{

}
```

---

# Step 3: Create Web Method

```csharp
using System.Web.Services;

[WebService]
public class Service1 : WebService
{
    [WebMethod]

    public string HelloWorld()
    {
        return "Welcome To ASP.NET Web Service";
    }
}
```

---

# Explanation

### [WebService]

Marks class as Web Service.

---

### [WebMethod]

Marks method accessible through Web Service.

---

# Complete Example

```csharp
using System.Web.Services;

[WebService]

public class StudentService : WebService
{
    [WebMethod]

    public string GetStudentName()
    {
        return "Rohan";
    }

    [WebMethod]

    public int AddNumbers(int a,int b)
    {
        return a + b;
    }
}
```

---

# Accessing Service

URL:

```text
http://localhost/StudentService.asmx
```

Browser shows:

```text
GetStudentName()
AddNumbers()
```

---

# Calling Web Method

Input:

```text
AddNumbers(10,20)
```

Output:

```text
30
```

---

# Web Service Execution Flow

```text
Client
   │
HTTP Request
   ▼
ASMX Web Service
   │
Business Logic
   ▼
Database
   │
SOAP/XML Response
   ▼
Client
```

---

# Web Service vs Website

| Feature           | Website | Web Service  |
| ----------------- | ------- | ------------ |
| Human Interaction | Yes     | No           |
| UI Available      | Yes     | No           |
| Data Exchange     | Limited | Main Purpose |
| Browser Display   | HTML    | XML/SOAP     |
| Used By           | Users   | Applications |

---

# Real-Life Uses of Web Services

### Payment Gateway

```text
PayPal
Razorpay
Stripe
```

---

### Weather Information

```text
Weather Services
```

---

### Maps

```text
Google Maps API
```

---

### SMS Services

```text
OTP Sending
Notifications
```

---

### Banking Systems

```text
Balance Inquiry
Fund Transfer
Account Validation
```

---

# Web Configuration in ASP.NET

## Introduction to Web.Config File, Common Configuration Sections, and AppSettings Section (In-Depth Explanation)

---

# Introduction to Web Configuration

Every ASP.NET application requires some settings and configuration information to run properly.

Examples:

```text
Database Connection String
Authentication Settings
Session Configuration
Error Handling
Application Settings
Caching Settings
```

Instead of writing these values inside code files, ASP.NET stores them in a configuration file called:

```text
Web.config
```

---

# What is Web.Config File?

## Definition

Web.config is an XML-based configuration file used to store application settings and configuration information for an ASP.NET web application.

It controls the behavior of the application without modifying source code.

---

# Key Features of Web.Config

### XML-Based File

Web.config uses XML format.

### Easy Configuration

Settings can be changed without recompiling the application.

### Centralized Management

All configuration settings are stored in one place.

### Security

Sensitive information can be protected.

### Hierarchical Configuration

Settings can be inherited from parent configuration files.

---

# Location of Web.Config

Usually located in the root folder of the ASP.NET application.

Example:

```text
MyWebsite
│
├── Default.aspx
├── About.aspx
├── Web.config
├── Bin
├── App_Data
└── Images
```

---

# Basic Structure of Web.Config

```xml
<?xml version="1.0"?>

<configuration>

</configuration>
```

All configuration settings are written inside:

```xml
<configuration>
</configuration>
```

---

# Example Web.Config

```xml
<?xml version="1.0"?>

<configuration>

    <appSettings>

    </appSettings>

    <connectionStrings>

    </connectionStrings>

    <system.web>

    </system.web>

</configuration>
```

---

# Purpose of Web.Config

Used to manage:

```text
Application Settings
Database Connections
Authentication
Authorization
Session State
Error Handling
Caching
Custom Configuration
```

---

# How ASP.NET Uses Web.Config

Application Start
↓
Read Web.config
↓
Load Configuration
↓
Apply Settings
↓
Run Application

---

# Advantages of Web.Config

### No Code Changes Required

Settings can be modified without editing code.

### Easy Maintenance

All settings are available in one file.

### Environment Configuration

Different configurations for:

```text
Development
Testing
Production
```

### Better Security

Sensitive settings can be encrypted.

---

# Common Configuration Sections

Web.config contains various sections.

Some of the most important sections are:

```text
appSettings
connectionStrings
system.web
authentication
authorization
sessionState
customErrors
compilation
```

---

# Web.Config Overview

```xml
<configuration>

    <appSettings>

    </appSettings>

    <connectionStrings>

    </connectionStrings>

    <system.web>

    </system.web>

</configuration>
```

---

# 1. AppSettings Section

## Purpose

Stores simple application-wide settings as key-value pairs.

---

## Syntax

```xml
<appSettings>

    <add key="KeyName"
         value="Value" />

</appSettings>
```

---

## Example

```xml
<appSettings>

    <add key="CompanyName"
         value="Lakshay Institute" />

    <add key="City"
         value="Rajkot" />

</appSettings>
```

---

# Reading AppSettings Values

## C# Code

```csharp
using System.Configuration;

string company =
ConfigurationManager.AppSettings["CompanyName"];

Response.Write(company);
```

---

## Output

```text
Lakshay Institute
```

---

# Multiple AppSettings Example

## Web.Config

```xml
<appSettings>

    <add key="WebsiteName"
         value="Student Portal" />

    <add key="Version"
         value="1.0" />

    <add key="AdminEmail"
         value="admin@gmail.com" />

</appSettings>
```

---

## ASP.NET Code

```csharp
string site =
ConfigurationManager.AppSettings["WebsiteName"];

string version =
ConfigurationManager.AppSettings["Version"];

string email =
ConfigurationManager.AppSettings["AdminEmail"];

Response.Write(site);
Response.Write("<br>");

Response.Write(version);
Response.Write("<br>");

Response.Write(email);
```

---

## Output

```text
Student Portal
1.0
admin@gmail.com
```

---

# 2. ConnectionStrings Section

## Purpose

Stores database connection strings.

---

## Syntax

```xml
<connectionStrings>

    <add
      name="MyConnection"
      connectionString="..."
      providerName="..." />

</connectionStrings>
```

---

## Example

```xml
<connectionStrings>

    <add
      name="StudentDB"

      connectionString=
      "Data Source=SERVER;
       Initial Catalog=CollegeDB;
       Integrated Security=True"

      providerName=
      "System.Data.SqlClient"/>

</connectionStrings>
```

---

# Reading Connection String

```csharp
using System.Configuration;

string conStr =
ConfigurationManager
.ConnectionStrings["StudentDB"]
.ConnectionString;
```

---

# 3. System.Web Section

## Purpose

Contains ASP.NET-specific settings.

Example:

```xml
<system.web>

</system.web>
```

---

# Common Settings Inside System.Web

```text
Authentication
Authorization
Session State
Compilation
Custom Errors
Caching
```

---

# Example

```xml
<system.web>

    <compilation debug="true" />

</system.web>
```

---

# Compilation Section

## Purpose

Controls application compilation behavior.

---

## Example

```xml
<compilation debug="true" />
```

---

# Meaning

```text
true  → Debug Mode ON
false → Debug Mode OFF
```

---

# Production Recommendation

```xml
<compilation debug="false" />
```

Improves performance.

---

# Authentication Section

## Purpose

Controls user login authentication.

---

## Example

```xml
<authentication mode="Forms" />
```

---

# Authentication Modes

| Mode    | Description            |
| ------- | ---------------------- |
| Windows | Windows Authentication |
| Forms   | Custom Login Form      |
| None    | No Authentication      |

---

# Authorization Section

## Purpose

Controls access permissions.

---

## Example

```xml
<authorization>

    <deny users="?" />

</authorization>
```

---

# Meaning

```text
? = Anonymous Users
```

Anonymous users are denied access.

---

# SessionState Section

## Purpose

Configures session management.

---

## Example

```xml
<sessionState
    timeout="20" />
```

---

# Meaning

```text
Session expires after 20 minutes.
```

---

# CustomErrors Section

## Purpose

Displays user-friendly error pages.

---

## Example

```xml
<customErrors mode="On">

    <error
      statusCode="404"
      redirect="NotFound.aspx" />

</customErrors>
```

---

# Behavior

Instead of:

```text
Technical Error Message
```

User sees:

```text
Friendly Error Page
```

---

# Complete Web.Config Example

```xml
<?xml version="1.0"?>

<configuration>

  <appSettings>

    <add key="CompanyName"
         value="Lakshay Institute"/>

    <add key="City"
         value="Rajkot"/>

  </appSettings>

  <connectionStrings>

    <add
      name="StudentDB"

      connectionString=
      "Data Source=SERVER;
       Initial Catalog=CollegeDB;
       Integrated Security=True"

      providerName=
      "System.Data.SqlClient"/>

  </connectionStrings>

  <system.web>

    <compilation debug="true"/>

    <authentication mode="Forms"/>

    <sessionState timeout="20"/>

  </system.web>

</configuration>
```

---

# Web.Config Hierarchy

ASP.NET supports multiple configuration files.

```text
Machine.config
       ↓
Root Web.config
       ↓
Application Web.config
       ↓
Folder Web.config
```

Child configuration overrides parent settings.

---

# Real-Life Example

Student Management System

Store:

```text
Website Name
Admin Email
Database Connection
Session Timeout
Authentication Rules
```

inside Web.config.

Code remains clean and maintainable.

---

# Best Practices

### Store Configuration in Web.Config

Avoid hardcoding values.

---

### Use ConnectionStrings Section

Store all database connections separately.

---

### Disable Debug Mode in Production

```xml
<compilation debug="false"/>
```

---

### Protect Sensitive Information

Encrypt:

```text
Passwords
Connection Strings
API Keys
```

---

### Use AppSettings for Simple Values

Examples:

```text
Company Name
Website Name
Support Email
Application Version
```

---

# Diagnostics and Debugging in ASP.NET

# Tracing in ASP.NET and Custom Error Handling (Complete In-Depth Guide)

---

# Introduction to Diagnostics and Debugging

While developing an ASP.NET application, errors and bugs are common.

Examples:

```text
Database Connection Error
Null Reference Error
Logic Error
Runtime Error
Syntax Error
```

To identify and solve these problems, ASP.NET provides:

```text
1. Tracing
2. Debugging
3. Custom Error Handling
4. Logging
```

These tools help developers monitor, analyze, and troubleshoot applications.

---

# What is Diagnostics?

## Definition

Diagnostics is the process of identifying, analyzing, monitoring, and resolving problems in an application.

---

# Purpose of Diagnostics

Diagnostics helps developers:

```text
Find Errors
Track Requests
Monitor Performance
Debug Applications
Identify Bottlenecks
```

---

# What is Debugging?

## Definition

Debugging is the process of finding and fixing errors (bugs) in an application.

---

# Types of Errors

### Compile-Time Errors

Errors found during compilation.

Example:

```csharp
int x = "Hello";
```

Compiler Error:

```text
Cannot convert string to int.
```

---

### Runtime Errors

Errors occurring while application runs.

Example:

```csharp
string name = null;

Response.Write(name.Length);
```

Error:

```text
NullReferenceException
```

---

### Logical Errors

Application runs but gives wrong results.

Example:

```csharp
int result = 10 - 5;
```

Expected:

```text
15
```

Actual:

```text
5
```

---

# Diagnostics Tools in ASP.NET

ASP.NET provides:

```text
Tracing
Debugging
Custom Errors
Event Logging
Performance Monitoring
```

---

# Tracing in ASP.NET

---

# What is Tracing?

## Definition

Tracing is a technique used to monitor the execution of an ASP.NET application and collect diagnostic information.

It helps developers understand:

```text
Page Execution Flow
Request Details
Control Processing
Session Information
Application Information
Performance Data
```

---

# Why Tracing?

Without Tracing:

```text
Error Occurred
      ↓
Cause Unknown
```

With Tracing:

```text
Error Occurred
      ↓
Execution Details Available
      ↓
Easy Troubleshooting
```

---

# Benefits of Tracing

### Monitor Execution Flow

Track which code executes.

### Debug Faster

Identify problem areas quickly.

### Performance Analysis

Measure execution time.

### Request Tracking

View client request information.

---

# Types of Tracing

ASP.NET supports:

```text
Page-Level Tracing
Application-Level Tracing
```

---

# Page-Level Tracing

Displays trace information for a specific page.

---

# Enabling Page Trace

Add:

```aspx
<%@ Page Trace="true" %>
```

---

# Example

```aspx
<%@ Page Language="C#"
Trace="true" %>
```

---

# Code Behind

```csharp
protected void Page_Load(
object sender,
EventArgs e)
{
    Trace.Write(
    "Page_Load",
    "Page Loaded Successfully");
}
```

---

# Output

Page displays normal content plus:

```text
Trace Information
---------------------------------
Page_Load
Page Loaded Successfully
```

at the bottom.

---

# Trace.Write()

Used to write trace messages.

Syntax:

```csharp
Trace.Write(
"Category",
"Message");
```

---

# Example

```csharp
Trace.Write(
"Database",
"Connection Established");
```

---

# Trace.Warn()

Used to write warning messages.

Syntax:

```csharp
Trace.Warn(
"Category",
"Warning Message");
```

---

# Example

```csharp
Trace.Warn(
"Login",
"Password Field Empty");
```

---

# Difference Between Write and Warn

| Method        | Purpose             |
| ------------- | ------------------- |
| Trace.Write() | Normal Information  |
| Trace.Warn()  | Warning Information |

---

# Application-Level Tracing

Tracks all pages in the application.

---

# Enable in Web.Config

```xml
<configuration>

 <system.web>

  <trace
   enabled="true"
   pageOutput="false"/>

 </system.web>

</configuration>
```

---

# Meaning

```text
enabled="true"
```

Tracing enabled.

---

```text
pageOutput="false"
```

Trace not shown on pages.

---

# Access Trace Information

URL:

```text
trace.axd
```

Example:

```text
http://localhost/MyApp/trace.axd
```

---

# Trace.axd

Displays:

```text
Recent Requests
Execution Time
Control Tree
Session Data
Request Details
```

---

# Information Available in Trace

### Request Information

```text
URL
Request Type
IP Address
```

---

### Session Information

```text
Session Variables
Session ID
```

---

### Application State

```text
Application Variables
```

---

### Cookies Collection

```text
Stored Cookies
```

---

### Headers Collection

```text
HTTP Headers
```

---

### Server Variables

```text
Browser Information
Server Name
```

---

# Tracing Example

```csharp
protected void Button1_Click(
object sender,
EventArgs e)
{
    Trace.Write(
    "Button",
    "Submit Button Clicked");

    Trace.Write(
    "Database",
    "Fetching Student Records");
}
```

---

# Trace Output

```text
Button
Submit Button Clicked

Database
Fetching Student Records
```

---

# Advantages of Tracing

### Detailed Execution Information

Tracks complete request lifecycle.

### Performance Monitoring

Identifies slow operations.

### Easier Debugging

Find issues quickly.

### Built-in Support

No additional tools needed.

---

# Limitations of Tracing

### Security Risk

Sensitive information may be exposed.

### Performance Overhead

Extra processing required.

### Should Be Disabled in Production

Avoid exposing internal details.

---

# Custom Error Handling

---

# What is Error Handling?

Error Handling is the process of managing application errors gracefully.

Instead of showing technical errors:

```text
NullReferenceException
Stack Trace
Line Number
```

Users see:

```text
Friendly Error Message
```

---

# Why Custom Errors?

Without Custom Errors:

```text
System.NullReferenceException

at Student.aspx.cs line 45
```

Users become confused.

---

# With Custom Errors

```text
Oops!
Something went wrong.

Please try again later.
```

Much better user experience.

---

# ASP.NET Error Handling Methods

```text
Try-Catch
Global Error Handling
Custom Errors
Application_Error
```

---

# Custom Errors in ASP.NET

Custom Errors display friendly pages instead of technical exception details.

---

# CustomErrors Section

Configured in:

```xml
Web.config
```

---

# Syntax

```xml
<customErrors
 mode="On" />
```

---

# Modes of Custom Errors

| Mode       | Description                                     |
| ---------- | ----------------------------------------------- |
| On         | Always Show Custom Error Page                   |
| Off        | Show Detailed Errors                            |
| RemoteOnly | Detailed Errors Locally, Custom Errors Remotely |

---

# Mode = On

```xml
<customErrors mode="On"/>
```

All users see custom error page.

---

# Mode = Off

```xml
<customErrors mode="Off"/>
```

Detailed ASP.NET errors shown.

---

# Mode = RemoteOnly

```xml
<customErrors mode="RemoteOnly"/>
```

Behavior:

```text
Developer Machine
    ↓
Detailed Error

Remote User
    ↓
Custom Error Page
```

---

# Default Redirect Page

```xml
<customErrors
 mode="On"
 defaultRedirect="Error.aspx"/>
```

---

# Example

```xml
<configuration>

 <system.web>

  <customErrors
   mode="On"
   defaultRedirect="Error.aspx"/>

 </system.web>

</configuration>
```

---

# Error.aspx

```aspx
<h2>
Sorry!
Something went wrong.
</h2>
```

---

# Result

Instead of:

```text
Runtime Error
```

User sees:

```text
Sorry!
Something went wrong.
```

---

# Handling Specific Errors

ASP.NET allows different pages for different error codes.

---

# Example

```xml
<customErrors
 mode="On"
 defaultRedirect="Error.aspx">

 <error
  statusCode="404"
  redirect="PageNotFound.aspx"/>

 <error
  statusCode="500"
  redirect="ServerError.aspx"/>

</customErrors>
```

---

# Behavior

404 Error:

```text
PageNotFound.aspx
```

---

500 Error:

```text
ServerError.aspx
```

---

Other Errors:

```text
Error.aspx
```

---

# 404 Error Example

User enters:

```text
Student.aspx
```

Page does not exist.

Redirect:

```text
PageNotFound.aspx
```

Message:

```text
Page Not Found
```

---

# Global Error Handling

Using:

```csharp
Global.asax
```

---

# Application_Error()

```csharp
protected void Application_Error(
object sender,
EventArgs e)
{
    Exception ex =
    Server.GetLastError();

    Response.Redirect(
    "Error.aspx");
}
```

---

# Flow

```text
Exception Occurs
      ↓
Application_Error()
      ↓
Error Logged
      ↓
Redirect User
```

---

# Try-Catch Error Handling

Example:

```csharp
try
{
    int x = 10;
    int y = 0;

    int z = x / y;
}
catch(Exception ex)
{
    Response.Write(
    "Error Occurred");
}
```

---

# Best Practices

### Use Custom Errors in Production

```xml
mode="On"
```

---

### Use RemoteOnly During Testing

```xml
mode="RemoteOnly"
```

---

### Log Errors

Store errors in:

```text
Database
File
Event Viewer
```

---

### Disable Tracing in Production

```xml
<trace enabled="false"/>
```

---

### Avoid Showing Technical Errors

Protect internal information.

---

# Tracing vs Debugging

| Feature                | Tracing           | Debugging   |
| ---------------------- | ----------------- | ----------- |
| Purpose                | Monitor Execution | Fix Bugs    |
| Output                 | Trace Information | Breakpoints |
| Runtime Analysis       | Yes               | Yes         |
| User Visible           | Can Be            | No          |
| Performance Monitoring | Yes               | Limited     |

---

# Tracing vs Custom Errors

| Feature                 | Tracing          | Custom Errors        |
| ----------------------- | ---------------- | -------------------- |
| Used By                 | Developers       | End Users            |
| Purpose                 | Diagnostics      | User-Friendly Errors |
| Shows Technical Details | Yes              | No                   |
| Production Use          | Usually Disabled | Enabled              |

---

# Real-Life Example

Student Management System

Tracing:

```text
Login Started
Database Connected
Student Retrieved
Response Generated
```

Used by developer.

---

Custom Errors:

```text
Sorry!
The requested page is unavailable.
```

Shown to user.

---

# Security in ASP.NET

# Authentication and Authorization (Complete In-Depth Guide)

---

# Introduction to Security in ASP.NET

Security is one of the most important aspects of any web application.

Consider websites like:

```text
Facebook
Instagram
Amazon
Net Banking
College Management System
```

These applications store sensitive information such as:

```text
User Accounts
Passwords
Personal Details
Financial Information
Academic Records
```

Without proper security:

```text
Unauthorized Access
Data Theft
Identity Fraud
System Hacking
```

can occur.

ASP.NET provides built-in security mechanisms to protect applications.

---

# What is Security?

## Definition

Security is the process of protecting an application, its resources, and its data from unauthorized access, modification, or destruction.

---

# Main Goals of Security

ASP.NET security focuses on:

```text
Authentication
Authorization
Confidentiality
Integrity
Availability
```

---

# Security Process Overview

```text
User Requests Resource
         │
         ▼
Authentication
(Who Are You?)
         │
         ▼
Authorization
(What Can You Access?)
         │
         ▼
Access Granted / Denied
```

---

# Authentication

---

# What is Authentication?

## Definition

Authentication is the process of verifying the identity of a user.

It answers the question:

```text
Who are you?
```

---

# Example

Suppose a user wants to access:

```text
Student Portal
```

The system asks:

```text
Username
Password
```

User enters:

```text
Username: rohan
Password: 12345
```

System verifies credentials.

If correct:

```text
User Authenticated
```

If incorrect:

```text
Access Denied
```

---

# Real-Life Example

ATM Machine

```text
Insert Card
      ↓
Enter PIN
      ↓
Verify Identity
      ↓
Access Account
```

PIN verification is Authentication.

---

# Authentication Process

```text
User
  │
Enter Credentials
  │
  ▼
Authentication System
  │
Verify User
  │
  ▼
Valid / Invalid
```

---

# Authentication in ASP.NET

ASP.NET supports multiple authentication methods.

---

# Types of Authentication

```text
Windows Authentication
Forms Authentication
Passport Authentication (Legacy)
Anonymous Authentication
```

---

# Windows Authentication

---

# Definition

Uses Windows user accounts to authenticate users.

Users log in using their Windows credentials.

---

# Working

```text
User Logged into Windows
        ↓
ASP.NET Uses Windows Identity
        ↓
User Authenticated
```

---

# Configuration

```xml
<authentication mode="Windows" />
```

---

# Example Usage

Commonly used in:

```text
Intranet Applications
Office Networks
Corporate Applications
```

---

# Advantages

### No Separate Login Required

Uses existing Windows credentials.

### Secure

Integrated with Windows security.

### Easy Administration

Managed through Active Directory.

---

# Disadvantages

### Not Suitable for Internet Applications

Works mainly within organizations.

---

# Forms Authentication

---

# Definition

Forms Authentication uses a custom login page to authenticate users.

Most commonly used authentication method in ASP.NET.

---

# Working

```text
User Opens Website
         │
         ▼
Login Page
         │
Enter Username & Password
         │
         ▼
Validate Credentials
         │
         ▼
Authentication Cookie Created
         │
         ▼
Access Granted
```

---

# Configuration

```xml
<authentication mode="Forms">

 <forms loginUrl="Login.aspx"/>

</authentication>
```

---

# Example

Web.config

```xml
<system.web>

 <authentication mode="Forms">

  <forms loginUrl="Login.aspx"/>

 </authentication>

</system.web>
```

---

# Login Page Example

```aspx
Username:
<asp:TextBox
ID="txtUser"
runat="server" />

Password:
<asp:TextBox
ID="txtPassword"
runat="server"
TextMode="Password" />
```

---

# Login Validation

```csharp
using System.Web.Security;

protected void btnLogin_Click(
object sender,
EventArgs e)
{
    if(txtUser.Text == "admin" &&
       txtPassword.Text == "123")
    {
        FormsAuthentication
        .RedirectFromLoginPage(
        txtUser.Text,
        false);
    }
}
```

---

# What Happens Internally?

ASP.NET creates:

```text
Authentication Cookie
```

Example:

```text
User = admin
```

Stored in browser.

Future requests use this cookie.

---

# Advantages

### User-Friendly

Custom login page.

### Suitable for Internet Applications

Widely used.

### Flexible

Can connect with:

```text
Database
API
Identity Providers
```

---

# Disadvantages

### Developer Must Manage Login Logic

More implementation effort.

---

# Passport Authentication (Legacy)

---

# Definition

Authentication using a centralized Microsoft account service.

---

# Note

Passport Authentication is now obsolete and replaced by modern identity providers.

Examples today:

```text
Google Login
Microsoft Login
Facebook Login
```

---

# Anonymous Authentication

---

# Definition

Allows users to access resources without logging in.

---

# Example

Public pages:

```text
Home Page
About Us
Contact Us
FAQ
```

No login required.

---

# Configuration

```xml
<authentication mode="None" />
```

---

# Authentication Comparison

| Authentication Type | Login Required    | Best For       |
| ------------------- | ----------------- | -------------- |
| Windows             | No Separate Login | Intranet       |
| Forms               | Yes               | Websites       |
| Passport            | Yes               | Legacy Systems |
| Anonymous           | No                | Public Pages   |

---

# Authorization

---

# What is Authorization?

## Definition

Authorization is the process of determining what resources an authenticated user is allowed to access.

It answers:

```text
What are you allowed to do?
```

---

# Important Difference

Authentication:

```text
Who are you?
```

Authorization:

```text
What can you access?
```

---

# Example

After login:

```text
Admin User
```

may access:

```text
Add Student
Delete Student
Update Student
```

---

Regular User:

```text
View Student
Search Student
```

Only.

---

# Authorization Process

```text
User Login
     │
Authentication
     │
     ▼
Authorized?
     │
 ┌───┴───┐
 │       │
Yes      No
 │        │
 ▼        ▼
Access  Denied
Granted
```

---

# Authorization Types

ASP.NET supports:

```text
URL Authorization
File Authorization
Role-Based Authorization
```

---

# URL Authorization

Controls access to specific pages or folders.

---

# Example

```xml
<authorization>

 <deny users="?" />

</authorization>
```

---

# Meaning

```text
? = Anonymous Users
```

Anonymous users cannot access the page.

---

# Authorization Example

```xml
<authorization>

 <allow users="admin" />

 <deny users="*" />

</authorization>
```

---

# Meaning

```text
Only admin can access.
All others denied.
```

---

# Symbols Used

| Symbol | Meaning         |
| ------ | --------------- |
| ?      | Anonymous Users |
| \*     | All Users       |

---

# Example

```xml
<authorization>

 <deny users="?" />

</authorization>
```

Authenticated users only.

---

# Role-Based Authorization

---

# Definition

Access is granted based on user roles.

---

# Example Roles

```text
Admin
Teacher
Student
Manager
Employee
```

---

# Authorization Logic

```text
Admin
  ↓
Can Add/Delete Records

Teacher
  ↓
Can Update Records

Student
  ↓
Can View Records
```

---

# Configuration Example

```xml
<authorization>

 <allow roles="Admin" />

 <deny users="*" />

</authorization>
```

---

# Meaning

Only Admin role can access.

---

# Folder-Level Authorization

Example:

```text
Admin Folder
```

Web.config inside folder:

```xml
<authorization>

 <allow roles="Admin"/>

 <deny users="*" />

</authorization>
```

Only admins can open pages inside that folder.

---

# Programmatic Authorization

Check authorization in code.

---

# Example

```csharp
if(User.Identity.IsAuthenticated)
{
    Response.Write(
    "User Logged In");
}
```

---

# Check Role

```csharp
if(User.IsInRole("Admin"))
{
    Response.Write(
    "Welcome Admin");
}
```

---

# Authentication vs Authorization

| Feature                        | Authentication  | Authorization      |
| ------------------------------ | --------------- | ------------------ |
| Purpose                        | Verify Identity | Verify Permissions |
| Question                       | Who are you?    | What can you do?   |
| Occurs First?                  | Yes             | No                 |
| Required Before Authorization? | Yes             | Yes                |
| Example                        | Login           | Access Control     |

---

# Real-Life Example

Bank ATM

Step 1:

```text
Insert Card
Enter PIN
```

Authentication

---

Step 2:

```text
Withdraw Money
Check Balance
Transfer Funds
```

Authorization

---

# ASP.NET Security Flow

```text
User Requests Page
         │
         ▼
Authentication
         │
         ▼
Authorization
         │
         ▼
Access Granted
         │
         ▼
Page Displayed
```

---

# Best Practices

### Use Forms Authentication

Most suitable for web applications.

---

### Store Passwords Securely

Use:

```text
Hashing
Encryption
Salt
```

Never store plain-text passwords.

---

### Use Role-Based Authorization

Easier permission management.

---

### Protect Admin Pages

Restrict access to admin roles only.

---

### Use HTTPS

Encrypt communication.

---

### Disable Anonymous Access for Sensitive Data

Protect private resources.

---

# Deployment of ASP.NET Application in Web Server

# Complete In-Depth Guide

---

# Introduction to Deployment

After developing and testing an ASP.NET application on a local computer, the next step is to make it available to users.

This process is called:

```text
Deployment
```

---

# What is Deployment?

## Definition

Deployment is the process of publishing an ASP.NET application from the development environment to a web server so that users can access it through a web browser.

---

# Simple Definition

```text
Development Computer
         ↓
Publish Website
         ↓
Web Server
         ↓
Users Access Website
```

---

# Real-Life Example

Suppose you develop:

```text
Student Management System
```

on your computer.

Initially:

```text
Only You Can Access It
```

After deployment:

```text
Students
Teachers
Administrators
```

can access it through:

```text
https://www.studentportal.com
```

---

# Why Deployment is Required?

Without deployment:

```text
Application runs only on local machine.
```

After deployment:

```text
Application becomes accessible worldwide.
```

---

# Benefits of Deployment

### Public Access

Users can access the application online.

### Centralized Data

Data stored on server.

### Better Security

Server security can be configured.

### Scalability

Supports many users.

### Easy Maintenance

Updates are managed centrally.

---

# Deployment Architecture

```text
Developer
     │
Build ASP.NET Application
     │
     ▼
Publish Application
     │
     ▼
Web Server (IIS)
     │
     ▼
Internet
     │
     ▼
Users
```

---

# What is a Web Server?

## Definition

A Web Server is software that receives requests from clients and sends web pages or web application responses.

---

# Popular Web Servers

| Web Server | Platform          |
| ---------- | ----------------- |
| IIS        | Microsoft         |
| Apache     | Open Source       |
| Nginx      | Open Source       |
| Tomcat     | Java Applications |

---

# ASP.NET Preferred Web Server

```text
IIS
(Internet Information Services)
```

---

# What is IIS?

IIS stands for:

```text
Internet Information Services
```

It is Microsoft's web server used to host:

```text
ASP.NET
ASP.NET MVC
ASP.NET Core
Web APIs
Web Services
```

---

# IIS Features

### High Performance

Handles multiple requests efficiently.

### Security

Supports authentication and authorization.

### SSL Support

HTTPS configuration available.

### Application Pools

Process isolation.

### Logging

Request and error tracking.

---

# Deployment Prerequisites

Before deployment ensure:

```text
Application Tested
Database Ready
IIS Installed
.NET Framework Installed
Required Permissions Available
```

---

# Deployment Methods

ASP.NET applications can be deployed using:

```text
1. Copy Deployment
2. Publish Deployment
3. Web Deploy
4. FTP Deployment
5. Cloud Deployment
```

---

# Method 1: Copy Deployment

## Definition

Copying application files directly to the web server.

---

# Process

```text
Local Website
      ↓
Copy Files
      ↓
Server Folder
      ↓
Run Website
```

---

# Required Files

```text
.aspx Files
.dll Files
Images
CSS
JavaScript
Web.config
```

---

# Advantages

### Simple

Easy deployment.

### Fast

No special tools required.

---

# Disadvantages

### Manual Process

Every update requires file copying.

---

# Method 2: Publish Deployment

Most commonly used.

---

# Process

```text
Visual Studio
      ↓
Publish
      ↓
Generate Deployment Files
      ↓
Upload to Server
```

---

# Steps in Visual Studio

## Step 1

Right Click Project

```text
Publish
```

---

## Step 2

Choose Target

```text
Folder
IIS
FTP
Azure
```

---

## Step 3

Publish

Visual Studio creates deployment files.

---

# Publish Output Example

```text
bin
Default.aspx
About.aspx
Web.config
Images
Scripts
```

---

# Method 3: Web Deploy

Microsoft deployment technology.

---

# Benefits

### Automated Deployment

### Incremental Updates

### Secure Publishing

### IIS Integration

---

# Method 4: FTP Deployment

Files uploaded using FTP software.

Examples:

```text
FileZilla
WinSCP
```

---

# Process

```text
Publish Website
      ↓
FTP Upload
      ↓
Web Server
```

---

# Method 5: Cloud Deployment

Deploy directly to cloud services.

Examples:

```text
Microsoft Azure
AWS
Google Cloud
```

---

# ASP.NET Deployment Using IIS

---

# Step 1: Install IIS

Open:

```text
Control Panel
```

↓

```text
Programs
```

↓

```text
Turn Windows Features On or Off
```

Enable:

```text
Internet Information Services
```

---

# IIS Structure

```text
IIS
 │
 ├── Sites
 ├── Application Pools
 ├── Virtual Directories
 └── Server Settings
```

---

# Step 2: Open IIS Manager

Run:

```text
inetmgr
```

or

```text
Internet Information Services (IIS) Manager
```

---

# Step 3: Create Website Folder

Example:

```text
C:\Websites\StudentPortal
```

Copy published files here.

---

# Step 4: Create New Website

In IIS:

```text
Sites
   ↓
Add Website
```

---

# Website Settings

---

# Site Name

```text
StudentPortal
```

---

# Physical Path

```text
C:\Websites\StudentPortal
```

---

# Port Number

```text
80
```

Default HTTP port.

---

# Host Name

Optional:

```text
www.studentportal.com
```

---

# Step 5: Configure Application Pool

---

# What is Application Pool?

Application Pool isolates applications from each other.

---

# Benefits

### Fault Isolation

One application crash won't affect others.

### Security

Separate process execution.

### Better Performance

Resource management.

---

# Configure .NET Version

Example:

```text
.NET Framework 4.x
```

---

# Step 6: Start Website

Click:

```text
Start
```

Website becomes active.

---

# Access Website

Example:

```text
http://localhost
```

or

```text
http://localhost:80
```

---

# Deployment of Database

Applications often require databases.

---

# SQL Server Deployment

Steps:

```text
Create Database
Create Tables
Insert Initial Data
Configure Permissions
```

---

# Update Connection String

Web.config:

```xml
<connectionStrings>

 <add
  name="StudentDB"

  connectionString=
  "Data Source=SERVERNAME;
   Initial Catalog=StudentDB;
   Integrated Security=True"

  providerName=
  "System.Data.SqlClient"/>

</connectionStrings>
```

---

# Web.Config During Deployment

Important settings:

```xml
<compilation debug="false"/>
```

---

# Why Disable Debug?

### Better Performance

### Increased Security

### Reduced Resource Usage

---

# Configure Custom Errors

```xml
<customErrors
 mode="On"
 defaultRedirect="Error.aspx"/>
```

---

# Configure Session Timeout

```xml
<sessionState
 timeout="20"/>
```

---

# Deployment Checklist

Before deployment verify:

```text
✓ All Pages Working

✓ Database Connected

✓ Connection Strings Updated

✓ Debug Mode Disabled

✓ Custom Errors Enabled

✓ IIS Installed

✓ Required DLL Files Present

✓ Application Pool Configured

✓ Security Settings Applied
```

---

# Common Deployment Issues

---

# Missing DLL Files

Error:

```text
Could not load assembly
```

Solution:

```text
Copy required DLLs into Bin folder.
```

---

# Database Connection Error

Error:

```text
Login Failed
```

Solution:

```text
Verify Connection String
Check SQL Permissions
```

---

# IIS Configuration Error

Error:

```text
HTTP Error 500
```

Solution:

```text
Check IIS Settings
Restart IIS
```

---

# Permission Error

Error:

```text
Access Denied
```

Solution:

```text
Grant Folder Permissions
```

---

# Port Conflict

Error:

```text
Website Not Starting
```

Solution:

```text
Use Different Port
```

---

# Deployment Flow Diagram

```text
ASP.NET Application
          │
          ▼
Build Project
          │
          ▼
Publish Project
          │
          ▼
Copy To IIS Server
          │
          ▼
Configure Website
          │
          ▼
Configure Database
          │
          ▼
Start Website
          │
          ▼
Users Access Application
```

---

# Real-Life Example

Student Management System

Development:

```text
Visual Studio
```

↓

Publish:

```text
StudentPortal Folder
```

↓

Copy To:

```text
C:\Websites\StudentPortal
```

↓

Create IIS Site

↓

Configure Database

↓

Access:

```text
http://localhost/StudentPortal
```

or

```text
https://www.studentportal.com
```

---
