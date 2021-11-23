# PHP

[![N|Prince](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

<?php ?>

## What is Php?

---

- php is a server side language

## Print Using Php?

---

> echo ''; -> use for print statement

> print_r(); -> to print in array style

> var_dump() -> to get all info about variable (with Data type)

---

## Comments

---

        // -> for Single line
        /* */ -> Multiline Comments

## Variables

---

        $var = 'Hello World';
        - Rules of variables
                - Prefix $
                - Start with a letter or an underscore
                - Only letters , numbers and underscores
                - Case Sensitive

        Constants
                define('NAME' , 'Value'); -> Not Changeable

---

## Data Types

---

        String ('prince')
        Integers (123)
        Float (1.2 , 1.3)
        Booleans (0/1 , true , false)
        Arrays ([1,2,3])
        Objects
        Null
        Resource

## Types Of Operators

---

    1) Arithmetic Operators : + , - , / , % , ++ , --
    2) Increment Operators : ++
    3) Decrement Operator : --
    4) Assignment Operators : ++ , -- , += , =+ , -= , =- , *= , %= , /=
    5) Relational Operators : > , < , >= , <= , >== , !=
    6) Logical Operators : && , ||
    7) Conditional Operator : == , != , === , < , > , <= , >=
    8) Bitwise Operator : & , | , ~ , ^
    9) Misc operators : ?: , * ,  &

## XML in PHP

---

        Load File : $Variable_Name =  simplexml_load_file('File_Name');

        All xml file is add in variable and yu can use like array

## String Function

---

> substr_replace(); : Replacing Part of String

> implode() : convert string to array

> str_replace() : Replace Some characters of string(Case-insensitive)

> str_split() : splites string into array

> strcmp() : compares two string

> strlen() : to find String Length

## Arrays

---

        Type of Arrays
                - Index
                - Associative
                - Multi-Dimensional (2D,3D)

        Indexed
        ----
                - Define Array
                $people = array('kevin' , 'jerem' , 'prince');
                $num = array(1,2,3);
                $cars = ['honda' , 'toyota' , 'maruti'];

                - Add in Array
                $cars[3] = 'new';
                $cars[] = 'add';

        Associative Arrays
        ----
                $people = array('Brad' => 35 , 'Prince' => 21);
                $id = [22 => 'brade' , 33 => 'Prince'];


        Multi-Dimensional (2D,3D)
        ------
                $cars = array(array('Honda' , 20 , 10),
                              array('Maruti' , 11 , 3) , )
                $people = [['prince' , 22 , 21],
                           ['romik' , 33 , 22]];

        Array UseFull Functions
        ----
                array() => to create array
                count($var); => get length of array
                print_r($var) => print array
                var_dump($var) => all info of array (with data-type)
                array_chunk($var , key) => In Break Array into to parts (Eg : $num = [1,2,3]; array_chunk($num , 2) => [[1,2],[3]] ;)
                array_diff($var1 , $var2) => get Difference between to array
                array_map("Function_Name" , $var) => Map all array and apply function to each tuple
                array_pop($var) => delete last element of tuple
                array_push($var , value1 , value2 ...) => add element in array
                sort() => Sorts an indexed array in ascending order

## Loops

        Type of Loops
                - While Loop
                - Do...While Loop
                - For Loop
                - For Each Loop

        While Loop
        ----
                while(condition){...Content...}
        Do...While Loop
        ----
                do {...Content...}while(condition)
        For Loop
        ----
                for($i = 0 ; $i < 10 ; $i++){...Content...}
        For Each Loop
        ----
                --INDEXED ARRAY----
               foreach($var as $new_name){....content...}

                --ASSOCIATIVE ARRAYS--
                foreach($var as $key => $value ){...Content...}

## Functions

            Function Name Style
              - Camel Case => myFunction()
              - Lower Case => my_function()
              - Pascal Case => MyFunction()

           Define
                function functionName(parameter){
                        --all Code---
                        return
                }
           Call Function :
                functionName(parameter);

## Date and TimeStamp

      time()
      indian_time_zone : date_default_timezone_set("Asia/Calcutta");
      date('D M Y @ H:i:s', $time);
      D : Day , M : Month Name , Y : Year No.
      d : date , m : month no. ,   Y : Year No. Last Two Latter
      H : hour , i : minute , s : second
      A : AM/PM

```sh
$time = time();
$date = date('d m y  @ h:i:s A', $time);
$modify = date('d M Y @ H:i:s', strtotime('-1 Week'));
echo 'the time now is' . $modify;
echo $date;
```

## Session

    start session : session_start();
    set session : $_SESSION['key'] = value ;
    unset any session : unset($_SESSION['key']);
    destroy all session : session_destroy();

## Cookies

    - set Cookies : setcookie('key' , 'value' , time()+YOUR_TIME)
    - After Time End Cookies Automatic Deleted

## File Management

    - W - Write : it is write from start and erase old details
    - A - Append :  it is write at the emd of file and not erase old details
    - R - Read : Read File

<fieldset>
	<legend>File Function</legend> 
	<table>
		<tr><td>Open File</td><td><b>$var = fopen('filename' , 'operation(r,w,a)');</b></td></tr>
		<tr><td>Close File</td><td><b>fclose($var);</b></td></tr>
		<tr><td>Write into File</td><td><b>fwrite($var, 'Text , What you want to add');</b></td></tr>
		<tr><td>Read File</td><td><b>file('fileName');</b></td></tr>
	</table>
</fieldset>

<fieldset>
	<legend>Note</legend> 
	<table>
		<tr><td>If File Not Exist in Directory then Automatically it creates new File </td></tr>
	</table>
</fieldset>

```sh
    //Write in file with Append (if you want to only write then change 'a' with 'w')
    $handle = fopen('temp.txt', 'a');
    $fwrite = fwrite($handle, $text . "\n");
    fclose($handle);

    //Read File : it give in array
    $read = file('temp.txt');
```

<br>

- Check File Exists

```sh

    $fileName = 'tem.txt';
    if (file_exists($fileName)) {
        echo 'File Exists';
    } else {
        $handle = fopen($fileName, 'w');
        fwrite($handle, '');
        fclose($handle);
        echo "New File created";
    }
```

<br>

- Delete File

```sh

    $fileName = 'tem.txt';
    if (@unlink($fileName)) {
        echo 'Your file <strong>' . $fileName . '</strong> has been deleted';
    } else {
        echo 'Your file <strong>' . $fileName . '</strong> Not Found';
    }

```

## Implode & Explode Function

- <b>Explode</b> : It is Used For make string to array<br>
- <b>Implode</b> : It is Used For make array to string

<fieldset>
	<legend>Explode Function</legend> 
	<table>
		<tr><td>$var = explode('brake point' , $string)</td></tr>
	</table>
</fieldset>

<fieldset>
	<legend>Implode Function</legend> 
	<table>
		<tr><td>$var = implode('join_with' , $array)</td></tr>
	</table>
</fieldset>
<br>

## Connect Database and Retrieve Data
<br>

```sh
<?php
$server = 'localhost';
$username = 'root';
$password = '';
$database = 'demo';

@$connect = mysqli_connect($server, $username, $password, $database);

    if (mysqli_connect_errno()) {
        die("<b style=\"color:red;\">Database Connection Not Establish</b>");
    }

    $query = 'SELECT * FROM user';
    $result = mysqli_query($connect, $query);
    $data = mysqli_fetch_all($result, MYSQLI_ASSOC);
    echo '<pre>';
    print_r($data);
    echo '</pre>';
    mysqli_free_result($result);
    mysqli_close($connect);
```
<br>

<fieldset>
	<legend>Basic Query</legend> 
	<table>
		<tr><td><b>SELECT DATA</b></td><td>SELECT * FROM TABLE_NAME ;</td></tr>
		<tr><td><b>INSERT DATA</b></td><td>INSERT INTO TABLE_NAME(ROW_NAME) VALUES (VALUES);</td></tr>
		<tr><td><b>UPDATE DATA</b></td><td>UPDATE TABLE_NAME SET column1=value, column2=value2,... WHERE Condition ;</td></tr>
		<tr><td><b>DELETE DATA</b></td><td>DELETE FROM TABLE_NAME WHERE Condition ;</td></tr>
	</table>
</fieldset>

<br>
<br>

## OOP With Php

- M - Model
- V - View
- C - Controller

![MVC Pattern](https://github.com/PrinceMakavana/PHP_ALL_Info/blob/main/Screenshot_99.png?raw=true)

> class->object->inheritance

## Define Class

        class ClassName {}

## Create Object Of Class

        $var = new ClassName;

## Get All info of Object

        var_dump($object);

## Access Modifiers in php OOP

> - public : this properties or methods are accessible from any were

> - private : this properties or methods are accessible only in class (Also not able to access in inherited class)

> - protected : this properties or methods are accessible only in class and in inherited class

```sh
<?php
class Person
{
    private $first = "Makavana";
    protected $last = "Prince";
    public $age = "28";

    public function owner()
    {
        $a = $this->first;
        return $a;
    }
}

class Pet extends Person //inheritence consept
{
    public function owner()
    {
        $a = $this->last; // if you try to access $first here you get error
        return $a;
    }
}
?>
```

## How to Access Private Properties in Php

- create a public method which access private properties , and you can use it any were out of class

```sh
class Person
{
    private $first = "Makavana";
    public function owner()
    {
        $a = $this->first;
        return $a;
    }
}

```

## Load Classes Automatically

```sh
        <?php
        spl_autoload_register('myAutoLoader');

        function myAutoLoader($className)
        {
            $url = $_SERVER['HTTP_HOST'] . $_SERVER['REQUEST_URI'];
            if (strpos($url, 'includes') !== false) {
                $path = '../classes/';
            } else {
                $path = 'classes/';
            }
            $extension = '.class.php';
            require_once $path . $className . $extension;
        }

```

## Type Declaration in Php

> if you want to get specific type of data method that time "Type Declaration" is come in picture.

```sh
<?php
Class file
        class Person
        {
            // Properties
            public $name;

            //Methods
            public function setName(string $name)
            {
                $this->name = $name;
                return $this->name;
            }
        }

Object File

<?php

declare(strict_types=1);
include Person;

$person1 = new Person;
try {
        echo $person1->setName(2); //It Gives an Error Due to strict_types
    } catch (TypeError $e) {
        echo "Error! : " . $e->getMessage();
    }

?>

```

## Database Connection with OOP

```sh
dbh.class.php
        <?php

        class Dbh
        {
            private $host = "localhost";
            private $username = "root";
            private $password = "";
            private $dbName = "oop_php";

            protected function connect()
            {
                // dsn : data source name
                $dsn = 'mysql:host=' . $this->host . ';dbname=' . $this->dbName;
                $pdo = new PDO($dsn, $this->username, $this->password);
                $pdo->setAttribute(PDO::ATTR_DEFAULT_FETCH_MODE, PDO::FETCH_ASSOC);
                return $pdo;
            }
        }
```

## Sql Query in OOP

```sh
test.class.php
        <?php

        class Test extends Dbh
        {
            public function getUsers()
            {
                $sql = "SELECT * FROM users";
                $stmt = $this->connect()->query($sql);
                while ($row = $stmt->fetch()) {
                    echo $row['f_name'] . '<br>';
                }
            }

            public function getUsersStmt($firstname, $lastname)
            {
                $sql = "SELECT * FROM users WHERE f_name = ? AND l_name = ?";
                $stmt = $this->connect()->prepare($sql);
                $stmt->execute([$firstname, $lastname]);
                $names = $stmt->fetchAll();
                foreach ($names as $name) {
                    echo $name['f_name'];
                }
            }

            public function store($f_name, $l_name, $surname)
            {
                $sql = "INSERT INTO users(f_name , l_name , surname) VALUES (? , ? , ?)";
                $stmt = $this->connect()->prepare($sql);
                $stmt->execute([$f_name, $l_name, $surname]);
            }

            public function destory($column, $value)
            {
                $sql = "DELETE FROM `users` WHERE $column = '$value'";
                $stmt = $this->connect()->prepare($sql);
                $stmt->execute();
            }
        }

```

```sh
index.php
    <?php
    $testObj = new Test();
    $testObj->store('yash', 'parshotambhai', 'vaghela');
    $testObj->destory('surname','vaghela');
    ?>
```
