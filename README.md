# Faasit

## Introduction

Faasit is a DSL and Serverless deployment toolchain. Users can use Faasit DSL to describe the deployment information of Serverless applications, and the Faasit tool will automatically execute deployment, local testing, code generation, and test case generation.

## Problem Analysis

### Requirements Analysis

- There are many Serverless providers, each with its own deployment method. How can a unified deployment description be used to reduce workload?
- How to define the characteristics and essential concepts of Serverless applications in a standardized way?
- Some automated functions (such as code generation and test case generation) require relevant information. How to define this information in a standardized form?
- How to design a DSL language to make deployment information easier to write and parse by automated tools?

### Target Users

- Serverless application development engineers
- Serverless platform operation and maintenance engineers
- Automation tool development engineers

### Shortcomings of YAML

YAML is a well-known data serialization and definition format, widely used in scenarios such as configuration description. Related tools such as Serverless Framework and Serverless Devs use YAML to describe the deployment model of Serverless applications.

However, the shortcomings of the YAML language are:

1. Lack of a standard modular approach, which is not conducive to configuration reuse.
2. It is difficult to describe complex semantic information, such as types and meta-information, without affecting readability and ease of use, which is necessary for the development of automated tools.

### Serverless Application Characteristics

Through research on Tencent Cloud SCF, Alibaba Cloud FC, and OpenFaaS, we have summarized the conceptual model of Serverless, as well as the characteristics of Serverless applications and the concepts that need to be considered during deployment.

## Solution

We propose the Faasit system, including Faasit DSL, Faasit IR, and Faasit toolchain. Use Faasit DSL to describe Serverless application deployment information, and use Faasit tools to automatically perform deployment, local testing, code generation, test case generation and other functions.

The specific solutions are as follows:

- Faasit DSL can describe Serverless deployment information, support external tools to read DSL information, and achieve automation
- Faasit DSL is higher-level than Yaml and JSON, supporting advanced language features such as modules, types, expressions, decorators, and compile-time computation, making it expressive and easy for application developers to write
- The Faasit system supports a plugin mechanism and designs a standardized intermediate object Faasit IR, making it easy for tool developers to develop plugins, obtain DSL meta-information, and develop automation tools
- The Faasit toolchain implements Serverless deployment on different platforms, as well as some higher-level functions.

### Possible Uses of Faasit

- Deploy the same application deployment declaration to different cloud platforms
- Automatically generate Stub code to provide a unified programming model
- Define function deployments with complex relationships, such as data flow processing DAGs
- Set up local simulation environment
- Automatic generation of test cases
- Visualize functions and deployment information
- Static analysis to check whether functions meet certain constraints

## Related Work

- Serverless Framework
- Serverless Devs  
- Terraform

