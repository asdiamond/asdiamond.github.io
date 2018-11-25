# My experience as an intern at CERDEC

During Summer of 2018 I got the opportunity to work at Aberdeen Proving Ground as 
a Software Engineering Intern. I worked in an Agile Environment with 5 group members on
network emulation software that was used daily by a group of 10 analysts at APG. 

## The project
When I came, there were large parts of the codebase that were technically written in Java, but 
were written by a C programmer. All the code was in one class, bad variable names, the 
whole legacy code experience. Unfortunately the project was built around this module, 
and we needed to make it extensible to add some new features. The analysts would load
some options for a simulation into the system, this guy with this radio over here, 
this helicopter over here, etc, and that would be transmitted as a json message into 
this large module of legacy code. The legacy code would then take this message, reconstruct 
this message into a different data format (?) and dispatch it out to workers to carry out parts of the simulation.

## The Solution
I didn't want to just refactor this code and be done with it, I wanted to leave with this project
in a more workable state. To do that, I knew I would need to essentially design the module with
the software's uses in mind. So I asked the team to show me how the software was used, and I followed
around analysts asking what it is they wanted to be able to do. From here I made some class diagrams
and asked the team to verify what entities were present in the system. After long group meetings and
healthy discussion, I feel like we all gained some more understanding of the system.

## ...and more
One of my teams major goals became to redesign this module around using google's [GSON](https://github.com/google/gson).
This would allow us to have the workers share a data model with the rest of the program. 
Further, gson allows you to serialize/deserialize polymorphic data, making the system much more
extensible/generic/better. 
The issue that immediatly arised when adding gson to the project was that it was an external library.
Why was that an issue? 

## ...
Up until this point the project was not using a build system, or a dependency management system.
Everytime somebody wanted to use the system, they would need to import it as a project into
their favorite java IDE, modify the source code to work off some configuration files, add fields,
then compile it and load it up. I was not going to leave with this continuing to be the case, so
I began to migrate the project to [Gradle](https://gradle.org). 

## The end
The migration to Gradle, the redesigning of a legacy code module, the requirements analysis, 
to me, the most important part of was working on something that mattered.
I want to be a software engineer, and I want to be a good one, so working on real code
that had an effect on real peoples lives was amazing. 
