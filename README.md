# Intro to SQL

1.  Install the SQLite Browser if you haven't already [here](http://sqlitebrowser.org/)
2.  Open the SQLite Browser and click 'File -> Open DataBase'
3.  Choose the `chinook.db` file from this repo. This database is open source and maintained by Microsoft.
4.  Click the tab that says 'Execute SQL'. Type SQL queries in the box above. Press the play button. See the results of that query in the box below

## Challenges

1. Write the SQL to return all of the rows in the artists table
```SQL
SELECT * FROM artists;
```

2. Write the SQL to select the artist with the name "Black Sabbath"
```SQL
SELECT name FROM artists where name = "Black Sabbath";
```

3. Write the SQL to create a table named 'fans' with an autoincrementing ID that's a primary key and a name field of type text
```SQL
CREATE TABLE fans(id INTEGER PRIMARY KEY, name STRING);
```

4. Write the SQL to alter the fans table to have a artist_id column type integer
```SQL
ALTER TABLE fans ADD COLUMN artist_id INTEGER;
```

5. Write the SQL to add yourself as a fan of the Black Eyed Peas (ArtistId 169)
```SQL
INSERT INTO fans (name, artist_id) 
VALUES
("Corinna", 169);
```

6. Check out the Faker gem. 
    - gem install faker
    - open up irb
    - run require 'faker'
    - generate a fake name for yourself using Faker::Name.name. 
    - How would you update your name in the fans table to be your new name?
    
    ```SQL
    UPDATE fans
    SET name = "Cristopher Bode"
    WHERE id = 1;
    ```

7. Write the SQL to delete your row in the fans table.
```SQL
DELETE FROM fans WHERE id = 1;
```

8. Write the SQL to return fans that are not fans of the black eyed peas.
```SQL
SELECT * FROM fans WHERE artist_id IS NOT 169;
```