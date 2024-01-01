# Paginate

A quick note on pagination.

```sql
USE StackOverflow2010;

-- SELECT COUNT(*) FROM dbo.Posts;
--  SELECT TOP 1000 * FROM dbo.Posts p ORDER BY p.Id;  -- 65ms
-- SELECT TOP 1000 * FROM dbo.Posts p ORDER BY p.ParentId; -- 20s

-- SELECT * FROM dbo.Posts p ORDER BY p.Id OFFSET 2000 ROWS FETCH NEXT 1000 ROWS ONLY; -- 101ms
-- SELECT * FROM dbo.Posts p ORDER BY p.ParentId OFFSET 2000 ROWS FETCH NEXT 1000 ROWS ONLY;   -- 19s
```

## Readings

- https://sqlperformance.com/2015/01/t-sql-queries/pagination-with-offset-fetch
