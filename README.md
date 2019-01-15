Useful resources
================
* https://google.github.io/styleguide/cppguide.html
* http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines



General naming policies
=======================

Filenames with ordering numbers
-------------------------------

* Start numbering with 0.

* Pad numbers with zeros: `001`, not `1`.

* Always increment numbers to avoid naming collisions in repositry history. For
  example, if there are two tests `test_005` and `test_010` in a certain
  module, a newly added test must have name `test_011` and not `test_000` nor
  `test_006`.


Dates
-----

* Dates must always be specified in YYYY-MM-DD order to be sorting-friendly,
  e.g., `2018_10_02`, various delimiters can be used depending on the context.

* Pad months and days with zeros.



General formatting policies
===========================

* Use auto-formatting utilities when possible.

* Configure your text/source editor to drop trailing whitespaces. Lines with
  different number of trailing whitespaces are generally treated as different
  by various diff utilities.

* Use tabulations only when necessary, e.g, in makefiles.

* Formatting of human-readable files should never favor horizontal or vertical
  space preservation over readability: separate logical blocks with multiple
  empty lines and/or comments, add extra linebreaks and whitespaces, etc.



C++ coding style
================

General rules
-------------

### Tabulation

* No tabs should be used. Indentation must include 4 spaces.


### Naming

* Function names, variable names, and filenames should be descriptive; avoid
  abbreviation. Types and variables should be nouns, while functions should
  be "command" verbs.

* Prefixes are usually more apparent than suffixes, so the former is
  preffered in special names, e.g., `g_global_variable` instead of
  `global_variable_g`.


### Other

* Minimize scope of entities -- minimal exposition does not distract with
  non-essential details and provides minimal base for potentially dangerous
  assumptions regarding implementation.

* Be explicit in order to minimize the effort required to understand your code,
  e.g., do not use `auto` type and `using` for namespaces, never use unnamed
  values.



Specific rules
--------------

### Files

* Filenames should be all lowercase and may include underscores `_`.

* Extensions of C++ source and header files should be `.cpp` and `.h`
  respectively.



### Type names

Names of all types -- classes, structs, typedefs, and enums -- have the same
naming convention:

* Type names start with a capital letter and have a capital letter for each new
  word, with no underscores: `MyExcitingClass`, `MyExcitingEnum`.



### Enumerations

* All enumerations must be defined within some container class scope.
* Names of the enumerators should be in upper case with underscores.



### Variables

* Variable names are all lowercase, with underscores between words, i.e.,
  `my_table_name`.

* Global variables must be avoided. If it is not possible, their names must
  have `g_` prefix, e.g., `g_my_global_variable`.



### Functions and methods

* Functions should start with a lowercase letter and have a capital letter for
  each new word without underscores.

* Function names should typically be imperative, i.e., they should be commands:
  `openFile()`.

* Parameters, which do not serve as outputs, must be marked with `const`.

* Output parameters must be gathered in the beginning of the list of
  parameters:
  `doSomething(output1, output2, input1, input2 = <default_value>)`.



### Classes

* It is not allowed to mix definitions with different access modifiers, i.e.,
  methods and members with the same access modifier should be gathered
  together.

* It is recommended to use access modifiers multiple times to visually separate
  members from methods.

* Names of member variables should have trailing underscores, i.e.,
  `member_name_`.

* Methods, which do not change the corresponding class, must always be marked
  with `const`.

* In general, destructors of base classes must be defined and must be
  protected. If it is necessary to allow polymorphic destruction, the
  destructor should be defined as public and virtual.

* Constructors of base classes should be protected as well.



### Macro

* Macro should be avoided when possible.
* Macro name must be in all capitals with underscores.



### Namespaces

* Names of namespaces should be in lower case with possible underscores.


### Templates

* Names of template parameters should follow the same conventions as the
  category they belong to (typenames, variables), but their names must include
  `t_` prefix: `t_BaseClass`.
