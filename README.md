## SQL Injection (SQLi)

SQL Injection (SQLi) is a web security vulnerability that allows unintended SQL commands to be executed when user input is improperly handled by an application.

It occurs when an application directly includes user-supplied data in SQL queries without proper validation or parameterization.

### Why SQL Injection Happens

Common causes include:

* Dynamic SQL query construction
* Lack of input validation
* Poorly implemented authentication systems
* Improper error handling
* Excessive database permissions

### Example of a Vulnerable Query


SELECT * FROM users
WHERE username = 'user_input';

If user input is directly inserted into a query, the database may interpret that input as part of the SQL command instead of ordinary data.

### Types of SQL Injection

#### Error-Based SQL Injection

Relies on database error messages to reveal information about the backend database.

#### Union-Based SQL Injection

Uses query result combination techniques when a vulnerable application allows additional query results to be returned.

#### Blind SQL Injection

Occurs when the application does not display database errors or query results directly.

#### Time-Based SQL Injection

Uses differences in response timing to infer application behavior.

#### Second-Order SQL Injection

Malicious input is stored by the application and executed later.

### Impact of SQL Injection

A successful SQL Injection vulnerability may allow:

* Unauthorized access to data
* Disclosure of sensitive information
* Modification of database records
* Deletion of data
* Authentication bypass
* Privilege escalation

### Prevention

The most effective defenses include:

* Parameterized Queries
* Prepared Statements
* Input Validation
* Output Encoding
* Least Privilege Database Accounts
* Secure Error Handling

### Secure Query Example

```python
cursor.execute(
    "SELECT * FROM users WHERE username = ?",
    (username,)
)
```

### Learning Resources

* OWASP Top 10
* PortSwigger Web Security Academy
* OWASP Juice Shop
* DVWA (Damn Vulnerable Web Application)

### Disclaimer

This repository is intended for educational purposes, security research, and authorized testing only. Always obtain permission before performing security assessments on any system.

