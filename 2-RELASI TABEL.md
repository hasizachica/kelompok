# Tabel 1 (Customers)
![hasil](tabel/prk1.png)
# Tabel 2 (Employees)
![hasil](tabel/prk2.png)

# Tabel 3 (Products)
![hasil](tabel/prk3.png)

# Tabel 4 (Orders)
![hasil](tabel/prk4.png)

# Tabel 5 (OrderDetails)
![hasil](tabel/prk5.png)

# Query 1
## Contoh Query
```sql
SELECT orders.OrderID, orders.OrderDate, orders.CustID,
    -> customers.CompanyName, customers.ContactName, customers.City,
    -> customers.Phone
    -> FROM orders, customers
    -> WHERE orders.CustID = customers.CustomerID;
```
## Hasil
![hasil](tabel/q1.png)

## Penjelasan

- `SELECT`= untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `orders, OrderID` = orders merupakan nama tabel yang ingin ditampilkan kolomn yaitu orderID, Jadi kolom orderID Pada dalam tabel orders indin ditampilkan.
- `orders. Order Date` = kolom orderDate pada dalam tabel orders ingin ditampilkan.
- `orders.custID` = kolom custID dalam tabel orders dipilih untuk ditampilkan.
- `Customers. companyName` = kolom companyName dalam tabel customers dipilih untuk ditampilkan.
- `customers.contactName` = kolom contactName dalam tabel customers dipilih untuk ditampilkan.
- `customers. city` = kolom city dalam tabel customers dipilih untuk ditampilkan.
- `Customers. Phone` = kolom Phone dalam tabel customers dipilih untuk ditampilkan.
- `FROM orders, customers` = untuk memilih dari tabel mana saja yang kolomnya ingin dipilih untuk ditampilkan. Orders adalah nama tabel Pertama yang dipilih dan customers adalah nama tabel kedua Yang dipilih.
- `WHERE` = Kondisi Yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan.
- `(orders.custID` = customers. customerID)= kondisi dari WHERE Yang harus dipenuhi. Jadi, data pada kolom custID dalam tabel orders harus sama dengan data Pada kolom customerID dalam tabel customers agar masing-masing datanya bisa ditampilkan.

## Hasilnya 

Jadi Yang tampil adalah kolom OrderID, orderDate dan custID dari tabel, orders dan kolom companyName, contactName, city, dan Phane dari tabel customers.


# Query 2
## Contoh Query
```SQL
SELECT o.OrderID, o.OrderDate, o.CustID,
    -> c.CompanyName, c.ContactName, c.City,
    -> c.Phone
    -> FROM orders o,customers c
    -> WHERE o.CustID = c.CustomerID AND c.City = "London";
```
## Hasil
![hasil](tabel/q2.png)

## Penjelasan

- `SELECT` = untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `o. orderID` = o merupakan Singkatan dari tabel orders, kolam orderID merupakan kolom dari tabel orders yang dipilih untuk ditampilkan.
- `o.orderDate` = kolom orderDate merupakan kolom dari tabel o yaitu orders yang dipilih untuk ditampilkan,
- `o. custID` = kolom custID merupakan kolom dari tabel o yaitu orders yang dipilih untuk ditampilkan
- `C. companyName` = C merupakan singkatan dari tabel customers, kolom companyName merupakan kolom dari tabel customers yang dipilih untuk ditampilkan.
- `C. ContactName` = kolom contactName merupakan kolom dari tabel c yaitu customers yang dipilih untuk ditampilkan.
- `C. city` = kolom city merupakan kolom dari tabel c yaitu customers yang dipilih untuk ditampilkan,
- `C. Phone` = kolom Phone merupakan kolom dari tabel c yaitu customers yang dipilih untuk ditampilkan.
- `From orders o, customers c` = untuk memilih dari tabel mana saja yang kolomnya ingin dipilih untuk ditampilkan. orders adalah nama tabel yang dipilih untuk ditampilkan tapi disingkat Jadi O, agar lebih mudah dan cepat. customers adalah nama tabel yang dipilih untuk ditampilkan tapi disingkat Jadi C.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan. 
- `(O.CustID = costumerID)` = data Pada kolom custID dalam tabel o (orders) harus sama dengan data Pada kolom customerID dalam tabel c (customers).
- `AND` = untuk menyeleksi dua data atau lebih Pada Perintah WHERE.
- `(C.city = • "London")` = kondisi tambahan yang harus dipenuhi juga. Jadi Pada kolom city dari tabel c(customers) datanya harus berisi data "London" agar bisa ditampilkan.

## Hasilnya 

Jadi hanya barisan data yang kolom city dari tabel c(customers) mempunyai data "London" yang bisa tampil.


# Query 3
## Contoh Query
```SQL
SELECT o.OrderID, o.OrderDate, c.CompanyName,
    -> c.ContactName, c.Phone, e.LastName, e.Title
    -> FROM orders o, customers c, employees e
    -> WHERE o.CustID = c.CustomerID AND o.EmpID = e.EmpID;
```
## Hasil
![hasil](tabel/q3.png)
## Penjelasan

- `SELECT` = untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `o.orderID, o. OrderDate` = kolom orderID dan orderDate dari tabel o(orders) dipilih untuk ditampilkan.
- `c.companyName,c.contactName, c. Phone` = kolom-kolom companyName, contactName dan Phone dari tabel c(customers) dipilih untuk ditampilkan. 
- `e LastName, e. Title` = kolom lastName dan Title dari tabel e (employees) dipilih untuk ditampilkan.
- `From orders o, customers c, employees e` = untuk memilih dari tabel mana saja Yang kolomnya dipilih untuk ditampilkan. orders disingkat Jadi o adalah nama tabel Yang dipilih. customers disingkat Jadi c adalah nama tabel yang dipilih employees disingkat Jadi e adalah nama tabel Yang dipilih untuk ditampilkan.
- `WHERE` = kondisi Yang harus dipenuhi oleh suatu data agar bisa ditampilkan.
- `(o.CustID = C. customerID)` = data pada kolom CustID dalam tabel c(customers) harus Sama dengan data Pada kolom customerID dalam tabel c(customers).
- `AND` = untuk menyeleksi dua data atau lebih Pada Perintah WHERE.
- `(o. emPID = e. EmPID)` = data pada kolom EMPID dalam tabel o(orders) harus Sama dengan data Pada kolom EmpID dalam tabel e(employees).

## Hasilnya

 yang tampil adalah kolom Yang memenuhi semua kondisi dari WHERE.

# Query 4
## Contoh Query
```SQL
SELECT o.OrderID, o.OrderDate, c.CompanyName,
    -> c.ContactName, c.Phone, e.LastName, e.Title
    -> FROM orders o, customers c, employees e
    -> WHERE o.CustID = c.CustomerID AND o.EmpID = e.EmpID AND
    -> e.FirstName = "Margaret";
```
## Hasil
![hasil](tabel/q4.png)
## Penjelasan

- `SELECT` = untuk memilih kolom mana saja Yang ingin ditampilkan dan dari tabel mana, kolom tersebut diambil.
- `o. orderID, o. orderDate` = kolom orderID dan orderDate dari tabel o (orders) dipilih untuk ditampilkan.
- `c.comPanyName, c.contactName, C. Phone` = kolom CompanyName,  ContactName dan Phone dari tabel c (customers) dipilih untuk ditampilkan.
- `e.lastName, e.Title` = kolom LastName dan Title dari tabel e (employees) dipilih untuk ditampilkan.
- `From orders o, customers c, employees e` = untuk memilih dari tabel mana saja Yang kolamnya dipilih untuk ditampilkan. orders atau o adalah nama tabel Yang dipilih untuk ditampilkan. customers atau c adalah nama tabel yang dipilih untuk ditampilkan. employees atau e adalah nama tabel yang dipilih untuk ditampilkan.
- `WHERE` = Kondisi Yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan. 
- `O.empID = e. empID)` = data Pada kolom EmpID dalam tabel o (orders) harus sama dengan data Pada kolom EmpID dalam table e (employees).
- `AND` = untuk menyeleksi dua data atau lebih Pada Perintah WHERE. 
- `(o. EmpId=e.EmPID)` = data Pada kolom EmpID dalam tabel o (orders) harus sama dengan data Pada kolom EmpID dalam tabel e(employees).
- `AND` = untuk menyelersi dua data atau lebih Pada Perintah WHERE.
- `(e. FirstName = "Margaret")` = data Pada kolom FirstName dalam tabel e(employees) harus berisi data "Margaret" agar bisa tampil.

## Hasilnya

Jadi barisan data yang sudah memenuhi kondisi WHERE akan tampil. terutama kolom FirstName dari tabel employees Yang isinya "Margaret".


# Query 5
## Contoh Query
```SQL
SELECT c.CustomerID, c.CompanyName, o.OrderID,
    -> o.OrderDate, od.ProductID, p.ProductName,
    -> od.Quantity AS Qty, od.UnitPrice
    -> FROM customers c, orders o, orderdetails od, products p
    -> WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID
    -> AND p.ProductID = od.ProductID
    -> ORDER BY c.CustomerID;
```
## Hasil
![hasil](tabel/q5.png)
## Penjelasan

- `SELECT`= untuk memilih kolom mana saja, Yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `C.customerID, C. companyName`= kolom customerID dan companyName dari tabel c (customers) dipilih untuk ditampilkan.
- `o. orderID, o. orderDate`= kolom orderID dan orderDate dari tabel o(orders) dipilih untuk ditampilkan.
- `od. ProductID, od. Quantity, od. unitPrice`= kolom ProductID, Quantity dan unitPrice dari tabel od (orderdetails) dipilih untuk ditampilkan.
- `P.ProductName`= kolam ProductName merupakan kolom dari tabel P(Products) yang dipilih untuk ditampilkan.
- `od. Quantity AS Qty`= kolom Quantity ditampilkan sebagai nama sementaranya yaitu qty. AS untuk mengubah nama suatu kolom Secara sementara.
- `FROM customers c. orders o orderdetails od, products p`= untuk memilih dari tabel mana saja yang kolomnya dipilih untuk ditampilkan. customers atar C adalah nama tabel Yang dipilih untuk ditampilkan. orders atau o adalah nama tabel Yang dipilih untuk ditampilkan. orderdetails atau od adalah nama tabel yang dipilih untuk ditampilkan. Products atau P adalah nama tabel Yang dipilih untuk ditampilkan.
- `WHERE`= Kondisi yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan.
- `(c.customerID = o.CustID)`= data Pada kolom customerID dari tabel customers atau c harus sama dengan data Pada kolom CustID dari tabel orders atau o.
- `AND`= untuk menyeleksi dua data atar lebih Poda perintah WHERE.
- `(o. order ID = Od.orderID)`= data Pada kolom orderID dari tabel orders atau o harus sama dengan data Pada kolom OrderId dari tabel orderdetails atau od.
- `AND`= untuk menyeleksi dua data atau lebih Pada Perintah WHERE.
- `(P.ProductID = od. ProductID)`= data Pada kolom ProductID dari tabel Products atau P harus sama dengan data Pada kolom ProductID dati tabel orderndetails atau d.
- `order By c.customerID`= untuk mengurut data berdasarkan kolom customerID dari tabel customers.

## Hasilnya

kolom-kolom data yang tampil adalah data Yang telah memenuhi Kondisi-kondisi Yang ada, dan seluruh isi data tersebut diurut berdasarkan satu kolom yaitu customerID dari tabel customers.

# Query 6
## Contoh Query
```SQL
SELECT c.CustomerID, c.CompanyName, o.OrderID as OrdID,o.OrderDate,
    -> CONCAT(e.LastName,',',e.FirstName) AS EmployeeName, od.ProductID AS ProdID,
    -> P.ProductName, od.Quantity AS Qty
    -> FROM Customers c, Orders o, OrderDetails od, Products p, Employees e
    -> WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID AND p.ProductID = od.ProductID AND e.EmpID = o.EmpID
    -> ORDER BY o.OrderID;
```
## Hasil
![hasil](tabel/q6.png)
## Penjelasan

- `SELECT`= untuk memilih kolom mana saja yang ingin ditampilkan dan digabungkan serta dari tabel mana kolom tersebut dipilih.
- `c. customerID. C. CompanyName`= kolom customerID dan companyName dari tabel c(customers) dipilih untuk ditampilkan.
- `o.OrderID AS ordID, O.orderDate`= kolom orderID dan orderDate dari tabel o(orders) dipilih untuk ditampilkan. As merupakan Perintah untuk mengubah nama Suatu kolom Secara sementara. Dalam hal ini kolom orderID diubah namanya sementara menjadi ordID.
- `CONCAT (e.LastName,',', e.FirstName) AS EmployeeName`= CONCAT adalah Perintah untuk menggabungkan beberapa kolom data menjadi satu kolom data. (e-LastName, e. First Name) merupakan kolom-kolom yang ingin digabund LastName dan First Name merupakan kolom dari tabel e(employees) yang ingin digabung. ('.') merupakan separator atau pemisah dari kedua kolom yang ingin digabungkan. As EmployeeName untuk mengubah hasil concat tadi menjadi Employeenon (namanya) untuk sementara.
- `od. ProductID As ProdID, od. Quantity AS Qty`= kolom productID dan quantity dari tabel od(orderdetails) dipilih untuk ditampilkan, kolom Productio namanya diubah sementara Jadi ProdID. kolom Quantity namanya diubah Sementara Jadi ProdID. kolom quantity namanya diubah sementara jadi qty.
- `P. ProductName`= kolom ProductName dari tabel P(Products) dipilih untuk ditampilkan.
- `From customers c, orders o, orderdetails od, Products P, employees e`= untuk memilih dari tabel mana saja Yang kolomnya dipilih untuk ditampilkan. customers atau c adalah nama tabel Yang dipilih. orders atau o adalah nama tabel Yang dipilih. order details od adalah nama tabel Yang dipilih. Products atau P adalah nama tabel Yang dipilih, employees atau e adalah nama tabel Yand dipilih.
- `WHERE`= kondisi yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan.
- `C.CustomerID = o. CustID)`= data pada kolom customerID dari tabel c(customers) harus sama dengan data Pada kolom custID dari tabel o corders).
- `AND`= untuk menyeleksi dua data atau lebih pada Perintah WHERE.
- `(OrderID = od orderID)`= data pada kolom orderID dari tabel (orders) harus Sama dengan data Pada kolom orderID dari tabel od (orderdetails).
- `AND`= untuk menyeleksi dua data atau lebih Pada Perintah WHERE.
- `(P.ProductID=od. ProductID)`= data pada kolom ProductID dari tabel P(ProductID) harus sama dengan data Pada kolom ProductID dari tabel od (orderdetail).
- `AND`= untuk menyeleksi dua data atau lebih Pada Perintah WHERE.
- `(e. EmPID = o. EmPID)`= data pada kolom EmPID dari tabel e(employees) harus sama dengan data Pada kolom EmPID dari tabel o(orders).
- `order By o. OrderID`= untuk mengurut data berdasarkan kolom orderID dari tobel orders.

## Hasilnya

kolom LastName dan FirstName dari tabel e(employees) digabung dengan Concat dan hasil kolomnya namanya diubah sementara Jadi EmployeeName.
# Query 7
## Contoh Query
```SQL
CREATE VIEW CustOrderEmp
    -> AS
    -> SELECT c.CustomerID, c.CompanyName, c.ContactName,
    -> o.OrderID, o.OrderDate, e.EmpID, e.LastName, e.FirstName
    -> FROM Customers c, Orders o, Employees e
    -> WHERE c.CustomerID = o.CustID AND o.EmpID = e.EmpID;
```
## Hasil
![hasil](tabel/q7.png)
## Penjelasan

- `CREATE VIEW custorder Emp`= merupakan tabel virtual Yang dibuat dengan nama custorderEmp.
- `AS SELECT`= untuk memilih kolom-kolom mana saja yang ingin dipilih untuk dimasukkan ke tabel virtual.
- `C.customerID, C. companyName, c.contactName`= kolom customerID, companyName dan contactName dari tabel c(customers) dipilih untuk dimasukkan ke dalam tabel virtual.
- `o.orderID, o. orderDate`= kolom orderID dan orderDate dari tabel (orders) dipilih untuk dimasukkan ke dalam tabel virtual.
- `e.EmPID, e LastName, e. FirstName`= kolom EmPID, LastName, dan FirstName dari tabel e(employees) dipilih untuk dimasukkan ke dalam tabel virtual.
- `From customers c orders o, employees e`= untuk memilih dari tabel mana saja yang kolomnya dipilih untuk dimasukkan. customers, orders dan employees merupakan nama tabel yang kolomnya dipilih.
- `WHERE`= kondisi yang harus dipenuhi oleh suatu data agar bisa dimasukkan ke dalam tabel virtual.
- `(c.customerID = o custID)`= data Pada kolom customerID dari tabel c(costumes) harus sama dengan data pada kolom custID dari tabel o(order) agar bisa dimasukkan.
- `AND`= untuk menyeleksi dua data atau lebih Pada WHERE.
- `(o. EmPID = e.EmPID)`= data pada kolom EmpID dari tabel o(orders) harus sama dengan data Pada kolom EmPID dari tabel e(employees) agar bisa dimasukkan.

## Hasilnya

sebuah Tabel virtual telah dibuat dengan nama custorderEmp yang berisi kolom-kolom dari 3 Tabel customers, orders, employees dan telah memenuhi semua kondisi.
# Query 8
## Contoh Query
```SQL
CREATE VIEW odproducts
    -> AS
    -> SELECT od.OrderID, od.ProductID, p.ProductName,
    -> od.Quantity, od.UnitPrice
    -> FROM OrderDetails od, Products p
    -> WHERE p.ProductID = od.ProductID;
```
## Hasil
![hasil](tabel/q8.png)

![hasil](tabel/q8_2.png)
## Penjelasan

- `CREATE VIEW od products`= untuk membuat tabel virtual dengan nama odproducts.
- `AS SELECT`= untuk memilih kolom-kolom mana saja yang Yand Ingin dipilih untuk dimasukkan ke tabel virtual.
- `od. orderID, od. ProductID, od unitPrice, od quantity`= kolom orderID, ProductID, unitPrice dan Quantity dari tabel od (orderdetails) dipilih untuk dimasukkan. 
- `P. ProductName`= kolom Productivame dari tabel p(Products) dipilih untuk dimasukkan. 
- `From orderdetails od, Products P`= untuk memilih dari tabel mana saja yang kolomnya dipilih untuk dimasukkan. orderdetails dan Products adalah nama tabel yang dipilih.
- `WHERE`= Kondisi yang harus dipenuhi oleh suatu data agar bisa dimasukkan ke dalam tabel virtual.
- `(P.ProductID = od. ProductID)`= data Pada kolom ProductID dari tabel P(Products) harus sama dengan kolom ProductID dari tabel od (order details). agar bisa dimasukin.

## Hasilnya

Tabel virtual yang bernama od Products Yang terbuat dari kolom dalam 2 Tabel orderdetails dan Products.
# Query 9
## Contoh Query
```SQL
SELECT c.CustomerID, c.CompanyName, o.OrderID, od.ProductID, ROUND(od.UnitPrice,2), od.Quantity,
    -> od.Discount, ROUND(((1-od.Discount)*od.UnitPrice*od.Quantity),2) AS Jumlah
    -> FROM Customers c, Orders o, OrderDetails od WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID
    -> ORDER BY c.CustomerID;
```
## Hasil
![hasil](tabel/q9.png)
## Penjelasan

- `SELECT`= untuk memilih Kolom mana saja Yang ingin ditampilkan dan dihitung.
- `c. customerID, C. companyName`= kolom customerID dan companyName dari tabel c(customers) dipilih untuk ditampilkan.
- `o.orderID`= kolom orderID dari tabel o (orders) dipilih untuk ditampilkan.
- `Od. ProductID, od.unitPrice, od. quantity, od, Discount`= kolom ProductID, unitPrice, Quantity dan Discount dari tabel Od (orderdetails) dipilih untuk ditampilkan dan dibulatkan.
- `ROUND (od. unitprice, 2)`= untuk membulatkan bilangan dari kolom unitPrice Sampai Jumlah digit tertentu sesuai dengan pilihan yang dibuat yaitu 2.
- `ROUND ((1-od. Discount) *od. unitPrice* od. Quantity), 2) AS Jumlah`= untuk membulatkan bilangan dari kolom hasil dari (1 dikurang kolom discount lalu dikali unitprice dan kali quantity) sampai sumlah digit yaitu 2. As Jumlah untuk mengubah kolom hasil tersebut nama sementaranya Jadi Jumlah.
- `From customers c, orders. o, orderdetails od`= untuk memilih dari tabel mana saja yang kolomnya dipilih untuk ditampilkan dan dibulatkan. customers, orders, onderdetails merupakan nama-nama tabel Yang dipilih. 
- `WHERE`= kondisi yang harus dipenuhi oleh suatu data agar bisa ditampilkan.
- `(customerID= o. CustID)`= data pada kolom customerID dari tabel c(customers) harus sama dengan data pada kolom custID dari tabel o(orders).
- `AND`= untuk menyeleksi dua data atau lebih Pada kondisi WHERE. 
- `(o.orderID = od.OrderID)`= data pada kolom orderID dari tabel o(orders) harus Sama dengan data pada kolom OrderID dari tabel od (orderdetails).
- `ORDER BY c.customerID`= untuk mengurut data berdasarkan kolom customers dari tabel c(customers).

## Hasilnya

akan tampil hasil Pembulatan dari kolom-kolom Yang telah memenuhi kondisi dari WHERE.
# Query 10
## Contoh Query
```SQL
SELECT c.customerid, c.companyname, ROUND(SUM((1-od.discount)*od.unitprice*od.quantity),2) AS TotalJumlah
    -> FROM customers c, orders o, orderdetails od WHERE c.customerid=o.custid AND o.orderid=od.orderid
    -> GROUP BY c.customerid, c.companyname order by c.customerid;
```
## Hasil
![hasil](tabel/q10.png)
## Penjelasan

- `SELECT`= untuk memilih kolom mana saja Yang ingin ditampilkan dan dibulatkan.
- `C.CustomerID, C.CompanyName`= kolom customerID dan companyName dari tabel (customers) dipilih untuk ditampilkan.
- `ROUND (Sum((1-od discount) * od. unitPrice *od. quantity), 2) As Total Jumlah`= untuk membulatkan hasil sum dari ((1 dikurang kolom Discount) dikali unitPrice Kali Quantity) Sampai 2 digit. Dan nama kolom hasilnya diubah sementara Jadi TotalJumlah.
- `FROM customers c, orders, orderdetails od`= untuk memilih dari tabel mana Saja Yang kolomnya dipilih untuk ditampilkan dan dibulatkan. customers, Orders dan Orderdetails adalah nama, tabel yang dipilih.
- `WHERE`= kondisi yang harus dipenuhi oleh suatu data agar bisa ditampilkan.
- `(C.customerID=o.custID)`= data Pada kolom customerID dari tabel c(customers) harus sama dengan data Pada kolom CustID dari tabel o (orders).
- `AND`= untuk menyeleksi dua data atau lebih Pada kondisi WHERE.
- `(o.orderID = od orderID)`= data Pada kolom orderID dari tabel o (orders). harus sama dengan data pada kolom orderID dari tabel od(orderdetails). 
- `GROUP BY c.customerID, C. companyName`= untuk mengelompokkan data sesuai dengan kolom customerID dan companyName dari tabel c(customers). 
- `ORDER BY c.customerID`= untuk mengurut data berdasarkan kolom customerID dari tabel c(customers).

## Hasilnya

Jadi, kolom Yang dikelompokkan adalah customerID dan companyName dan tampilan datanya diurutkan berdasarkan kolom customerID.