#### Symbolic Names and Reserved Words................................................................................................

```
The valid character set for the RPG IV language consists of:
```
- The letters A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
- RPG IV accepts lowercase letters in symbolic names but translates them to uppercase during
    compilation
- The numbers 0 1 2 3 4 5 6 7 8 9
- The characters + - * ,. ' & ⁄ $ # : @ _ > < = ( ) %
- The blank character
**Note:** The $, #, and @ may appear as different symbols on some codepages. For more information, see
the IBM i Information Center globalization topic.

##### Symbolic Names.............................................................................................................................

```
A symbolic name is a name that uniquely identifies a specific entity in a program or procedure. In the RPG
IV language, symbolic names are used for the following:
```
- Arrays (see “Array Names” on page 74)
- Conditional compile names (see “Conditional Compile Names” on page 74)
- Data structures (see “Data Structure Names” on page 74)
- Exception output records (see “EXCEPT Names” on page 74)
- Fields (see “Field Names” on page 74)
- Key field lists (see “KLIST Names” on page 74)
- Labels (see “Labels” on page 74)
- Named constants (see “Named Constants” on page 203)
- Parameter lists (see “PLIST Names” on page 75)
- Prototype names (see “Prototype Names” on page 75)
- Record names (see “Record Names” on page 75)
- Subroutines (see “Subroutine Names” on page 75)
- Tables (see “Table Names” on page 75).
The following rules apply to all symbolic names except for deviations noted in the description of each
symbolic name:
- The first character of the name must be alphabetic. This includes the characters $, #, and @.

```
Symbolic Names
```
© Copyright IBM Corp. 1994, 2021 **73**


- The remaining characters must be alphabetic or numeric. This includes the underscore (_).
- The name must be left-adjusted in the entry on the specification form except in fields which allow the
    name to float (definition specification, keyword fields, and the extended factor 2 field).
- A symbolic name cannot be an RPG IV reserved word.
- A symbolic name can be from 1 to 4096 characters. The practical limits are determined by the size of
    the entry used for defining the name. A name that is up to 15 characters can be specified in the Name
    entry of the definition or procedure specification. For names longer than 15 characters, use a
    continuation specification. For more information, see “About Specifications” on page 303.
- A symbolic name must be unique within the procedure in which it is defined.

###### Array Names..............................................................................................................................

```
The following additional rule applies to array names:
```
- An array name in a standalone field cannot begin with the letters TAB. Array names may begin with TAB
    if they are either prototyped parameters or data structures defined with the DIM keyword.

###### Conditional Compile Names......................................................................................................

```
The symbolic names used for conditional compilation have no relationship to other symbolic names. For
example, if you define a file called MYFILE, you may later use /DEFINE to define condition name MYFILE,
and you may also use /UNDEFINE to remove condition name MYFILE. This has no effect on the file name
MYFILE.
Conditional compile names can be up to 50 characters long.

###### Data Structure Names...............................................................................................................

```
A data structure is an area in storage and is considered to be a character field.
```
###### EXCEPT Names..........................................................................................................................

```
An EXCEPT name is a symbolic name assigned to an exception output record. The following additional
rule applies to EXCEPT names:
```
- The same EXCEPT name can be assigned to more than one output record.

###### Field Names...............................................................................................................................

```
The following additional rules apply to field names:
```
- A field name can be defined more than once if each definition using that name has the same data type,
    the same length, and the same number of decimal positions. All definitions using the same name refer
    to a single field (that is, the same area in storage). However, it can be defined only once on the definition
    specification.
- A field can be defined as a data structure subfield only once unless the data structure is qualified
    (defined with QUALIFIED or LIKEDS). In this case, when the subfield is used, it must be qualified
    (specified in the form _dsname_. _subfieldname_ ).
- A subfield name cannot be specified as the result field on an *ENTRY PLIST parameter.

###### KLIST Names.............................................................................................................................

```
A KLIST name is a symbolic name assigned to a list of key fields.
```
###### Labels.........................................................................................................................................

```
A label is a symbolic name that identifies a specific location in a program (for example, the name assigned
to a TAG or ENDSR operation).
```
```
Symbolic Names
```
