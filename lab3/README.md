//notes to self

1st - go to https://start.spring.io/ and declare the dependencies;

use all the imports necessary
create 'private final UserRepository userRepository' and it's constructor, aswell as the UserRepository Interface, to serve as middleware;

//b)
- The “UserController” class gets an instance of “userRepository” through its constructor; how is this new repository instantiated?
By starting a repository as soon as we instantiate the UserController class;

- List the methods invoked in the “userRepository” object by the “UserController”. Where are these methods defined?
        -userRepository.save(user)
        -userRepository.findAll()
        -userRepository.findById(id)
        -userRepository.delete(user)
    These methods are defined in CrudRepository;    

- Where is the data being saved?
In the "userRepository" repository: userRepository.save(user);

- Where is the rule for the “not empty” email address defined?
In lines 19/20 of the class User.java;
