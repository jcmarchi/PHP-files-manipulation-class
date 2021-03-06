# PHP Files Class
This package can manipulate files and directories in several ways.


## This package can manipulate files and directories in several ways.

It can perform several types of operations. Currently it can:

1.  Create directory
2.  Generate random string
3.  Change file permission
4.  Copy Files or folders
5.  Move files and folders
6.  Delete files and folders
7.  Upload files with validation
8.  Multiple file upload with validation
9.  read/write files 
## Requirement

- PHP
- Composer

## install
run this command
``` composer require lablnet/files```

## usage

```php
<?php 

use Lablnet\Files;

require_once "../vendor/autoload.php";

$files = new Files();

//Write on file 
$files->open('test.txt','writeOnly')->write("I am test files");

// read the file
var_dump($files->open('test.txt','readOnly')->read('test.txt'));

//delete the file
$files->delete('test.txt');


//Make dir
$files->mkDir('name');

//Change premission
$files->permission('test.txt',0774);

//Delete files
$files->deleteFiles(['test.txt']);

//Copy files
$files->copyFiles('/name','dir/',['test.txt']);

//Move files
$files->moveFiles('/','dir/',['test.txt']);


//Delete dirs
$files->deleteDirs(['test.txt']);

//Copy dirs
$files->copyDirs('/','dir/',['test.txt']);

//Move dirs
$files->moveDirs('/','dir/',['test.txt']);

//File upload
$status = $files->fileUpload($_FILES['file'],'/','image');
var_dump($status);

//Multiple file upload
$status = $files->filesUpload($_FILES['file'],'/','image',count($_FILES['file']['name']));
var_dump($status);


```