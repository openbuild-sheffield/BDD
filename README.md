# BDD

This project contains a Vagrant powered VM built via ansible.  It contains everything you need to build a BDD project with PHP, this includes:

* Nginx - with self signed cert, proxy and webserver
* MySQL server
* PHP-FPM with common extentions and composer

##SpecBDD and TDD

There is no real difference between SpecBDD and TDD. The value of using an xSpec tool instead of a regular xUnit tool for TDD is the language.

##SpecBDD and StoryBDD

StoryBDD tools like Behat help to understand and clarify the domain. They help specify feature narratives, their needs, and what we mean by them. With SpecBDD we are only focused on the how, in other words, the implementation. You are specifying how your classes will achieve those features.

#Getting started - SpecBDD

Build a spec

  ```bin/phpspec describe Openbuild/TestClass```

Run the specs

  ```bin/phpspec run```

Add test method to file spec/Openbuild/TestClassSpec.php

  ```
    function it_should_say_hello_name()
    {
        $this->sayHelloName("Danny")->shouldReturn("Hi, Danny");
    }
  ```

Run the specs

  ```bin/phpspec run```

Should fail and offer to create class/method, accept the offer and complete the method.  Rince repeat.

##Useful links

* [PHP Spec Docs](http://www.phpspec.net/en/stable/manual/introduction.html)

#Getting started - StoryBDD

  ```shell
  BEHAT_PARAMS='{"extensions":{"Behat\\MinkExtension":{"base_url":"http://danny-lewiss-macbook-air.local:8136"}}}' bin/behat --append-snippets --config config/test.yml features/test/
  ```