# SQL Lab

The Springfield Cinema is having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'

```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:

```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1.  Return ALL the data in the 'movies' table.
    SELECT * FROM movies;

2.  Return ONLY the name column from the 'people' table
    SELECT name FROM people;

3.  Oops! Someone spelled Krusty The Clown's name wrong! Change it to reflect the proper spelling (Crusty should be Krusty).
    UPDATE people SET name = 'Krusty the clown' WHERE name = 'Crusty the Clown';
    SELECT name FROM people;

4.  Return ONLY Homer Simpson's name from the 'people' table.
    SELECT name FROM people WHERE name = 'Homer Simpson';

5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.
        DELETE FROM movies WHERE title = 'Batman Begins';

6.  We forgot one of the main characters! Add Bart Simpson to the 'people' table
    INSERT INTO people (name) VALUES ('Bart Simpson');


7.  Eric Cartman has decided to hijack our movie evening, Remove him from the table of people.
    DELETE FROM people WHERE name = 'Eric Cartman';

8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.
        INSERT INTO movies (title, show_time) VALUES ('Avengers: Infinity War','00:00');

9.  The cinema would like to make the Iron Man movies a triple billing. Find out the show time of "Iron Man 2" and set the show time of "Iron Man 3" to start two hours later.
        UPDATE movies SET show_time = '20:45' WHERE title = 'Iron Man 3';


## Extension

1.  Research how to delete multiple entries from your table in a single command.
        DELETE FROM your_table_name WHERE X IN
        DELETE FROM table_name WHERE X is ... example
        DELETE FROM table_name WHERE name = 'Homer Simpso', 'Lisa Simpson'; or 
        DELETE FROM table_name WHERE name IN ('Homer','Lisa');

        DELETE FROM people
        WHERE SUBSTR(name, 1, 1) = 'M';
        SELECT name FROM people;
        meaning:
        The SUBSTRING function accepts three arguments:
        The source_string is the string from which you want to extract the substring.
        The position is the starting position where the substring begins. The first position of the string is one (1).
        The length is the length of the substring. The length argument is optional. 