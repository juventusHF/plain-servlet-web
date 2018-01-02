# Übung zum Java Servlets

Sieh nach, wie im `pom.xml` die Abhängigkeit zum Servlet API und das Tomcat Maven Plugin definiert sind.

Kompiliere das Projekt:

    mvn package
    
Als Ergebnis wird ein `.war`-File im `target` Ordner erzeugt. 
Inspiziere den Ordner `target/plain-servlet-web-1.0-SNAPSHOT`, um die Anatomie eines `.war`-Files zu sehen.

Starte nun Tomcat:

    mvn tomcat7:run
    
Du kannst nun die Applikation unter folgender URL aufrufen: http://localhost:8080/plain-servlet-web/hello

Erweitere das `HelloServlet` um folgende Fähigkeiten:

- Anstatt HTML soll folgende JSON-Struktur zurückgegeben werden: `{ greeting: "Hello", name: "Linda" }`. 
  - Achte auf den korrekten Content-Type.
- Nun soll `name` dynamisch sein, d.h. als GET-Parameter übergeben werden: http://localhost:8080/plain-servlet-web/hello?name=Bob
  - Welches in der `doGet`-Methode bereits verfügbare Objekt könnte die Information über den übermittelten Request-Parameter enthalten?
  - Ist der Parameter extrahiert, lässt er sich in die JSON-Struktur entsprechend einbetten.