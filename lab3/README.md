/notes to self

1st - go to https://start.spring.io/ and declare the dependencies;

use all the imports necessary create 'private final UserRepository userRepository' and it's constructor, aswell as the UserRepository Interface, to serve as middleware;

run: ./mvnw spring-boot:run

//b)

The “UserController” class gets an instance of “userRepository” through its constructor; how is this new repository instantiated? By starting a repository as soon as we instantiate the UserController class;

List the methods invoked in the “userRepository” object by the “UserController”. Where are these methods defined? -userRepository.save(user) -userRepository.findAll() -userRepository.findById(id) -userRepository.delete(user) These methods are defined in CrudRepository;

Where is the data being saved? In the "userRepository" 
repository: userRepository.save(user);

Where is the rule for the “not empty” email address defined? 
In lines 19/20 of the class User.java;

#### Explain the annotations @Table, @Colunm, @Id found in the Employee entity.
-	**@Table**
	-	Allows you to specify the details of the table that will be used to persist the entity in the database.
	-	So when we use `@Table(name = "employees")`, we're basically saying that the entity will be saved on the table "employees" within our MySQL database, allowing the data to persist.

-	**@Column**
	-	Allows you to access a specific column from a table, permitting you to access a specified filed instead of having to access all of them.
	-	So when we use `@Column(name = "first_name", nullable = false)`, we're accessing ONLY the column "first_name" from our "employees" table.

-	**@Id**
	-	Allows you to tag a certain field as being the object's primary key (i.e what identifies it)
	-	So when we use `@Id  @GeneratedValue(strategy = GenerationType.AUTO)`, we're creating an auto-generated primary key for our Employee

#### Explain the use of the annotation @AutoWired

In our project we use the @AutoWired annotation on our **EmployeController** to tag our **EmployeeRepository**'s instance, like so:
```
@Autowired  
private EmployeeRepository employeeRepository;
```
So basically what we're doing is using the @AutoWIred annotation on a property, hence eliminating the need to manually use getters and setters. SpringBoot will look for and inject _employeeRepository_ during the creation of our EmployeeController doing all of that nasty work for us.
