### Run app

``` bash
mvn package exec:java
```

### Run Dapr

``` bash
./daprd --app-id java-jetty --app-port 8080 --dapr-http-port 3500 --log-level debug --dapr-http-read-buffer-size 0
```

### Service invoke via REST Client

```
GET http://localhost:3500/v1.0/invoke/java-jetty/method/hello
```

Should Return:

``` html
<h1>Hello world!</h1>
```

This project contains a barebones example webapp that uses embedded Jetty and Maven to deploy a server.

This project is laid out like this:

- `hello-world-embedded-jetty-maven/`
  - **`pom.xml`** is a Maven [POM file](https://maven.apache.org/pom.html) that defines the project.
  - `src/main/` is a directory that contains the code.
    - `java/` is a directory that contains server-side code.
      - `io.happycoding.`**`ServerMain.java`** is the main class that sets up the server.
      - `io.happycoding.servlets.`**`HelloWorldServlet.java`** is a Java servlet that returns some HTML content.
    - `webapp/` is a directory that contains web files.
      - **`index.html`** is an HTML file that shows static content.

You can run this locally by executing this command:

```
mvn package exec:java
```

Learn more at [HappyCoding.io/tutorials/java-server](https://happycoding.io/tutorials/java-server).
