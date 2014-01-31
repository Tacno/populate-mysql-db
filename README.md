Populate Database (Works only for mysql)
=================

This class populate the table in database with random values.
In same cases we need to view an application with data and this class solve this problema.

This is an example:

<code>
<?php
try {

	$pdo = new PDO("mysql:host=localhost;dbname=test;charset=utf8",'root','');

	$populate = new Populate();
	$populate->beginWithLoremIpsum(false); // If you want the text beginning with lorem ipsum
	$populate->setPDO($pdo); // set the PDO class

	$populate->setTable('table_test'); // Set the table to populate
	$populate->setFixValue('image_example','/assets/image/photo.jpg'); // if you want a fix value
	echo $populate->insert(100); // The number of inserts
</code>
