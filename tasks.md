# Football Matches - Tasks

Each of the questions/tasks below can be answered using a `SELECT` query. When you find a solution copy it into the code block under the question before pushing your solution to GitHub.

1) Find all the matches from 2017.

```sql

-- SELECT * FROM matches 
-- WHERE SEASON = 2017; 
```

2) Find all the matches featuring Barcelona.

```sql

-- SELECT * FROM matches 
-- WHERE hometeam, awayteam
-- LIKE 'Barcelona';
```

3) What are the names of the Scottish divisions included?

```sql

-- SELECT DISTINCT name FROM divisions
-- WHERE country = 'Scotland';
```

4) Find the value of the `code` for the `Bundesliga` division. Use that code to find out how many matches Freiburg have played in that division. HINT: You will need to query both tables

```sql
-- SELECT DISTINCT code from divisions 
-- WHERE name = 'Bundesliga';

-- SELECT COUNT(*) from matches 
-- WHERE division_code = 'D1' AND hometeam = 'Freiburg';

-- SELECT COUNT(*) from matches
-- WHERE division_code = 'D1' AND awayteam = 'Freiburg';

```

5) Find the teams which include the word "City" in their name. 

```sql

-- SELECT DISTINCT awayteam FROM matches
-- WHERE awayteam LIKE '%City%' OR a

-- SELECT DISTINCT hometeam FROM matches
-- WHERE hometeam LIKE '%City%';
```

6) How many different teams have played in matches recorded in a French division?

```sql

-- SELECT code FROM divisions
-- WHERE country = 'France';

-- SELECT DISTINCT hometeam, awayteam FROM matches
-- WHERE division_code = 'F1' OR division_code = 'F2';
```

7) Have Huddersfield played Swansea in any of the recorded matches?

```sql

-- SELECT * FROM matches
-- WHERE hometeam = 'Swansea' AND awayteam = 'Huddersfield';

-- SELECT * FROM matches
-- WHERE hometeam = 'Huddersfield' AND awayteam = 'Swansea';
```

8) How many draws were there in the `Eredivisie` between 2010 and 2015?

```sql

-- SELECT DISTINCT code FROM divisions
-- WHERE name = 'Eredivisie';

-- SELECT * from matches 
-- WHERE ftr = 'D'
-- AND division_code = 'N1';
```

9) Select the matches played in the Premier League in order of total goals scored from highest to lowest. When two matches have the same total the match with more home goals should come first.

Premier league matches sum of the goals ordered fthg desc
```sql
-- SELECT DISTINCT code from divisions
-- WHERE name = 'Premier League';

-- SELECT hometeam, fthg, awayteam, ftag from matches 
-- WHERE division_code = 'E0'
-- ORDER BY fthg desc, fthg + ftag desc;

```

10) In which division and which season were the most goals scored?

```sql

-- SELECT DISTINCT fthg, ftag, season, division_code FROM matches
-- ORDER BY fthg DESC;

-- SELECT DISTINCT fthg, ftag, season, division_code FROM matches
-- ORDER BY ftag DESC;
```


### Useful Resources

- [Filtering results](https://www.w3schools.com/sql/sql_where.asp)
- [Ordering results](https://www.w3schools.com/sql/sql_orderby.asp)
- [Grouping results](https://www.w3schools.com/sql/sql_groupby.asp)