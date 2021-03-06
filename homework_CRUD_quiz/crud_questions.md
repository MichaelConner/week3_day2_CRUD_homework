# CRUD Quiz

Use the solution to this afternoon's Property Tracker lab to answer the following questions. Please write your answers under each question, push the file to GitHub, and submit in the usual way.

## MVP Questions

In our Property Tracker application:


Q1. Where are we instantiating instances of the `Property` class?

--  Lines 6-11, 15-20 & 24-29 on console.rb.


Q2. Where are we defining the SQL that enables us to save the ruby `Property` object into the database?

--  Lines 18-29 in property.rb.


Q3. In console.rb, which lines modify the database?

--  Line 4 deletes all values from the database.
    Lines 13, 22 and 31 add entries to the database.
    Line 33 deletes an entry from the database.


Q4. Why do we not define the id of a `Property` object at the point we instantiate it (‘new it up’)?

--  The id is not known for certain at this point - it is assigned once the entry is added to the database.


Q5. Where and how do we assign the id (that is generated by the database) to the ruby `Property` object?

--  Line 9 in property.rb


Q6. Why do we put a guard (an `if` clause) on the `@id` attribute in the constructor?

--  The 'if' clause is there to accommodate for when the id value either is not assigned yet, or has not been passed back to Ruby from the database. The 'if' statement allows us to ignore the id value in these circumstances, as it is not yet known.


Q7. Why are some of the CRUD actions represented by instance methods, and others by class methods?

--  Some of the actions only apply to specific instances in our data (i.e. only one property), while others apply to, or require, our whole set of data.


Q8. What type of data structure is returned by calls to `db.exec_prepared()`? In the `save` method, how do we access the id from the returned data structure?

--  An array of hashes. We call the first element of the array using [0] and then the value of the id key using ["id"]


Q9. Why do we use prepared statements when performing database operations?

--  To cleanse data and protect from malicious inputs i.e. SQL Injection attack.


## Extension Questions

Look at the `find_by_id` and `find_by_address` methods in the `Property` class.

Q10. What do they take in as their arguments?

--  The id or address that is being sought.


Q11. What are their return values?

--  Objects of the Property class with values corresponding to the entry that was found in the database.
