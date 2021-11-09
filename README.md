# ESEO - Projet Bibliotheque en J2E

### Premier lancement

**Si c'est la première fois que vous démarrez le projet,** il faut créer un conteneur docker qui va contenir notre base de données mariadb.
```
docker run -e MYSQL_ROOT_PASSWORD=MySQL2021 -p 127.0.0.1:3306:3306 --name mariadb_td3 -d mariadb
```

Deuxième étape, on se connecte au conteneur.
```
docker exec -it mariadb_td3 mysql -u root -p
```

Ensuite on peut y créer notre base de données.
```sql
CREATE DATABASE library DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
use library;
create table books(id INT(13) NOT NULL AUTO_INCREMENT ,title VARCHAR(100) NOT NULL, author VARCHAR(100) NOT NULL, description VARCHAR(300), PRIMARY KEY(id));
insert into books(title, author, description) values("Angular Development with TypeScript","Yakov Fain","This practical book covers real-world development concerns like state management, data and views, user interaction with forms, and communicating with servers.");
insert into books(title, author, description) values("Programmer en Java: Couvre Java 10 à Java 14","Claude Delannoy","Apprentissage du langage Java.");
```

### Projet déjà lancé au moins une fois
**Si jamais ce n'est pas la première fois que vous démarrez le projet,** il faut direct lancer le conteneur *mariadb_td3* via l'interface Docker Desktop.



