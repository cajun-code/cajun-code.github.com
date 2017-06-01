.. contents::

Erebus
======

Overview
---------

Erebus is a C++ Project management tool written in ruby.  The problem I tend to have with C++ projects is that they are
not set to the way i think.  I wanted a tool to enforce the way i wanted the project to work and use the make system I
understand


Installation
---------------

Install it yourself as:

   $ gem install erebus

Usage
-----------

To see a list of tasks erebus can do:

   erebus

To create a new C++ project:

   erebus project NAME

To create a new C++ project without Tests:

   erebus project NAME --no-testing

To add Igloo Testing to an existing project:

   erebus setup_test .

To create a header file:

    erebus header NAME

To create a C++ source file:

    erebus source NAME

To create a Igloo Test Spec:

    erebus spec <Name of the class to test>

To create a C source file:

    erebus source NAME --ext c

To generate a C++ class:

    erebus cpp_class NAME

To generate a C++ class without Tests:

    erebus cpp_class NAME --no-testing

Source
-------

* Github_

.. _Github: https://github.com/cajun-code/erebus