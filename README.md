Populate Database (Works only for mysql)
=================

This class populate the table in database with random values.
In same cases we need to view an application with data and this class solve this problema.

Requirements
-----------

 * PDO
 * PHP >= 5.3

How to usage:
-----------

The class Populate generate random numbers for:
 * int
 * bigint
 * mediumint
 * smallint
 * tinyint
 * float
 * double

and generate texts for
 * varchar
 * text

There is a class to generate Lorem impsum texts.

If you want to change a fix value instead a lorem ipsum generator, you can use the method `->setFixValue('<fieldname>','<valuename>');`.

```php
// Example:
....
$populate->setFixValue('image_field','/assets/image/photo.png');
```

An example
-----------

Paragraphs are separated by a blank line.

```php
try {

	$pdo = new PDO("mysql:host=localhost;dbname=test;charset=utf8",'root','');

	$populate = new Populate();
	$populate->beginWithLoremIpsum(false); // If you want the text beginning with lorem ipsum
	$populate->setPDO($pdo); // set the PDO class

	$populate->setTable('table_test'); // Set the table to populate
	$populate->setFixValue('image_example','/assets/image/photo.jpg'); // if you want a fix value
	echo $populate->insert(100); // The number of inserts
}
catch(Exception $e)
{
	echo $e->getMessage();
}

```

Another Example
-------------

```php

$pdo = new PDO("mysql:host=localhost;dbname=test;charset=utf8",'root','');

$populate = new Populate();
$populate->beginWithLoremIpsum(false); // If you want the text beginning with lorem ipsum
$populate->setPDO($pdo); // set the PDO class

$populate->setTable('table_test'); // Set the table to populate
$populate->setFixValue('image_example','/assets/image/photo.jpg'); // if you want a fix value
echo $populate->clean(); // Truncate the table

```

You can execute via php cli or task.
