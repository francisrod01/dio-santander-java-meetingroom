# dio-santander-java-meetingroom

Back-end application for meeting room reservations using Spring Boot.

The front-end **Angular** application is:  
https://github.com/francisrod01/dio-santander-angular-meetingroom

A project built during the **Santander Full-stack developer** bootcamp on the **Digital Innovation One** platform.

- Author: [Francis Rodrigues](https://github.com/francisrod01)

## Workspace environment

- Java 16
- Maven 4.0.0
- IntelliJ IDE or VSCode with `Java Extension Pack` plugin enabled

## How to get started

Start the spring application by running the `mavenw` binary with the command `./mavenw spring-boot:run`

Then you'll need to insert some records in the h2 database.
In a command line do it using the command `curl` as we don't have an interface to do it now.

```bash
 curl -H "Content-Type: application/json" -d '{ "name": "Digital Innovation One", "date": "09/05/2021", "startHour": "21hs", "endHour": "23hs" }' http://localhost:8082/api/v1/rooms | json_pp

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   162    0    80  100    82   6112   6265 --:--:-- --:--:-- --:--:--  6307

{
  "id": 1,
  "name": "Digital Innovation One",
  "date": "09/05/2021",
  "startHour": "21hs",
  "endHour": "23hs"
}
```

Do it more times providing different information. Let's check what we have put in the database until now.

Now run the command `curl http://localhost:8082/api/v1/rooms | json_pp` as below:

```bash
curl http://localhost:8082/api/v1/rooms | json_pp

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   258    0   258    0     0   3986      0 --:--:-- --:--:-- --:--:--  4031
[
   {
      "name" : "Digital Innovation One",
      "startHour" : "21hs",
      "endHour" : "23hs",
      "id" : 1,
      "date" : "09/05/2021"
   },
   {
      "date" : "09/05/2021",
      "id" : 2,
      "endHour" : "23hs",
      "startHour" : "22hs",
      "name" : "crud"
   },
   {
      "endHour" : "23hs",
      "name" : "spring",
      "startHour" : "20hs",
      "id" : 3,
      "date" : "09/05/2021"
   }
]
```

Your Spring Boot REST API is working now, otherwise you'll receive this output:

```bash
curl http://localhost:8082/api/v1/rooms | json_pp

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0

curl: (7) Failed to connect to localhost port 8082: Connection refused
malformed JSON string, neither array, object, number, string or atom, at character offset 0 (before "(end of string)") at /usr/bin/json_pp line 45.
```
