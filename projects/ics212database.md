---
layout: project
type: project
image: img/ics212database/Cprogramming.png
title: "ICS 212 Final C project"
date: 2023-1-18
published: true
labels:
  - C
  - C++
summary: "Final assignment coding assingment for ICS 212, creating a basic data storage system with an user interface"
---

<img width="100px" class="img-fluid" src="../img/ics212database/Cprogramming.png">

## Overview
The final coding assignment in ICS 212, Spring 2023. The project helped me learn how to read and write data into a txt file.

Using a linked list to store information such as their account number, name and address, allowing for a user to interact and add new entries or remove entries in the database. 

When the user is done, the data is saved into a txt file, which will be read upon the next startup of the program.

###

## Difficulties
### Saving data
Writing data to a file

```c
void writefile(struct record* database, char filename[])
{
    struct record* curr_Record = database;
    FILE *file = fopen( filename, "w" );
    
    while (curr_Record != NULL)
    {
        fprintf ( file, "%d\n%s%s;\n", curr_Record->accountno, curr_Record->name, curr_Record->address);
        curr_Record = curr_Record->next;
    }
    fclose(file);
    return;
}
```
Deleting data to prevent memory leaks

```c
void cleanup(struct record** database)
{
    struct record* curr;
    curr = *database;
    while ( curr != NULL )
    {
        struct record * temp;
        temp = curr->next;
        curr->next = NULL;
        free (curr);
        curr = temp;
    }
    return;
}
```
<hr>

### Reading data

Adding data to the linkedlist "database" from a txt file
```c
void writefile(struct record* database, char filename[])
{
    struct record* curr_Record = database;
    FILE *file = fopen( filename, "w" );
    
    while (curr_Record != NULL)
    {
        fprintf ( file, "%d\n%s%s;\n", curr_Record->accountno, curr_Record->name, curr_Record->address);
        curr_Record = curr_Record->next;
    }
    fclose(file);
    return;
}
```
Function to create a linked node
```c
void addRecord(struct record** database, int actnum, char name[], char address[])
{
    struct record* new_Record;
    struct record* prev_Record;
    struct record* curr_Record;
    int done;
    if ( debugMode == 1 )
    {
        printf( "D: addRecord has been called with database** %p, account number %d,\n", database, actnum );
        printf( "the name: %s\n", name );
        printf( "the address: %s\n", address );
    }
    new_Record = (struct record*) malloc( sizeof(struct record) );
    done = -1;

    new_Record->accountno = actnum;
    strncpy( new_Record->name, name, 30 );
    strncpy( new_Record->address, address, 50 );

    if ( *database == NULL )
    {
        new_Record->next = NULL;
        *database = new_Record;
    }
    else if ( actnum < (*database)->accountno )
    {
        new_Record->next = *database;
        *database = new_Record;
    }
    else if (actnum == (*database)->accountno)
    {
        new_Record->next = NULL;
        (*database)->next = new_Record;
    }
    else
    {
        prev_Record = *database;
        curr_Record = (*database)->next;
        while ( done == -1 )
        {
            if ( curr_Record == NULL )
            {
                new_Record->next = NULL;
                prev_Record->next = new_Record;
                done = 0;
            }
            else if ( curr_Record->accountno < actnum )
            {
                prev_Record = curr_Record;
                curr_Record = curr_Record->next;
            }
            else 
            {
                new_Record->next = prev_Record->next;
                prev_Record->next = new_Record;
                done = 0;
            }
        }
    }

    if ( debugMode == 1 )
    {
        printf( "\nD: addRecord finished\n" );
    }
}
```

