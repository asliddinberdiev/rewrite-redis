# Rewrite Redis (Go Implementation)

A simplified, high-performance Redis-clone implemented in **Go** for educational purposes. This project demonstrates how to build a TCP server, handle concurrent client connections using Go routines, and parse the **RESP** (Redis Serialization Protocol).



## 🚀 Features

* **TCP Server:** Built using the `net` package to handle multiple concurrent connections.
* **RESP Protocol:** Custom implementation and integration with `github.com/tidwall/resp` for command parsing[cite: 1, 3].
* **In-Memory Storage:** A thread-safe Key-Value store utilizing `sync.RWMutex` for data integrity.
* **Supported Commands:**
    * `SET <key> <value>`: Store a string value.
    * `GET <key>`: Retrieve a stored value.
* **Built-in Client:** Includes a Go client SDK for easy integration.

## 🛠 Prerequisites

* **Go:** Version 1.25.5 or higher.
* **Make:** For running automated build commands.

## 📦 Installation & Usage

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/asliddinberdiev/rewrite-redis.git
    cd rewrite-redis
    ```

2.  **Run the Server:**
    The server listens on port `:5001` by default.
    ```bash
    make run
    ```

3.  **Run Tests:**
    Execute the integration tests to see the server in action:
    ```bash
    go test -v ./...
    ```

## 📂 Project Structure

* `main.go`: Server initialization and flag handling.
* `server.go`: Core server logic and connection loops.
* `peer.go`: Manages individual client connections and RESP reading.
* `keyval.go`: Thread-safe data storage implementation.
* `proto.go`: RESP command definitions and parsing logic.
* `client.go`: Go client library for the server.

## 🗺 Roadmap

- [ ] Support for more Redis data types (Lists, Sets).
- [ ] Persistence (saving data to a file).
- [ ] Support for `DEL` and `EXPIRE` commands.