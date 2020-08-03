<img height="100px" width="100px" src="https://github.com/benefactor-org/valve/blob/master/valve-logo.png">

# Valve: Sampling and feature release control for better customer experience.

[![][maven img]][maven]
[![][license img]][license]

## Introduction

Valve is a simple to integrate sampling and code flow control library, which can perform sampling on an unknown size of identifiers. It was developed to fullfill the need to perform percentage based roll out of a certain feature for users.

## Full Documentation

See the [Wiki](https://github.com/benefactor-org/valve/wiki/) for java documentation and how to use.


## Communication

- [GitHub Issues](https://github.com/benefactor-org/valve/issues)

## What does it do?

#### 1) Sampling

Given a unique identifier and roll out percentage, decides weather to be sampled or not to be sampled.

#### 2) Feature gates for enabling or disabling a perticular feature.[WIP]

You can configure Valve with all your features at the application start up, and dynamically enable or disable it during runtime.

## How to import?

Add below mentioned dependency to your pom.xml to install using Maven build automation tool.

    <dependency>
      <groupId>com.github.benefactor-org</groupId>
      <artifactId>valve</artifactId>
      <version>1.0.0</version>
    </dependency>

## How to use?

You can perform sampling using any unique identifier. For instance using emailid of users you perform a percent feature roll out.

    ...
    ...
    String email = user.getEmail();                 // Unique identifier.
    int percentEnabled = 25;                        // For how many percent of your user base should the new feature be enabled.
    if(Valve.control(email, percentEnabled)) {
       performNewLogin(user);
    } else {
      performOldLogin(user);
    }
    ...
    ...
 

## Bugs and Feedback

For bugs, questions and discussions please use the [GitHub Issues](https://github.com/benefactor-org/valve/issues).

 
## LICENSE

Copyright 2020 Benefactor, Org.

Licensed under the GNU GENERAL PUBLIC LICENSE Version 3 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

<https://github.com/benefactor-org/valve/blob/master/LICENCE>

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


[maven]:https://search.maven.org/artifact/com.github.benefactor-org/valve/1.0.0/jar"
[maven img]:https://maven-badges.herokuapp.com/maven-central/com.github.benefactor-org/valve/badge.svg

[license]:LICENSE-2.0.txt
[license img]:https://img.shields.io/github/license/benefactor-org/valve
