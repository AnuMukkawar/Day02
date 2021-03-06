# Day02

Q1. Write a blog on Difference between HTTP1.1 vs HTTP2
ans:
HTTP/1.1-
  It supports connection reuse i.e. for every TCP connection there could be multiple requests and responses, and pipelining where the client can request several resources from the server at once. However, pipelining was hard to implement due to issues such as head-of-line blocking and was not a feasible solution.
  
  Introduces a warning header field to carry additional information about the status of a message. Can define 24 status codes, error reporting is quicker and more efficient.
  
  It is relatively secure since it uses digest authentication, NTLM authentication.
  
  Expands on the caching support by using additional headers like cache-control, conditional headers like If-Match and by using entity tags.
  
  HTTP/1.1 provides faster delivery of web pages and reduces web traffic as compared to HTTP/1.0. However, TCP starts slowly and with domain sharding (resources can be downloaded simultaneously by using multiple domains), connection reuse and pipelining, there is an increased risk of network congestion.
  
HTTP/2-
  Uses multiplexing, where over a single TCP connection resources to be delivered are interleaved and arrive at the client almost at the same time. It is done using streams which can be prioritized, can have dependencies and individual flow control. It also provides a feature called server push that allows the server to send data that the client will need but has not yet requested.
  
  Underlying semantics of HTTP such as headers, status codes remains the same.
  
  Security concerns from previous versions will continue to be seen in HTTP/2. However, it is better equipped to deal with them due to new TLS features like connection error of type Inadequate_Security.
  
  HTTP/2 does not change much in terms of caching. With the server push feature if the client finds the resources are already present in the cache, it can cancel the pushed stream.
  
  HTTP/2 utilizes multiplexing and server push to effectively reduce the page load time by a greater margin along with being less sensitive to network delays.

Q2. Write a blog about objects and its internal representation in Javascript
Ans-

Objects, in JavaScript, it???s most important data-type and forms the building blocks for modern JavaScript. These objects are quite different from JavaScript???s primitive data-types(Number, String, Boolean, null, undefined and symbol) in the sense that while these primitive data-types all store a single value each (depending on their types).

Objects are more complex and each object may contain any combination of these primitive data-types as well as reference data-types.
An object, is a reference data type. Variables that are assigned a reference value are given a reference or a pointer to that value. That reference or pointer points to the location in memory where the object is stored. The variables don???t actually store the value.

Loosely speaking, objects in JavaScript may be defined as an unordered collection of related data, of primitive or reference types, in the form of ???key: value??? pairs. These keys can be variables or functions and are called properties and methods, respectively, in the context of an object.

For Eg. If object is a student, it will have properties like name, age, address, id, etc and methods like updateAddress, updateNam, etc.

Objects and properties:-

A JavaScript object has properties associated with it. A property of an object can be explained as a variable that is attached to the object. Object properties are basically the same as ordinary JavaScript variables, except for the attachment to objects. The properties of an object define the characteristics of the object. You access the properties of an object with a simple dot-notation:

sytax-
objectName.propertyName

Like all JavaScript variables, both the object name (which could be a normal variable) and property name are case sensitive. You can define a property by assigning it a value. For example, let???s create an object named myCar and give it properties named make, model, and year as follows:

var myCar = {
make = 'Ford',
model = 'Mustang',
year = 1969
};

Unassigned properties of an object are undefined (and not null).

myCar.color; // undefined

Properties of JavaScript objects can also be accessed or set using a bracket notation. Objects are sometimes called associative arrays, since each property is associated with a string value that can be used to access it. So, for example, you could access the properties of the myCar object as follows:

myCar['make'] = 'Ford';
myCar['model'] = 'Mustang';
myCar['year'] = 1969;

An object property name can be any valid JavaScript string, or anything that can be converted to a string, including the empty string. However, any property name that is not a valid JavaScript identifier (for example, a property name that has a space or a hyphen, or that starts with a number) can only be accessed using the square bracket notation. This notation is also very useful when property names are to be dynamically determined (when the property name is not determined until runtime). Examples are as follows:

// four variables are created and assigned in a single go, 
// separated by commas
var myObj = new Object(),
    str = 'myString',
    rand = Math.random(),
    obj = new Object();
myObj.type              = 'Dot syntax';
myObj['date created']   = 'String with space';
myObj[str]              = 'String value';
myObj[rand]             = 'Random Number';
myObj[obj]              = 'Object';
myObj['']               = 'Even an empty string';
console.log(myObj);

Creating Objects In JavaScript :
Create JavaScript Object with Object Literal
One of easiest way to create a javascript object is object literal, simply define the property and values inside curly braces as shown below

let bike = {name: 'SuperSport', maker:'Ducati', engine:'937cc'};
this is key:value pair object.

You can use for-in loop to iternate the object values as given below-
syntax -

for(key in object)
{
  console.log(objectname[keyname]);
}

so here you object is bike -
for(i in bike)
{
  console.log(bike[i]);
}

there are two more concepts-
1) copy by value
2) copy by reference

Copy by value- 
Primitive datatypes i.e. inbuilt datatype(ex-number,boolean,string) are involved in copy by value.
ex-
var a=23;
var b=a;
a=34;
console.log(a,b); o/p=23,34
so this is how it copied the value of one variable to another.
and it will create new object for it.

copy by reference-
For single objects will have multiple refernces.

ex-
var obj={
name:"Jhon",
age:23};
var obj1=obj;
console.log(obj.name); o/p=Jhon

As we seen in copy by value, it is creating new object but, in this copy by reference case it will just take reference of the object obj.

So, this is how we can create and access the JS object.
