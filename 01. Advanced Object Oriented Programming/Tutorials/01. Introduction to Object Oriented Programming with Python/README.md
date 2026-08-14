# Tutorial 01: Introduction to Object-Oriented Programming with Python

## Overview

Modern software systems are expected to manage increasing levels of complexity.

Whether we are building:

-- a library management system,

-- an online store,

-- a banking platform,

-- a hospital management system,

-- or an artificial intelligence application,

we need a way to organize information and behavior in a manner that remains understandable as systems grow.

Object-Oriented Programming (OOP) provides a structured way to model software by representing real-world entities as software objects.

This tutorial introduces the fundamental ideas behind object-oriented thinking and explains how Python supports object-oriented software development.


## Learning Objectives

By completing this tutorial, you should be able to:

-- Understand the motivation behind Object-Oriented Programming.

-- Identify objects in real-world scenarios.

-- Differentiate between attributes and behaviours.

-- Understand classes and objects.

-- Explain the core principles of OOP.

-- Recognize the advantages of object-oriented design.

-- Understand why Python is widely used in modern software development.


## Why Do We Need Object-Oriented Programming?

Imagine you are building software for a furniture store.

The store deals with:

-- Customers

-- Employees

-- Products

-- Orders

-- Payments

A procedural approach might store all information in separate variables:

```
customer_name = "Alamin"
customer_address = "3 Empire St."
customer_budget = 2000
```

This works initially.

However, what happens when we have:

```
1 customer?
10 customers?
10,000 customers?
```

The program quickly becomes difficult to manage.

Software engineers therefore need a way to group related information together and define how that information behaves.

This is where Object-Oriented Programming becomes useful.


## Thinking in Objects

Before learning classes and code, let's learn to think like an object-oriented designer.

Consider yourself.

You have:

### **Attributes**
```
Name
Age
Address
Email
Phone Number
```

and you can perform actions:

### **Behaviours**
```
Study
Walk
Talk
Send Email
Purchase Items
```

In object-oriented terminology:
```
Attributes → Data
Behaviours → Methods
```

## Real-World Example: A Furniture Store ![hypothetical image](https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/blob/main/01.%20Advanced%20Object%20Oriented%20Programming/Images/Gemini_Generated_Image_udupkludupkludup.jpg)
Image Credit: Gemini


Consider the following scenario.

A customer enters a furniture store and asks:

```Can I order this chair?```

A salesperson responds:

```Certainly. The price is $99.```

Immediately we can identify two objects

```
Customer
SalesPerson
```
Each object has information and actions.


### Customer

#### Attributes
```
Name
Address
Budget
```

#### Behaviours
```
Place Order
Browse Products
Make Payment
```

### SalesPerson

#### Attributes
```
Name
Employee ID
Commission
```

#### Behaviours
```
Take Order
Issue Receipt
Update Inventory
```


### Objects Have Identity

Even when two objects belong to the same category, they remain unique.

For example:
```
Customer A
Customer B
```

Both are customers, but they have different values.

| Attribute | Customer A  | Customer B |
| --------- | ----------- | ---------- |
| Name      | Alamin        | Mishu      |
| Address   | Empire St | King St   |
| Budget    | $3000       | $2000      |


The category is the same.

The data is different.


## What Is a Class?

Suppose a software system contains thousands of customers.

Creating each customer from scratch would be inefficient.

Instead, we define a blueprint called a class.

Think about constructing houses.

The blueprint is created once.

Many houses can then be built using that blueprint.

```
Blueprint = Class
Actual House = Object
```

### Illustration ![imaginaryImage](https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/blob/main/01.%20Advanced%20Object%20Oriented%20Programming/Images/Gemini_Generated_Image_tdcps4tdcps4tdcp.jpg)
Credit: Gemini


