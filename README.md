# FreeFooders

FreeFooders is a distributed MapReduce-based restaurant inventory and order processing system implemented in Java. It demonstrates a simple MapReduce framework, a Master–Worker architecture, and client applications for both customers and managers to interact with a network of food stores.

## Features

* **Custom MapReduce Framework**: Lightweight Java implementation for map and reduce jobs.
* **Master–Worker Architecture**: MasterServer coordinates tasks and Workers process data.
* **Client Applications**:

  * **CustomerClient**: Browse nearby stores, view products, place orders.
  * **Manager**: Manage store inventory and view sales statistics.
* **Sample Data**: Includes JSON files for multiple store locations and menus.

## Project Structure

```
FreeFooders/
├── app/                       # Core Java application (Gradle project)
│   ├── src/main/java/
│   │   ├── Freefooders/       # Core client entry points
│   │   │   ├── Client.java
│   │   │   └── CustomerClient.java
│   │   ├── Manager/           # Manager console app
│   │   │   ├── Manager.java
│   │   │   ├── ProductManager.java
│   │   │   └── StoreManager.java
│   │   ├── Master/            # Master server components
│   │   │   ├── MasterServer.java
│   │   │   └── ActionForClients.java
│   │   ├── Worker/            # Worker node
│   │   │   └── Worker.java
│   │   ├── Reduce/            # Reducer logic
│   │   │   ├── Reduce.java
│   │   │   └── ReduceHandler.java
│   │   └── mapreduce/         # MapReduce framework
│   │       └── MapReduceFramework.java
│   └── resources/jsonf/stores/  # Sample store JSON definitions
├── lib/                       # External libraries (GSON)
│   └── gson-2.12.1.jar
├── build.gradle.kts           # Root Gradle build
├── settings.gradle.kts        # Gradle settings
├── gradlew / gradlew.bat      # Gradle wrapper scripts
├── Logos.txt                  # Link to store logos assets
└── ΑΜ.txt                     # (Optional student metadata)
```

## Prerequisites

* **Java 11 or higher**
* **Gradle 7+**

## Build Instructions

From the project root, run:

```bash
./gradlew build
```

This compiles sources, runs tests, and assembles `app.jar` under `app/build/libs/`.

## Running the Application

You can start each component from the command line using the generated JAR and the GSON library:

### 1. Master Server

```bash
java -cp app/build/libs/app.jar:lib/gson-2.12.1.jar Master.MasterServer
```

### 2. Worker Nodes

In one or more terminals, run:

```bash
java -cp app/build/libs/app.jar:lib/gson-2.12.1.jar Worker.Worker
```

### 3. Customer Client

```bash
java -cp app/build/libs/app.jar:lib/gson-2.12.1.jar Freefooders.Client
```

### 4. Manager Console

```bash
java -cp app/build/libs/app.jar:lib/gson-2.12.1.jar Manager.Manager
```

## Data & Configuration

* Sample store JSON files are located in `app/src/main/resources/jsonf/stores/`.
* To add or modify stores, drop new JSON files in that folder with the same schema.

## Store Logos

High‑resolution logos and assets are available here:

```
https://drive.google.com/drive/folders/1r0IkOkDicrR-OQefapWP3jj0nHApN9qV?usp=sharing
```

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests for new features, bug fixes, or documentation improvements.

## License

This project is open‑source under the MIT License.
