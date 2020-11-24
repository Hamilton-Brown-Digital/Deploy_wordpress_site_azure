# Six Degrees Azure WordPress

The ```BaltimoreCyberTrustRoot.crt.pem``` resides in the root of the directory. This is required to link a WordPress Azure Web App deployment to a remote Azure MySQL instance.

[wp-config.php](wp-config.php) includes Azure specific references as well as a link to the above certificate:

```
$connectstr_dbhost = getenv('DATABASE_HOST');
$connectstr_dbname = getenv('DATABASE_NAME');
$connectstr_dbusername = getenv('DATABASE_USERNAME');
$connectstr_dbpassword = getenv('DATABASE_PASSWORD');


define('DB_NAME', $connectstr_dbname);

/** MySQL database username */
define('DB_USER', $connectstr_dbusername);

/** MySQL database password */
define('DB_PASSWORD',$connectstr_dbpassword);

/** MySQL hostname */
define('DB_HOST', $connectstr_dbhost);

/** Database Charset to use in creating database tables. */
define( 'DB_CHARSET', 'utf8' );

/** The Database Collate type. Don't change this if in doubt. */
define( 'DB_COLLATE', '' );

/** For MySQL SSL */define('DB_SSL', true);
define('MYSQL_SSL_CA_PATH','BaltimoreCyberTrustRoot.crt.pem');
/*define('MYSQL_SSL_CA', getenv('MYSQL_SSL_CA'));*/
define('MYSQL_CLIENT_FLAGS', MYSQLI_CLIENT_SSL | MYSQLI_CLIENT_SSL_DONT_VERIFY_SERVER_CERT);
```

*Note in the above, the ```getenv``` refers to Application Settings configured in the Web App.*

[wp-db.php](wp-includes/wp-db.php) also contains a reference to the certificate:

```
mysqli_ssl_set($this->dbh, NULL, NULL, ABSPATH . 'BaltimoreCyberTrustRoot.crt.pem', NULL, NULL);
```