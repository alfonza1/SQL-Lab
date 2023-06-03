CREATE DATABASE MovieDB;

USE MovieDB;

INSERT INTO Movies(Title, Runtime, Genre, IMDB_Score, Rating)
VALUES
('Howard the Duck', 110, 'Sci-Fi', 4.6, 'PG'),
('Lavalantula', 83, 'Horror', 4.7, 'TV-14'),
('Starship Troopers', 129, 'Sci-Fi', 7.2, 'PG-13'),
('Waltz With Bashir', 90, 'Documentary', 8.0, 'R'),
('Spaceballs', 96, 'Comedy', 7.1, 'PG'),
('Monsters Inc.', 92, 'Animation', 8.1, 'G');


INSERT INTO Movies(Title, Runtime, Genre, IMDB_Score, Rating)
VALUES
('Insidious', 148, 'Horror', 8.8, 'PG-13'),
('Friday', 81, 'Comedy', 10, 'R');

SELECT * FROM Movies WHERE Genre = 'Sci-Fi';


SELECT * FROM Movies WHERE IMDB_Score >= 6.5;


SELECT * FROM Movies WHERE Rating IN ('G', 'PG') AND Runtime < 100;


SELECT Genre, AVG(Runtime) FROM Movies WHERE IMDB_Score < 7.5 GROUP BY Genre;


UPDATE Movies SET Rating = 'R' WHERE Title = 'Starship Troopers';


SELECT ID, Rating FROM Movies WHERE Genre IN ('Horror', 'Documentary');


SELECT Rating, AVG(IMDB_Score), MAX(IMDB_Score), MIN(IMDB_Score) FROM Movies GROUP BY Rating;


SELECT Rating, AVG(IMDB_Score), MAX(IMDB_Score), MIN(IMDB_Score) FROM Movies GROUP BY Rating HAVING COUNT(*) > 1;


DELETE FROM Movies WHERE Rating = 'R';
