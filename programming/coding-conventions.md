---
description: >-
  Clean code is something that takes slightly more effort in the present, but
  saves vast amounts of time in the future. Clean code needs to be maintained to
  create beautiful code.
---

# Coding Conventions

## General Conventions

\----------------------------------------------------------------

* There is no official Java convention, so when in doubt, follow the [Google Style Guide](https://google.github.io/styleguide/javaguide.html).
* Class names should follow PascalCase
* Variable names should be descriptive, with no room left for guessing. Long, descriptive names like leftArmMotor are better than short names like motor1.
* In the Commands folder, there should be a folder specifically for autonomous.
* Long lines of code should be broken up into multiple shorter lines.
* Do not have too many Smartdashboard or Shuffleboard messages being updated at once as this is known to slow down the robot significantly.
* If a number is unknown, use 0-9 as a placeholder.
* Add whitespace (blank lines) between chunks of code, e.g.

<figure><img src="https://lh7-us.googleusercontent.com/-P7_qbfZYwo2pJmcgvSbaBCEGyZsPZP9AU00pflc_djiSDDmjIgBy7IDcRZ1Mx0Uw7RDrvEYy9PrZwWapdlInU3POQDLTkYk8m94idaiqrGHz9cZKNKAYKxfUew__k9K447duXkoPqTwRktzHdTOTNU" alt=""><figcaption></figcaption></figure>

## Comments

\----------------------------------------------------------------

* Comment your code! They will be a huge help to someone trying to understand your code in the future.
* Comments should be used to set a description of the function/subsystem you are defining.
* If a variable needs a comment to describe its purpose, that means you need to make the variable name more descriptive.
* To preserve code if something is changed, you can comment out the old code, but try to avoid keeping deprecated code commented out “just in case” you still need it.
* Docstrings should be used to describe what a class or method does. They should be used for every class and almost every method excluding extremely simple ones like getters and setters. For methods, they should include information about the parameters and what is returned.&#x20;
  * To make one, on the line above a class or method, type ”/\*\*”, press enter, and it should automatically create a docstring. Here is an example of what a proper docstring should look like:

<figure><img src="https://lh7-us.googleusercontent.com/vl2wHfSaiWnQU5KlhOhgkMv3wa5PQRB1zceJ8fqOIuum0yb7wcP7MSaA4J9gVJZQYSJhNwuM1lYGeD08gbbAAsvZkWnMJQ3ntNtUwa1iZewaYNnvMdJEvQxa_B1c1wFjUoyEdOTZrdpGZhpwvwaIFL8" alt=""><figcaption></figcaption></figure>

\
\


## Constants

\----------------------------------------------------------------

* A separate class should be made for each subsystem following the name of \<Subsystem>Constants, e.g. DriveConstants for the Drive Subsystem.
* Variables the constants file should be named in UPPERCASE\_SNAKECASE
* Every variable in the constants file should be declared as public static final

\


## Commands

\----------------------------------------------------------------

* Unnecessary/unneeded commands should be deleted.
* In commands, when using subsystems, name the class’ local copy of the subsystem \<subsystem>Subsystem, e.g. driveSubsystem for the Drive Subsystem. Avoid adding the m\_ before names as we don’t do that. Consistency is key.
* Try to make the isFinished method readable and clearly document what is happening in it
* Try to avoid using Instant Commands (unless you are testing) as they decrease readability and if they are needed should be a method present in the subsystem.
  * In the 2022 Loopy code, a mess of chained commands were used for the drive command, don’t do this:\
    \


<figure><img src="https://lh7-us.googleusercontent.com/4gZNgyg8HyWDEbnT4MIJyk92_W_EW6hbpbADlcrQBXWInTyWgSY8bzkq4LgWSoKLLK_X1bCvSR6O5mfTc596mV7XGDeUszMsmiQ-Af7aFfXtbiw_7LgxoDfAXLjeEdmaI3EGIN9vv7IeExkw950ysyc" alt=""><figcaption></figcaption></figure>

## Subsystems

\----------------------------------------------------------------

* A subsystem class should be made for each section of the robot that completes a coherent/meaningful task; a subsystem class should group together multiple parts that work together to accomplish something.
* When there are multiple methods for controlling one part, group them together.
* Do not create more than one copy of a subsystem. The only copy of the subsystem should be created in RobotContainer.java, then passed into every command it is used in.
* If there are two corresponding parts, (one of them is the left part, the other is the right part) group the methods for those parts in left-right pairs rather than grouping all of the left parts together, and all of the right parts together.\
  \


<figure><img src="https://lh7-us.googleusercontent.com/Hv5LuIKi6RGL_fsv493KECPLXuSQVXjkY_s6OjhK-Vdw6_uw9DsI63aNZpdVRk2xlBnWo9RbNOCAHe-i3quFS172Cx_dn-cNAkHwxp-4Grl_FJiJUo5wKLnXXe2_ZTR_BeCTBmgP9hHguJNvwlgI4Ts" alt=""><figcaption></figcaption></figure>

## Robot Container

\----------------------------------------------------------------

* Group button bindings that control the same subsystem.
* Delete excess comments. Over time they really build up and make navigating the code a nightmare.
* Buttons should be created as variables in a group at the top of configureButtonBindings(), and then configured with methods such as .whenPressed() at the bottom. Do not do both of these in one line. E.g.

<figure><img src="https://lh7-us.googleusercontent.com/5ITASxQlorWgUjADbjQ3evvUqaeuKJlGpZP23gdXwodzBw6mcalZOvv9VLZTb8RelSbCIwr0a8rrj50j6Tdd0m1_PcBo4UjyzhcU5H3jwoDagmNa9iTaZ4N9u6czZhX3UY8w_m4mdrHbVVbF8lJJnt8" alt=""><figcaption></figcaption></figure>

* Buttons should be named in ALL CAPS and snake\_case, e.g. BUTTON, or BUTTON\_1.

\
\


## Additional

\----------------------------------------------------------------

* Try to keep our [Github organization](https://github.com/TitaniumTigers4829) clean as it is what other programmers will be looking at.
* The name of the repository for the current season’s robot code should be \<robot name>-robot-code-\<year>, e.g. loopy-robot-code-2022.

Try not to make unnecessary, extra repositories (e.g. AutoClimb-testing). Instead, create a new branch and work on your code there. It is easier to work as a team if all of the code for the robot is in one repository.
