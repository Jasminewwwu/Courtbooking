| Endpoint | Method | Description | Input JSON | Ouput JSON |Possible Error|Scope|
|----------|--------|-------------|------------|------------|--------------|-----|
|/user      |POST    |Create a new user   |firstname,lastname, email, studentNum, password, [phoneNum], [icon]| HTTP Success     |400 User exists or logged in already 500 Failed to create user|all|
|/user/:id  |GET     |Get a user info based on student number     |n/a           |first/last name, email, studentNum, etc|400 If not logged in 500 Failed to find user|all|
|/user/:id  |PUT     |Update user info    |[email], [password], [phoneNum], [icon] |HTTP Success|400 If not logged in or User does not exist 500 Failed to update user|Admin or current user|
|/user/:id  |DELETE  |Delete account      |n/a           |   HTTP Success      |400 User does not exist 500 Failed to delete user|Admin or current user|
|/login          |POST        |Logging in             |studentNum, password             |HTTP Success         |403 Wrong User/Password wrong  |all|
|/index/logout    |GET        |Logout               |n/a            |HTTP Success            |400 If unlogged in |Logged in user|
|/court          |POST        |Create a court         |name,description,location          |HTTP Success            |500 Failed to create court|Admin|
|/court/:id          |GET        |Get a court info based on court id             |n/a            |name,description,location           |400 Not logged in 500 Failed to get the court info|all|
|/court/:id/edit          |GET        |admin page of a court             |n/a            |n/a            |n/a|500 Failed to get the page|
|/court/:id/edit             |PUT        |Update court info             |[name],[description],[location]          |HTTP Success            |500 Failed to update court|Admin|
|/court/:id          |DELETE        |Delete court           |n/a            |HTTP Success              |500 Failed to delete the court|admin|
|/search          |GET        |Seach page             |n/a            |n/a            |500 Failed to search|all|
|/search/?court=xx          |GET       |Seaching             |n/a          |all courts fits the pattern            |500 Failed to Search|all|
|/admin/news          |POST        |Create notification           |[title], [content], [date]    |    n/a   |500 Failed to add news|Admin|
|/user/:id/news          |GET        |Get all news             |      n/a      |     all the news       |500 Failed to get news|owner|
|/user/:id/bookings      |GET        |Get booking history for user |    n/a  |   all the bookings     |500 Failed to get bookings|owner|
|court/:id/comment  |GET  |Get comments of the court  | n/a| all the comments of the court|500 Failed to get comments |owner or Admin|
|court/:id/comment  |POST |make comment of the court  |[firstname], [lastname], [content], [date] | HTTP SUCCESS |500 Failed to make comments|owner or Admin|
|/booking/:id          |GET        |Get all the bookings with a specific student Id  | studentNum        |all the bookings            |500 Failed to get booking |owner|
|booking           |POST        |Book a court             |starttime, endtime,date, courtname           |HTTP Success        |400 If the info is not valid;403 if the court is already booked| 500 Failed to book this court|Logged in user|
|booking/:id       |PUT        |Update booking info             |[date],[starttime],[endtime]            |HTTP Success            |500 Failed to update booking info|Admin or owner|
|booking/:id           |DELETE        |Delete a booking             |n/a           |HTTP Success          |500 Failed to delete the booking|Admin or owner|
|admin/users  |GET  |get all users  |n/a |all users|500 Failed to get all users|Admin|
|admin/users  |PUT  |delete a user |studentNum | HTTP Success|500 Failed to delete the user|Admin|

*square bracket means optional
