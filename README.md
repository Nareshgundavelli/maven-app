🚀 Maven JAR Application – Demo Project
📌 Project Overview

This is a simple Java application built using Apache Maven.
It demonstrates how to:

Create a Maven project
Build a JAR file
Fix common Maven errors
Run the application successfully
🛠️ Technologies Used
Java (JDK 11 or higher)
Apache Maven
Linux / AWS EC2 (Amazon Linux)
⚙️ Setup Instructions
1️⃣ Install Java & Maven
sudo yum update -y
sudo yum install java-11-amazon-corretto -y
sudo yum install maven -y

Verify:

java -version
mvn -version
2️⃣ Create Maven Project
mvn archetype:generate \
-DgroupId=com.naresh \
-DartifactId=demo-app \
-DarchetypeArtifactId=maven-archetype-quickstart \
-DinteractiveMode=false
3️⃣ Navigate to Project
cd demo-app
4️⃣ Build Project
mvn clean package

👉 This will:

Compile code
Run tests
Create JAR file
5️⃣ Run Application
java -jar target/demo-app-1.0-SNAPSHOT.jar
📂 Project Structure
demo-app/
 ├── src/
 │   ├── main/java        # Application code
 │   └── test/java        # Test cases
 ├── pom.xml              # Maven configuration
 └── target/              # Build output (JAR file)
🔥 Common Errors & Solutions
❌ 1. Source option 5 is no longer supported

Error:

Source option 5 is no longer supported

Reason:
Old Maven project uses Java 1.5

Fix: Add this in pom.xml

<properties>
  <maven.compiler.source>11</maven.compiler.source>
  <maven.compiler.target>11</maven.compiler.target>
</properties>
❌ 2. No main manifest attribute

Error:

no main manifest attribute

Reason:
JAR doesn’t know which class to run

Fix: Add plugin in pom.xml

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
❌ 3. Malformed POM (build tag error)

Error:

Unrecognised tag: 'build'

Reason:
<build> placed inside <dependencies>

Fix:

Move <build> outside <dependencies>
🎯 Key Maven Commands
mvn clean      # Remove old build
mvn compile    # Compile code
mvn test       # Run tests
mvn package    # Create JAR/WAR
mvn install    # Install in local repo
💡 Key Concepts
JAR → Standalone application (runs with java -jar)
WAR → Web application (deploy on Tomcat)
pom.xml → Configuration file for dependencies & build
🚀 Output
Hello Naresh! Your JAR is running successfully 🚀
📚 Learning Outcome

By completing this project, you learned:

Maven basics
Build lifecycle
Dependency management
Debugging real-world errors
Running Java applications
👨‍💻 Author

Naresh
