Creating a database should be, well? Simple!

Include the simpledb file, extend the class, and have a writable folder.

The block below defines a database, but does not create it. A database is not created until something is committed. For more information on **`$__indexes`** read [Indexes](Indexes.md)
```
include_once 'lib.simpledb.php';

class Users extends SimpleDb
{
    protected $__indexes = array('username', 'password', 'active');
    public $username;
    public $password;
    public $lastlogin;
    public $active = true;
}
```

To defind where you want to save the database in the filesystem
```
$db = new Users('database'); // database is the folder name
```

Again not until you commit an entry does the database get created.