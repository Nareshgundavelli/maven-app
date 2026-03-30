# 🚀 Maven JAR Application (Demo Project)

<p align="center">
  <b>Simple Java Application using Maven Build Tool</b><br>
  Build • Package • Run • Debug
</p>

---

## 📌 Overview

This project demonstrates how to build and run a **Java application using Apache Maven**.
It covers the complete workflow from project creation to execution, including **real-world error handling**.

---

## 🛠️ Tech Stack

* ☕ Java (JDK 11+)
* 📦 Apache Maven
* 🐧 Linux / AWS EC2 (Amazon Linux)

---

## ⚙️ Installation & Setup

### 🔹 Install Java & Maven

```bash
sudo yum update -y
sudo yum install java-11-amazon-corretto -y
sudo yum install maven -y
```

### 🔹 Verify Installation

```bash
java -version
mvn -version
```

---

## 🚀 Project Setup

### 🔹 Create Maven Project

```bash
mvn archetype:generate \
-DgroupId=com.naresh \
-DartifactId=demo-app \
-DarchetypeArtifactId=maven-archetype-quickstart \
-DinteractiveMode=false
```

### 🔹 Navigate to Project

```bash
cd demo-app
```

---

## 🏗️ Build the Application

```bash
mvn clean package
```

✔️ This will:

* Compile code
* Run tests
* Generate JAR file

---

## ▶️ Run the Application

```bash
java -jar target/demo-app-1.0-SNAPSHOT.jar
```

---

## 📂 Project Structure

```
demo-app/
 ├── src/
 │   ├── main/java        → Application code
 │   └── test/java        → Test cases
 ├── pom.xml              → Maven configuration
 └── target/              → Output (JAR file)
```

---

## 🔥 Common Errors & Fixes

### ❌ 1. Java Version Error

```
Source option 5 is no longer supported
```

✔️ **Fix:**

```xml
<properties>
  <maven.compiler.source>11</maven.compiler.source>
  <maven.compiler.target>11</maven.compiler.target>
</properties>
```

---

### ❌ 2. No Main Manifest Attribute

```
no main manifest attribute
```

✔️ **Fix:**

```xml
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-jar-plugin</artifactId>
      <version>3.2.2</version>
      <configuration>
        <archive>
          <manifest>
            <mainClass>com.naresh.App</mainClass>
          </manifest>
        </archive>
      </configuration>
    </plugin>
  </plugins>
</build>
```

---

### ❌ 3. Malformed POM Error

```
Unrecognised tag: 'build'
```

✔️ **Fix:**

* Ensure `<build>` is **outside `<dependencies>`**

---

## 🧠 Maven Lifecycle

```
clean → compile → test → package → install
```

---

## 🎯 Key Concepts

* **JAR** → Standalone app (runs using JVM)
* **WAR** → Web app (deploy on Tomcat)
* **pom.xml** → Project configuration file

---

## ✅ Output

```
Hello Naresh! Your JAR is running successfully 🚀
```

---

## 💡 What You Learned

✔️ Maven project setup
✔️ Build lifecycle
✔️ Dependency management
✔️ Debugging real errors
✔️ Running Java applications

---

## 👨‍💻 Author

**Naresh**

