# credentials-storage
Credentials Storage on local environment.
(implemetation in progress)

## Intro
If going to use connection to JIRA via RESTFul for example, you need to store credentials somewhere.
The package will keep it safe and make it available for PHP.

```php
$options = array(
    'type' => 'jira',
    'name' => 'my_company',
);
$storage  = AndKirby\CredentialsStorage\Storage($options);
$login    = $storage->getLogin();
$password = $storage->getPassword();
```

## Configuration
Put configuration in file `~/.credstorage/config.xml`:
```xml
<?xml version="1.0"?>
<config>
    <jira>
        [...]
        <my_company>
            <login>my.name</login>
            <password>some.password1</password>
        </my_company>
        [...]
    </jira>
</config>
```
Node `password` will be removed and encripted.
