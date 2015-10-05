### April 17th 2009 ###
Given the recent update and how broken this project still is, Im going to move into a different direction. I'll be dropping the filter calls and just allow ordering, indices, and caching results.

---

SQL is not in the mind of a programmer, simpledb aims to simplify the process of creating a small database application. So if your making a small application with about 0-10,000 entries per table, consider simpledb.

===Release Log=== [Past Releases](ReleaseLog.md)
  * 0.6.6
    * Fixed an issue with deleting a row and the key still being visible.
  * 0.6.5
    * Fixed an issue with moving the database folder to another path.
  * 0.6.4
    * Fixed bad results with mixed filters and orders.
  * 0.6.3
    * Fixed key/value of result sets returned by a pure filter. Added ClearCache function
  * 0.6.2
    * Accidently disabled caching, re-enabled.
  * 0.6.1
    * New TmpCache, importing ArraySets, and building FromArray. Also fixed issues with Ordering.
  * 0.5.1
    * Fixed errors with cache.
  * 0.5.0
    * Fixed errors with empty tables.
    * Filters 6x Faster / Ordering - 3.5x Faster.
    * New Index Format, please use "reindex()" function to reindex your current database files if you are updating from 0.4.3
```
include 'lib.simpledb.php';

class User extends SimpleDb 
{
    protected $__indexes = array('username', 'password');
    public $username;
    public $password;
    public $signup;
    public $lastlogin;
}

$user = new User('data');
$user->reindex();
```
    * New Function: reindex()  - for migration / fix broken indexed files Or if your adding a new index.