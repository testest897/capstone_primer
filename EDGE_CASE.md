# Document your edge case here
- To get marks for this section you will need to explain to your tutor:
1) The edge case you identified
2) How you have accounted for this in your implementation

=========================================================================

1) Upon initialising a new value, there are no checks for whether a student of the same name and course has already been implemented. Assuming that duplicate names will refer to the same individual (as we do not work with unique student identifiers and would be poor design as a result), we should not allow adding duplicate entries of a Student and Course of the same name.

2) In order to check for duplicates, within the /students POST route, I would fetch all students and iterate over them to check for any records matching both the student name and the course code with the request parameters provided. If they appeared, I would return a 400 and exit instead of adding the value to the database.