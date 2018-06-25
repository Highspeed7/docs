---
title: Authenticate Users Using Your Database
connection: custom
image: /media/connections/mysql.svg
description: Learn how to authenticate users using your database as an identity provider.
crews: crew-2
---
# Authenticate Users Using Your Database

If you have your own user database, you can use it as an identity provider in Auth0 to authenticate users.

In this tutorial, you'll learn how to connect your user database to Auth0 and configure it for use as an identity provider. More specifically, you will:

* Create a [database connection](/connections/database) on the [Auth0 dashboard](${manage_url}).
* Make sure that your database has the appropriate fields to store user profiles attributes such as **id**, **nickname**, **email**, and **password**. See [Auth0 Normalized User Profile](/user-profile/normalized) for details on Auth0's user profile schema and the expected fields.
* Provide database action scripts to configure the database for use as an identity provider.

## Before you begin

Here are some things to know before you begin the process of setting up your database for use as an identity provider.

* You'll write your database action scripts in JavaScript. The scripts run in a [Webtask](https://webtask.io/) environment that supports JavaScript and [select Node.js libraries}(https://tehsis.github.io/webtaskio-canirequire/).

* Auth0 provides custom script templates for most of the commonly-used databases, including:

  * ASP.NET Membership Provider
  * MongoDB
  * MySQL
  * Oracle
  * PostgreSQL
  * SQLServer
  * Windows Azure SQL Database
  * Web services accessed via Basic Auth

  Essentially, you can connect to any kind of database or web service with a properly-configured custom script.

* You can use the [auth0-custom-db-testharness library](https://www.npmjs.com/package/auth0-custom-db-testharness) to deploy, execute, and test the output of database action scripts using a Webtask sandbox environment.

* [Update Users Using Your Database](/user-profile/customdb) has information on updating user profile fields.