# Overview

This repository is a part of the Java language training plan. Please read the following guidelines before start.

# Getting Start

## Basic Principals

Each repository contains a gradle java project with a number of unit tests. The initial state of all unit tests are *FAILED*. So the aim is to correct the failed test. Please follow the following steps to get the best experience:

* Read the test code and try to understand what it says.
* Trying to fix the test **WITHOUT RUNNING**. This is very important. Because once you run the test, you may find the failure message of the test telling you the expected result. That means you may lose the chance to figure it out by yourself. Note that you should **ONLY** be able to modify code within the **TODO AREA**. The code outside the **TODO AREA** is **NOT** changable.
* Run the test to examine if the fix is correct.
* Answer the following 4 questions after the test is passed.

The 4 questions are:

1. What is the knowledge point of the test? Where is the offical document to the knowledge point?
1. Why the test failed at first?
1. Why you corrected the test that way?
1. Do you have further questions on this knowledge point?

## Example

Let's take a look at an example:

```java
@Test
void should_pass_by_value() {
  int value = 5;

  tryingToUpdateValue(value);

  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 0;
  // --end-->

  assertEquals(expected, value);
}
```

First, read the test. From the title and code we can know that the test what to examine the behavior when passing an argument. We are not sure what `tryingToUpdateValue` does, so we can jump into its implementation:

```java
private static void tryingToUpdateValue(int value) {
  value += 2;
}
```

Now we have got the full context of the test. The argument is passed by value so the integer will be copied when passing into `tryingToUpdateValue`. Thus the value from the caller site will not change.

Notice that the todo area is in the test method. So we can modify codes within the todo area to pass the test:

```java
  // TODO: please modify the following code to pass the test
  // <--start
  final int expected = 5;
  // --end-->
```

Please note that not all todo areas are located in test method. And some todo area may have further restrictions, for example:

```java
  // TODO: You should not write concrete number here. Please find a property or constant instead.
  // <!--start
  final int maximumSymbol = 0;
  final int minimumSymbol = 0;
  // --end-->
```

The hint indicates that we should not write concrete number here. So I should not write `3` or `0xffffffff`, but write symbol (e.g. `Integer.MAX_VALUE`).

## Running Test

You could run unit tests with the help of IntelliJ. But it is also possible to run unit test via command line: `./gradlew build`.

If you just want to build your code without running test. Please use `./gradlew build -x test
`
****Answer****
Exception Test 
1. should_be_careful_of_the_order_of_finally_block
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to understand finally block 
    Why the test failed at first?
    - The test failed because expectedResult  is null. 
    Why you corrected the test that way?
    - Finally block checks value if the value use in the try block is equal to 2 if its 2 then it will return 0 if it's not the answer in the return value fo the try will be return 
    but since the value 2 is equal in the finally block checking it return 0. 
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 

2. should_use_the_try_pattern 
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - Create object of the class ClosableStateReference then reference it in the object of the class MyClosableType. 
    Why the test failed at first?
    - The test failed because its returning empty Optional.empty(). 
    Why you corrected the test that way?
    - method isClosed() is returning isClosed that's why it's true. 
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 

3. should_call_closing_even_if_exception_throws
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point is to call close method even if it's throwing exception 
    Why the test failed at first?
    - The test failed because its returning null. 
    Why you corrected the test that way?
    - method close() have a throw Exception 
      so since ClosableWithException have the throw that's why it get this return first then follows by ClosableWithoutException
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 
    
3. should_get_method_name_in_stack_frame
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point is to check if the calling method of the class is returning a value. 
    Why the test failed at first?
    - The test failed because expected is not equal in the return of the method. 
    Why you corrected the test that way?
    - I pu t returning value in the method.
    Do you have further questions on this knowledge point?
    - I don’t have further questions.     
    
StackFrameHelper
1. should_get_method_name_in_stack_frame
       What is the knowledge point of the test? Where is the official document to the knowledge point?
       - The knowledge point of the test is to know how to return value. 
      Why the test failed at first?
       - The test failed because expected it's not returning a value. 
       Why you corrected the test that way?
       - To pass to equal the value of the expect. 
       Do you have further questions on this knowledge point?
       - I don’t have further questions.
                     
StringFormatException
1. What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is on how to return the constructor 
 of the superclass with the same parameter String message.  
    Why the test failed at first?
    - The test failed because it returning message. 
    Why you corrected the test that way?
    - Since StringFormatException method calling the constructor of Exception.
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 

2. What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is on how to return the constructor 
 of the superclass with the same parameter String message and Throwable cause.  
    Why the test failed at first?
    - The test failed because it returning message. 
    Why you corrected the test that way?
    - Since StringFormatException method calling the constructor of Exception.
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 

Inheritance Test
1. should_be_derived_from_object_class
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to get the superclass of the class SimpleEmptyClass.
    Why the test failed at first?
    - The test failed because it returning null. 
    Why you corrected the test that way?
    - SimpleEmptyClass have no superclass so it's means it is an object.class. 
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 
    
2. should_call_super_class_constructor
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know inheritance and constructor.
    Why the test failed at first?
    - The test failed because it returning null. 
    Why you corrected the test that way?
    - Since our object have a superclass it will get first the object inside of it then the child object will follows. 
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 
    
3. should_call_super_class_constructor_continued
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know inheritance and constructor with parameter.
    Why the test failed at first?
    - The test failed because it returning null. 
    Why you corrected the test that way?
    - DerivedFromSuperClassWithDefaultConstructor have a parameter int. 
    - This will get first the constructor of the parent since, 
    Then get the child constructor DerivedFromSuperClassWithDefaultConstructor and DerivedFromSuperClassWithDefaultConstructor with parameter. 
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 
    
4. should_call_super_class_constructor_more
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know inheritance and constructor with parameter.
    Why the test failed at first?
    - The test failed because it returning null. 
    Why you corrected the test that way?
    - The instance of the object DerivedFromSuperClassWithDefaultConstructor is have a parameter string. This means it find first the constructor of the parent with string,
    if have it will get the constructor of the child with string to. 
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 
    
5. should_call_most_derived_methods
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know override. 
    Why the test failed at first?
    - The test failed because it returning null. 
    Why you corrected the test that way?
    - It is the returning value of the sub class getName(). 
    Do you have further questions on this knowledge point?
    - I don’t have further questions. 
    
6. should_call_super_class_methods
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know override. 
    Why the test failed at first?
    - The test failed because it returning null. 
    Why you corrected the test that way?
    - Will get first the getName of the super class then concat the value in the child. 
    Do you have further questions on this knowledge point?
    - I don’t have further questions.
    
7. should_use_caution_when_dealing_with_array_type      
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know about array type. 
    Why the test failed at first?
    - The test failed because it returning empty Optional.empty();. 
    Why you corrected the test that way?
    - I corrected it that way to equal the expected and the willthrow value.
    Do you have further questions on this knowledge point?
    - I don’t have further questions.
    
8. should_not_make_you_confused
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know about override. 
    Why the test failed at first?
    - The test failed because it returning null;. 
    Why you corrected the test that way?
    - I corrected it that way because NestedDerivedClassWithName override the return value of the BaseClassWithName. 
    Do you have further questions on this knowledge point?
    - I don’t have further question. 

9. should_not_make_you_confused_2
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know about the return value of the super class. 
    Why the test failed at first?
    - The test failed because it returning null. 
    Why you corrected the test that way?
    - I corrected it that way because NestedDerivedClassWithName have BaseClassWithName that have a returning method.
    Do you have further questions on this knowledge point?
    - I don’t have further question. 

10. should_use_instance_of_to_determine_inheritance_relationship
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know the relationship about inheritance. 
    Why the test failed at first?
    - The test failed because it returning empty Optional.empty();. 
    Why you corrected the test that way?
    - It's all true because is the NestedDerivedClassWithName and DerivedFromBaseClassWithName are the instanceof BaseClassWithName
    Do you have further questions on this knowledge point?
    - I don’t have further question. 
    
11. should_use_instance_of_only_in_inheritance_relationship
    What is the knowledge point of the test? Where is the official document to the knowledge point?
    - The knowledge point of the test is to know the relationship about inheritance. 
    Why the test failed at first?
    - The test failed because it returning empty Optional.empty();. 
    Why you corrected the test that way?
    - Integer is the instance of data type Integer that's why its true. 
    - Integer is not the instance of data type Long that'w why it's false. 
    Do you have further questions on this knowledge point?
    - I don’t have further question. 
    
12. should_write_perfect_equals_1
     What is the knowledge point of the test? Where is the official document to the knowledge point?
     - to know how to instantiate the object of the person and the object of PersonForEqual. 
     Why the test failed at first?
     - The test failed because it throw new NotImplementedException().
     Why you corrected the test that way?
     - I check the logic of the object and PersonForEqual object but before i do that i instantiate first the object to the PersonForEqual it to have the same type. 
     Do you have further questions on this knowledge point?
     - I don’t have further question.    

13. should_write_perfect_equals_2
     What is the knowledge point of the test? Where is the official document to the knowledge point?
     - To compare 2 same object 
     Why the test failed at first?
     - The test failed because it throw new NotImplementedException().
     Why you corrected the test that way?
     - I check the logic of the object and PersonForEqual object but before i do that i instantiate first the object to the PersonForEqual it to have the same type. 
     Do you have further questions on this knowledge point?
     - I don’t have further question.    
 

14. should_write_perfect_equals_3    
     What is the knowledge point of the test? Where is the official document to the knowledge point?
     - To compare 3 same object 
     Why the test failed at first?
     - The test failed because it throw new NotImplementedException().
     Why you corrected the test that way?
     - I check the logic of the object and PersonForEqual object but before i do that i instantiate first the object to the PersonForEqual it to have the same type. 
     Do you have further questions on this knowledge point?
     - I don’t have further question.    
 
     
15. should_write_perfect_equals_4
    What is the knowledge point of the test? Where is the official document to the knowledge point?
     - To know how to check if the parameter pass is null. 
     Why the test failed at first?
     - The test failed because it doesn't have handling for null. 
     Why you corrected the test that way?
     - I put checking if the object pass is null to return false. 
     Do you have further questions on this knowledge point?
     - I don’t have further question.   

16.  should_write_perfect_equals_5
     What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is to know how to compare 2 different object PersonForEquals and Integer. 
      Why the test failed at first?
      - The test failed because it doesn't have handling for null. 
      Why you corrected the test that way?
      - I put checking if the PersonForEquals is not equal to Integer.  
      Do you have further questions on this knowledge point?
      - I don’t have further question.   

17.  should_write_perfect_equals_6
    What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is to know how to compare 2 same object PersonForEquals and PersonForEquals with different parameters value. 
      Why the test failed at first?
      - The test failed because it doesn't have handling for null. 
      Why you corrected the test that way?
      - I put checking if the PersonForEquals property is equal to the comparing object property.  
      Do you have further questions on this knowledge point?
      - I don’t have further question.         

18. should_write_perfect_equals_7
  What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is to know hashcode. 
      Why the test failed at first?
      - The test failed because it doesn't throw. 
      Why you corrected the test that way?
      - I corrected it that way to hashCode() the name and to pass the result. 
      Do you have further questions on this knowledge point?
      - I don’t have further question.   

ObjectTest
1. should_point_to_the_same_object 
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about referencing of object and checking if it is the same object.  
      Why the test failed at first?
      - The test failed because of Optional.empty();
      Why you corrected the test that way?
      - Its comparing the 2 instance of the object that's why its true. 
      Do you have further questions on this knowledge point?
      - I don’t have further question.           

2. should_point_to_different_object
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about comparing 2 different object.  
      Why the test failed at first?
      - The test failed because of Optional.empty();
      Why you corrected the test that way?
      - since goodDay and sameday is not the same it is false. 
      Do you have further questions on this knowledge point?
      - I don’t have further question.              
      
3. should_initialized_to_default_value
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about comparing 2 different object.  
      Why the test failed at first?
      - The test failed because of Optional.empty();
      Why you corrected the test that way?
      - Since the data type is boolean i use Optional.of(true) and and since they have the same object i return true. 
      Do you have further questions on this knowledge point?
      - I don’t have further question.

5. should_initialized_to_default_value
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about having a default value.  
      Why the test failed at first?
      - The test failed because the value of initialized variable is not the same with the Instance object;
      Why you corrected the test that way?
      - I removed the default value of the variable because FieldNotExplicitlyInitialized doesn't instantiate the value of it's returning variable
      making the value as null or 0. For it to correct the output i same the value of the variable in the FieldNotExplicitlyInitialized. 
      Do you have further questions on this knowledge point?
      - I don’t have further question.      

6. should_pass_by_value    
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about pass by value.  
      Why the test failed at first?
      - The test failed because the value is 0. 
      Why you corrected the test that way?
      - I input 5 since there's no return value in tryingToUpdateValue so since the answer in that method is 7 but it didn't 
      return the value the answer will still be 5. 
      Do you have further questions on this knowledge point?
      - I don’t have further question.     

7. should_pass_by_value_continued
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about pass by value and instantiating object in other method.  
      Why the test failed at first?
      - The test failed because the value is 0. 
      Why you corrected the test that way?
      - I use sameReference because it is same with objectReference
      Do you have further questions on this knowledge point?
      - I don’t have further question. 
      
8. should_modify_internal_state    
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about modifying internal state.  
      Why the test failed at first?
      - The test failed because the value is null. 
      Why you corrected the test that way?
      - Initial Name has been updated in tryingToUpdateState using setName(). That's why i input the "Updated Name"
      Do you have further questions on this knowledge point?
      - I don’t have further question 
                   
9. should_choose_method_at_compile_time
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about overloading. Method with same name but different parameters.  
      Why the test failed at first?
      - The test failed because the value is null. 
      Why you corrected the test that way?
      - I corrected it that way because this is overloading even it have the same name but it follows the parameter type. 
      Do you have further questions on this knowledge point?
      - I don’t have further question 

10. should_choose_the_most_specific_overload
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about overloading. Method with same name but different parameters.  
      Why the test failed at first?
      - The test failed because the value is null. 
      Why you corrected the test that way?
      - I corrected it that way because this is overloading even it have the same name but it follows the parameter type. 
      Do you have further questions on this knowledge point?
      - I don’t have further question 
      
11.  should_calling_another_constructor 
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about calling another constructor.   
      Why the test failed at first?
      - The test failed because the value is null. 
      Why you corrected the test that way?
      - I use the returning value of CallingAnotherCtor method. 
      Do you have further questions on this knowledge point?
      - I don’t have further question   
      
12. should_get_initialization_ordering
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - The knowledge point of the test is about initialization ordering.   
      
13. should_get_message_of_var_length_parameters
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - To know the about of the behavior of a string builder when you pass an parameter 
      Why the test failed at first?
      - The test failed because the value is null. 
      Why you corrected the test that way?
      - Logic is it read the value each(1,2,3) and appending on each arg is "\n" that's why it's output is like that. 
      Since this is a for loop and the value was indicated. 
      Do you have further questions on this knowledge point?
      - I don’t have further question   

14. should_get_message_of_var_length_parameters_2
      What is the knowledge point of the test? Where is the official document to the knowledge point?
      - To know the about of the behavior of a string builder when you pass an array 
      Why the test failed at first?
      - The test failed because the value is null. 
      Why you corrected the test that way?
      - Logic is it read the value each(1,2,3) and appending on each arg is "\n" that's why it's output is like that.   
      Do you have further questions on this knowledge point?
      - I don’t have further question   
     
 
                                