A feature called "track_commit_timestamp" has been enabled for our
primary PostgreSQL database server. While PostgreSQL does not track the
creation times of database objects, this feature will allow you to
determine exactly when a given record was inserted into a table.

    select pg_xact_commit_timestamp(xmin) from <yourtablename>;

This will show the time stamps for rows within the table you specify
(obviously, "<yourtablename>" should be changed to a refer to a specific
table, such as "lgc.livarhist", for example). However, the above query
only shows the most basic way of retrieving creation timestamps, and
isn't particularly useful. Please consider the following example
instead:

    SELECT pg_xact_commit_timestamp(xmin), * FROM <yourtablename>
    WHERE pg_xact_commit_timestamp(xmin) IS NOT null
    ORDER BY pg_xact_commit_timestamp(xmin) DESC LIMIT 10;

This will display all records in a specific table and order by the most
recent creation timestamp in descending order.

Alternatively, you could display the last 10 records (or any number you
determine) in ascending order, by writing something like:

    SELECT * FROM (SELECT pg_xact_commit_timestamp(xmin) AS crte_ts, * FROM <yourtable>
    WHERE pg_xact_commit_timestamp(xmin) IS NOT null
    ORDER BY pg_xact_commit_timestamp(xmin) desc LIMIT 10) AS qry1 ORDER BY crte_ts asc;

NOTE: This feature was only enabled on November 16, 2018, at around
11:00am. Any records written in any table before this date will not
contain commit timestamps.
