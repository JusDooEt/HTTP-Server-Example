[![progress-banner](https://backend.codecrafters.io/progress/http-server/411a2e6e-0fe6-4810-885d-ac9cc536d763)](https://app.codecrafters.io/users/codecrafters-bot?r=2qF)

This is a starting point for C++ solutions to the
["Build Your Own HTTP server" Challenge](https://app.codecrafters.io/courses/http-server/overview).

[HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) is the
protocol that powers the web. In this challenge, you'll build a HTTP/1.1 server
that is capable of serving multiple clients.

**Note**: If you're viewing this repo on GitHub, head over to
[codecrafters.io](https://codecrafters.io) to try the challenge.
# Newest Update
This program will now determine if data needs to be encrypted via the gzip encoding method when a 'GET /echo/' request is sent. It will encrypt the data using the zlib library function and constants and send back an appropriate response with the gzip encrypted data.
# About
This project is a challenge that was provided by [codecrafters.io](https://app.codecrafters.io/catalog?_gl=1*kgzjyd*_ga*MTA2MzY1OTcyOS4xNzE3MTgwNTE5*_ga_N8D6K4M2HE*MTcxNzQ1Mzk2NS4yLjAuMTcxNzQ1Mzk2NS4wLjAuMA..) that challenges developers to create a HTTP server. The main challenge of this project was learning how HTTP messages are formatted and how to parse requests and responses to meet the format's requirements. In order to interpret a request, the message must be broken down into different strings representing a start line, HTTP headers, and a body if one is present. From there the start line will provide the main instructions of the request and the headers will provide specifications for the start line and the body if one is present. A response will be structured similarly but the start line will indicate a success or failure.

# Functionality
- This program will receive a HTTP request and parse the string received into usable data that is stored into a struct object 'ClientRequest'
   - This struct will store the start line, the directory path, headers, body content, and the instruction found in the start line separately as member variables.
   - A map object is created to store the headers and the data for each header.
      - The header title is used for the key of the map in order to find it's corresponding data.
      - A method called setHeader will be used to create the map member variable
      - A method called containsHeader will be used to verify wether a header exists in the ClientRequest object
      - The get header method will return the data stored in the headers map relating to the key sent through the function.
   - The method stringToMethod will convert a string passed to the function into an enum type of Method and return the enum value.
- This program will create an appropriate HTTP response and store it into a class object 'ServerResponse'
   - This class will store the status line, headers, and the body content in member variables.
- The split function will split a string using a specified delimiter character and returning a vector containing the split string
- The split encoding function will function similarly to the split function but will check for any leading white space in the created substrings and remove it from the string if found.
- The program will then correctly format the HTTP response and send it.
- This server supports one kind of encoding method and includes a gzip_compression function to compress the data within the body of the response.
   - The gzip_compression function uses the zlib library.
      - This library is used to compress the HTTP body data to the required encoded data for this challenge.
      - The functions deflateInit2, deflate, and delateEnd are utilized from the zlib library
      - Many other constants from the zlib library are used as arguments for the function used from the same library.


