### Documentation ###
  1. [Sample Php & Mysql to Php & SimpleDb](SQLtoPurePhp.md)
  1. [Creating a Database / Table](CreatingTheDatabase.md)
  1. [Creating an Index](Indexes.md)
  1. [Inserting / Updating / Deleting an entry](InsertsAndUpdates.md)
  1. [Filters](Filters.md)
  1. [Ordering Filtered Data](Order.md)
  1. [Joins](Joins.md)
  1. [API Calls](DocFunction.md)

And now some sample code
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

//-- Add a new entry
$users = new Users('dbfolder');
$users->username = 'billy';
$users->password = '123456';
$users->lastlogin = strtotime('NOW');
$userid = $users->commit();

//-- Or add a user via
$users = new Users('dbfolder');
$users->save(array(
    'username'=>'billy',
    'password'=>'123456',
    'lastlogin'=>strtotime('now');
));
$userid = $users->commit();


//-- Query for a user
$username = addslashes($_POST['username']);
$password = addslashes($_POST['password']);
$users = new Users('dbfolder');
$userids = $users
    ->filter("username == '{$username}' and password == {$password}")
    ->query();
$userid = array_shift($userids);
$user = $users->fetch($userid);
echo $user->username;
//-- Outputs: billy

//-- Update the user we just got
$user->lastlogin = strtotime('NOW');
$user->commit();

//-- Delete the same user
$users = new Users('dbfolder');
$users->delete($userid);

```