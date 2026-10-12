# AutoLoc API — Atelier 1

Starter project for Java 17+, Spring Boot 3.5.16, Maven, Spring Data JPA, Lombok and XAMPP's MariaDB.

## 1. Database setup

Start **Apache** and **MySQL** (MariaDB) from the XAMPP Control Panel. Open `http://localhost/phpmyadmin`, select the SQL tab and execute:

```sql
CREATE DATABASE IF NOT EXISTS autoloc_db
  CHARACTER SET utf8mb4
  COLLATE utf8mb4_unicode_ci;
```

The standard XAMPP database account often has username `root` and an empty password. If you configured a password, change `spring.datasource.password` in `src/main/resources/application.properties`.

## 2. Open in IntelliJ

Open the `autoloc-api` folder in IntelliJ as a Maven project. Use JDK 17 or newer. Wait for Maven dependencies to download. Enable Lombok annotation processing in Settings if IntelliJ marks generated getters/setters as unresolved.

## 3. Run

Run `src/main/java/tn/esprit/autoloc/AutolocApiApplication.java`. With the database service reachable and credentials correct, Hibernate creates/updates the nine entity tables. Refresh `autoloc_db` in phpMyAdmin.

Expected tables: `agence`, `client`, `contrat`, `employe`, `equipement`, `maintenance`, `paiement`, `reservation`, `vehicule`.

No entity relationships are defined yet, in accordance with Atelier 1; foreign keys will be introduced during Atelier 2.

> `spring.jpa.hibernate.ddl-auto=update` is a development setting. Do not use it as-is for a production database.
