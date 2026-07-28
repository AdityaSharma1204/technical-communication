# REST Architecture

## Introduction

REST (Representational State Transfer) is a software architectural style used to design web services. It was introduced by Roy Fielding in 2000. REST provides a simple and efficient way for different applications to communicate over the internet. Most modern web applications and APIs use REST because it is lightweight, scalable, and easy to understand. REST commonly uses the HTTP protocol to exchange data between clients and servers.

## Principles of REST Architecture

The main principles of REST architecture are:

* Client and server are separated, allowing both to evolve independently.
* Communication between the client and server is stateless. Every request contains all the information needed to process it.
* Resources are identified using unique URLs.
* Responses can be cached to improve performance.
* A consistent interface makes APIs easier to use and maintain.
* The system can be designed in layers to improve security and scalability.

## HTTP Methods Used in REST

REST APIs use standard HTTP methods to perform different operations.

1. GET – Retrieves data from the server.
2. POST – Creates a new resource.
3. PUT – Updates an existing resource.
4. DELETE – Removes a resource.
5. PATCH – Updates part of an existing resource.

## Example

A REST API for managing students may use the following endpoints:

* `GET /students` – Returns all students.
* `GET /students/101` – Returns the student with ID 101.
* `POST /students` – Creates a new student.
* `PUT /students/101` – Updates the student with ID 101.
* `DELETE /students/101` – Deletes the student with ID 101.

## Advantages of REST Architecture

* Easy to understand and implement.
* Platform-independent because it uses standard HTTP.
* Supports multiple data formats such as JSON and XML.
* Improves scalability through stateless communication.
* Allows caching to increase performance.
* Widely used in web, mobile, and cloud applications.

## Conclusion

REST architecture has become the standard approach for building modern web services and APIs. Its simple design, scalability, and flexibility make it suitable for applications of all sizes. By following REST principles, developers can create reliable, maintainable, and efficient APIs that can be accessed by different clients such as websites, mobile applications, and desktop software.

## References

* https://restfulapi.net/
* https://aws.amazon.com/what-is/restful-api/
* https://developer.mozilla.org/en-US/docs/Web/HTTP
* https://en.wikipedia.org/wiki/Representational_state_transfer
* https://www.geeksforgeeks.org/rest-api-introduction/
