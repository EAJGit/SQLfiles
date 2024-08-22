show databases;
create database universe;
USE UNIVERSE;
SELECT DATABASE();


CREATE TABLE tbl_heroes(

HeroID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
Name VARCHAR(30) NOT NULL,
Origin VARCHAR (10) NOT NULL,
Power VARCHAR (10) NOT NUll
);

SHOW TABLES;

DESC tbl_heroes;
EXPLAIN tbl_heroes;

CREATE TABLE tbl_villains(

villID INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
Name VARCHAR(30) NOT NULL,
Origin VARCHAR (10) NOT NULL,
Power VARCHAR (10) NOT NUll
);

DESC tbl_villains;

CREATE TABLE tbl_heroloss(
HeroID INT NOT NULL,
Date DATE,
CONSTRAINT HeroID
 FOREIGN KEY(HeroID)
 REFERENCES tbl_heroes(HeroID)

ON DELETE CASCADE
ON UPDATE CASCADE);

CREATE TABLE tbl_villloss(
villID INT NOT NULL,
Date DATE,
CONSTRAINT villID
 FOREIGN KEY(villID)
 REFERENCES tbl_villains(villID)

ON DELETE CASCADE
ON UPDATE CASCADE);


ALTER TABLE tbl_heroes CHANGE COLUMN Origin Origin VARCHAR(50) NOT NULL;

ALTER TABLE tbl_heroes CHANGE COLUMN Power Power VARCHAR(50) NOT NULL;


ALTER TABLE tbl_villains CHANGE COLUMN Origin Origin VARCHAR(50) NOT NULL;

ALTER TABLE tbl_villains CHANGE COLUMN Power Power VARCHAR(50) NOT NULL;

UPDATE tbl_heroes
SET Power = 'Energy Absorption'
WHERE HeroID =1;

UPDATE tbl_heroes
SET Power = 'Psionic Powers'
WHERE HeroID =10;

DELETE FROM tbl_villains WHERE villID =8;
DELETE FROM tbl_villains WHERE villID =1;

INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Avalanche', 'Mutant', 'Tremor Emission');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Justin Hammer', 'Alpha Human', 'Genuis Intelligence');

UPDATE tbl_villains
SET villID = 1
WHERE villID =11;

UPDATE tbl_villains
SET villID = 8
WHERE villID =12;

INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Bishop', 'Mutant', 'Energy Absorption');
INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Firelord', 'Alien', ' Power Cosmic');
INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Shroud', 'Mutate', 'Darforce Manipulation ');
INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Temugin', 'Alpha Human', 'Martial Arts');
INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Xman', 'Mutant', 'Psionic Powers');
INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Rogue', 'Mutant', 'Super Strength');
INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Hercules', 'Alien', 'Super Strength');
INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Jocasta', 'Robot', 'Power suit');
INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Brother Voodoo', 'Alpha Human', 'Magic');
INSERT INTO tbl_heroes (Name, Origin, Power) VALUES ('Sage', 'Mutant', 'Enhanced Intelligence');

INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Avalanche', 'Mutant', 'Tremor Emission');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Super Skrull', 'Alien', ' Power Combo');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Kraven', 'Mutate', 'Combat Strategist ');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Zaran', 'Alpha Human', 'Martial Arts');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Black Queen', 'Mutant', 'Psionic Powers');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Mr Hyde', 'Mutate', 'Super Strength');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Ares', 'Alien', 'Super Strength');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Justin Hammer', 'Alpha Human', 'Genuis Intelligence');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Enchantress', 'Alien', 'Magic');
INSERT INTO tbl_villains (Name, Origin, Power) VALUES ('Baron Zemo', 'Alpha Human', 'Genuis Intelligence');

SELECT * FROM tbl_heroes;
SELECT * FROM tbl_villains;
SELECT * FROM tbl_heroloss;
SELECT * FROM tbl_villloss;

INSERT INTO tbl_villloss (villID, Date) VALUES ('2', '2024-07-25');
INSERT INTO tbl_villloss (villID, Date) VALUES ('6', '2024-07-25');

 SELECT * FROM tbl_heroes ORDER BY Power;
 SELECT * FROM tbl_heroes ORDER BY Power DESC;
 SELECT * FROM tbl_heroes ORDER By Origin;
 SELECT * FROM tbl_heroes ORDER By Name;
  SELECT Power FROM tbl_heroes GROUP BY Power;
   SELECT Origin FROM tbl_heroes ORDER By Origin;
 
  SELECT * FROM tbl_villains ORDER BY Power;
 SELECT * FROM tbl_villains ORDER BY Power DESC;
 SELECT * FROM tbl_villains ORDER By Origin;
 SELECT * FROM tbl_villains ORDER By Name;
  SELECT Power FROM tbl_villains GROUP BY Power;
   SELECT Origin FROM tbl_villains ORDER By Origin;
