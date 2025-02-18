---
title: Documentation
description: Learn about Laravel Orchid, the open-source package for accelerating the development of administration-style applications. Explore the documentation for features like permission management, notifications, attachments, form builder, charts, configuration, controllers, custom templates, display elements, form elements, Eloquent filters, global search with Scout, layers for grouping, and using icons and SVG icons in your project.
---

## Introduction to Laravel Orchid

**Laravel Orchid** is a powerful open-source package that simplifies the development and creation of administration-style applications. With its elegant and intuitive interface, developers can quickly implement beautiful and functional interfaces with minimal effort.


Some of the key features of Laravel Orchid include:

- A form builder that eliminates the need to manually describe HTML fields of the same type.
- Screens that provide a comfortable balance between CRUD generation and tedious coding.
- Over 40 different field types to choose from.
- Permissions management that makes it easy to manage user access in development and support.
- Additional features such as menus, charts, notifications, and more.


As a Laravel package, Laravel Orchid seamlessly integrates with other components and can serve as the foundation for applications such as content management systems.


> This documentation is intended for users familiar with the Laravel framework. If you are new to Laravel, it is recommended that you first read through the [Laravel documentation](https://laravel.com/docs/) to gain a better understanding of the framework before using Laravel Orchid.


## What Orchid is not

It is important to note that while Laravel Orchid is a powerful tool for developers, it is not a "turnkey" solution. It is not intended for those with little or no programming experience, as it requires a strong understanding of programming concepts and the ability to work comfortably with complex systems.

## Looking for something simpler?


If you're searching for a more straightforward solution for creating simple applications with minimal coding, Laravel Orchid's **CRUD** feature may be a good fit for you. It offers a straightforward syntax that allows for easy creation of basic applications. To get started, take a look at the [CRUD section](https://orchid.software/en/docs/packages/crud/#introduction) of the documentation.


## Migrating to Laravel Orchid

If you currently have an admin panel based on `Blade` templates, you do not need to entirely rewrite your application in order to use Laravel Orchid. Instead, you can gradually transition to using Orchid by [connecting old controllers](https://orchid.software/en/docs/controllers) and integrating Orchid's features into your existing application. This way, you can take advantage of Orchid's powerful features without having to completely overhaul your existing codebase.


## What sets Laravel Orchid apart from other packages?

The Laravel ecosystem offers a variety of admin panels, such as Nova, Voyager, BackPack, and QuickAdminPanel, that aim to simplify the process of working with CRUD applications. However, Laravel Orchid stands out by offering a different approach to streamlining the development process.

Unlike other packages that rely on scaffolding or visual programming, Laravel Orchid is designed to be helpful at any stage of development and can grow with your application as it becomes more complex. Instead of generating physical stubs files or dragging and dropping objects, Orchid requires developers to write code using a keyboard. And instead of providing a single god class, it offers a range of small, reusable components that can be combined in various ways to build a wide range of applications.

Orchid's approach is designed to be flexible, allowing developers to adapt it to their specific needs and workflows. It can be used for simple CRUD applications, but it also has the capability to handle more complex tasks. 


## What is rapid development?

A classic web application is a subsystem with a common three-tier architecture, which comprises:

- **Presentation level** - a graphical interface presented to the user (browser), including scripts, styles, and other resources.

- **The level of applied logic** - in our cases, this framework is the link where most business logic is concentrated, works with the database (Eloquent), sending resources, and various processing.

- **Level of resource management** - We implement data storage using database management systems (MySQL, PostgreSQL, Microsoft SQL Server, SQLite).

 
![Architecture](/img/scheme/architecture.jpg)

It reduces development time, which is directly related to the distribution of responsibilities between levels. This is especially noticeable when it's necessary to create auxiliary code. At the same time, most of the useful work is done by the application layer.

As various examples of conflicting tasks can be cited:
- Generation of "HTML" using the "Blade" template engine or the "Vue" framework.
- Use of ORM or stored procedures.

Depending on the choice of decisions, responsibilities are assigned, each decision having both advantages and disadvantages.

Similarly, the platform assigns new responsibilities to the application layer for managing the mapping and bridging of data.

```php
Classic          |   Orchid
├── Route        |   ├── Route   
├── Model        |   ├── Model 
├── Controller   |   └── Screen
└── View         |
    ├── HTML     |
    ├── CSS      |
    └── JS       |
```



## Is something wrong?

If you find that something is missing or unclear in our documentation, we welcome contributions to improve it. You can click on the **Suggest Edits** link on the top right side of any documentation page to suggest changes.

