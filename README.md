# php-crud 

###Cloned Ian's repository

It's a bit hard to work with an unfinished project, they have a lot of branches and last push was 17 hours ago,
but I will try to comment out on Ian's branch. This

##Controllers:

#Homepage Controller:
<!-- language: php 
class HomepageController
{
    //render function with both $_GET and $_POST vars available if it would be needed.
    public function render(array $GET, array $POST)
    {
        //this is just example code, you can remove the line below
        //creating a new user named John Smith
        $user = new User('John Smith');
        
        $DBLoader = new DatabaseLoader();
        // you should not echo anything inside your controller - only assign vars here
        
        // Models will be responsible for getting the data, for example if you want to get some students from a database:
        // $students = StudentHelper::getAllStudents();
        // The line above this one will use a StudentHelper model that you can make and require in this file
        // the getAllStudents is a static method, which means you can call this function without an instance of your StudentHelper
        // If you want to learn more about static methods -> https://www.w3schools.com/Php/php_oop_static_methods.asp
        
        // then the view will actually display them.

        //load the view
        require 'View/homepage.php';
    }
}
-->

#Teacher Controller:
<-- language: php
declare(strict_types = 1);

class TeacherController
{
//$DBLoader is a property for the class
private DatabaseLoader $DBLoader;

    //constructs the database
    public function __construct($DBLoader)
    {
        $this->DBLoader= new DatabaseLoader();
    }

    //calling the render function to display stuff
    public function render(array $GET, array $POST)
    {
        $sqlTeacherTable= $this->DBLoader->getConnection()->query('SELECT * FROM coaches'); // select all from coaches table
        $teacherArray=[];
        while($row=$sqlTeacherTable->fetch()){
            $teacherArray[]=new Teacher($row[0], $row[1], $row[2]);
        }
        require 'View/teacher.php';
    }
}
-->

