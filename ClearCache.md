# clearCache #

clearCache() removes all cached quires for a table. Maybe later on I will allow specific resultset to be cleared but for now it clears them all.

```
class Users extends SimpleDb
{
    protected $__indexes = array('username', 'password', 'active');
    public $username;
    public $password;
    public $lastlogin;
    public $active = true;
}

//-- Add a new entry
$db = new Users('dbfolder');
$db->clearCache();
$indexes = $db->filter('active === true')->query();
foreach($indexes as $idx) {
    $db   = new $dbname(SimpleDb::TMPCACHE);
    $user = $db->fetch($idx);
    echo $idx, ':', $user->username, '<br />';
}
```