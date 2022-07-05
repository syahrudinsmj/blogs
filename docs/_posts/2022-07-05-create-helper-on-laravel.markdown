---
layout: post
title:  "Create Helper On Laravel"
date:   2022-07-05 10:21:44 +0700
categories: laravel
---
## cara pertama
- buat folder dengan nama `Helpers` didalam `app` seperti ini : `app/Helpers`
- kemudian buat file dengan nama sesuai kebutuhan anda sebagai contoh `CustomHelpers.php` dengan isian seperti dibawah ini :
  ```php
  if (! function_exists('helloWorld')) {
    function helloWorld() : string
    {
      return 'Hello World';
    }
  }
  ```
- kemudian tambahkan pada file `composer.json` tepat nya pada `autoload` seperti dibawah ini : 
  ```json
  "files": [
      "app/Helpers/CustomHelpers.php"
  ]
  ```
- kemudian jalan kan perintah `composer dump-autoload`
- kemudian anda dapat menjalankan perintah `helloWorld()` untuk memanggil helper tersebut.

## cara kedua
- buat folder dengan nama `Helpers` didalam `app` seperti ini : `app/Helpers`
- kemudian buat file dengan nama sesuai kebutuhan anda sebagai contoh `CustomHelpers.php` dengan isian seperti dibawah ini :
  ```php
  namespace App\Helpers;
  
  class CustomHelpers {
    public static function helloWorld()
    {
      return 'hello world';
    }
  }
  ```
- kemudian anda dapat menjalankan perintah sebagai berikut :
  ```php
  // didalam controllers :
  use App\Helpers\CustomHelpers;
  ...
  public function test()
  {
    CustomHelpers::helloWorld();
  }

  // didalam blade :
  {{ App\Helpers\CustomHelpers::helloWorld() }};

  ```



