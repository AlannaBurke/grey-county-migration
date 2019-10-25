This is a custom migration to migrate paragraphs from Drupal 7 to Drupal 8.    

Install the module on your Drupal 8 site.     

You will have to connect your Drupal 8 site to your Drupal 7 site. You'll need
an extra entry in your `settings.php` file that will look something like this:    

```
$databases['grey-county-d7']['default'] = array(
  'driver' => 'pgsql',
  'database' => 'd7',
  'username' => YOURUSERNAME,
  'password' => YOURPASSWORD,
  'host' => 'localhost',
  'prefix' => '',
);
```

Note the key in the databases array - that's what this module is using, it's set
in `config/install/migrate_plus.migration_group.grey-county-d7.yml`.

This module requires Migrate tools and Migrate Plus, which will give you some
great Drush commands. You can find them here: https://www.drupal.org/node/1561820

Another helpful link on how to use the options: https://drushcommands.com/drush-8x/migrate/migrate-import/

The ones you'll use most are `drush mim mymigration` and `drush ms`. 

I've documented the files for each migration. Make sure each field is represented,
 and that each machine name is correct for every paragraph and field.     
 Create all of the paragraphs and fields on your D8 site before running the
  migration using `drush mim`. You can make sure that the module is set up 
  properly by using `drush ms` - it will list all of the current migrations 
  and their status. 