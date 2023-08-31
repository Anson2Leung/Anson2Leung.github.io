---
layout: project
type: project
image: img/ics212database/Cprogramming.png
title: "ICS 212 C Final project"
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

This project is in two parts: one in C which was made roughly a few months before, and the other which was to convert our C code to C++.

Using a linked list to store information, allowing for a user to interact and add new entries or remove entries in the linked list data base. 

When the user is done, the data is saved into a txt file, which will be read upon the next startup of the program.

## Challenges
### Saving data
<hr>
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
<hr>
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