# Client-Server Basics | TryHackMe Walkthrough

## Room Overview

In this room, I learned how computers communicate with each other using the **Client-Server model**. The room explains the concepts of clients, servers, protocols, ports, DNS, and IP addresses using a simple pizza delivery analogy. It also demonstrates how a web browser communicates with a web server using HTTP requests.

---

# Task 1: Introduction

In the early days, computers mostly worked independently. They stored their own files and ran their own programs without communicating with other systems.

As networks evolved, computers became connected, allowing them to share information and resources. This eventually led to the development of the modern Internet.

This room introduces the basic concepts behind communication between computers, including:

- Client
- Server
- DNS
- Port
- Protocol
- Network

### Answer

No answer needed.

---

# Task 2: Pizza Delivery

To explain the Client-Server model, TryHackMe uses a pizza takeaway analogy.

Alice wants a pizza and tells Bob her order. Bob goes to Luigi's Pizza, places the order, waits for the pizza, and brings it back to Alice.

This is similar to how computers communicate over a network.

<img width="1200" height="800" alt="image" src="https://github.com/user-attachments/assets/a7b1fa15-17f0-47c0-9668-b6183ceac10b" />

---

## Client and Server

In this example:

- **Alice** is the **Client** because she requests a service.
- **Luigi's Pizza** is the **Server** because it provides the service.
- **Bob** delivers the request and response between them.

Likewise, when we visit a website, our browser acts as the client and sends a request to the web server.

The client always starts the communication.

---

## Request and Response

The client sends a request to the server.

The server processes the request and returns a response.

If the requested resource is unavailable or the request is invalid, the server returns an error response.

---

## Protocol

A protocol defines how communication takes place between the client and server.

It specifies:

- Which commands are supported
- How requests are structured
- What syntax should be used
- What responses should be returned
- How errors should be handled

Without a common protocol, communication would not be possible.

---

## Port

A server can provide multiple services at the same time.

Each service listens on its own **port**.

Just like Luigi's Pizza may have different doors for takeaway, delivery, and dine-in services, each service on a server is identified using a different port.

---

## DNS

Instead of remembering an IP address, users type a website name.

DNS (**Domain Name System**) converts the website name into its corresponding IP address so the client can locate the server.

---

### Questions

**What do we use to identify a specific service on a server?**

```text
Port
```

**What do we call the address of a server?**

```text
Internet Protocol (IP) Address
```
---

# Task 3: Web Communication in Practice

The room then demonstrates how web browsers communicate with web servers using the **HTTP** protocol.

HTTP stands for **Hypertext Transfer Protocol** and is used to transfer web pages between clients and servers.

<img width="1200" height="800" alt="image" src="https://github.com/user-attachments/assets/35f5e216-3751-4826-aaa1-0c2cf87f8d43" />

---

## HTTP GET Method

The room focuses on the **GET** method.

A GET request is used to retrieve information from a web server.

Example:

```http
GET https://tryhackme.com/index.php
```

The browser automatically creates this request when we enter a website address.

The server then processes the request and returns the requested webpage.

---

## Inspecting a GET Request

Using Firefox Developer Tools, the room demonstrates how to inspect HTTP requests.

<img width="1366" height="977" alt="image" src="https://github.com/user-attachments/assets/1fb4c285-737b-4b67-9f14-60b46bdb7f0e" />

After opening the **Network** tab and refreshing the page, multiple GET requests become visible.

<img width="1380" height="582" alt="image" src="https://github.com/user-attachments/assets/63586848-df4d-4b04-80a5-4bd650d40975" />

Selecting one request displays useful information such as:

- Scheme
- Host
- Filename
- Address (IP)
- Status

Example:

| Field | Value |
|--------|-------|
| Scheme | HTTP |
| Host | httpdemo.local |
| Filename | / |
| Address | 127.0.0.1 |
| Status | 200 OK |

A **200 OK** status indicates that the request was successful.

---

## Response

Every HTTP request receives a response.

The response consists of two parts:

- **Response Header** – Contains metadata about the response.
- **Response Body** – Contains the requested webpage or resource.

The Response tab in Firefox Developer Tools displays the HTML returned by the server.

<img width="1380" height="1045" alt="image" src="https://github.com/user-attachments/assets/993aa442-d723-47ee-bc7a-db1a0d14217a" />

---

### Questions

<img width="1538" height="1344" alt="Screenshot 2026-07-27 173839" src="https://github.com/user-attachments/assets/38c80bf0-986b-486b-b1eb-63d6485483c8" />

**What would be the host in the following URL?**

https://www.iamlearning.thm/contact

```text
www.iamlearning.thm
```

**What would be the scheme in the following URL?**

https://www.iamlearning.thm/contact

```text
https
```

---

# Task 4: Conclusion

This room introduced the Client-Server model and explained how computers communicate over the internet.

Using the pizza delivery analogy made it easier to understand the roles of clients, servers, requests, responses, protocols, ports, and DNS.

The practical exercise also demonstrated how a browser sends HTTP requests and receives responses when loading a webpage.

### Answer

No answer needed.

---

# Key Takeaways

- The client always initiates communication.
- The server receives requests and returns responses.
- Protocols define how communication takes place.
- Ports identify individual services running on a server.
- DNS translates domain names into IP addresses.
- Browsers use HTTP requests to retrieve webpages from web servers.
