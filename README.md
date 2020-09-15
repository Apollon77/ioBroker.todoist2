![Logo](admin/todoist.png)
# ioBroker.todoist2

[![NPM version](http://img.shields.io/npm/v/iobroker.template.svg)](https://www.npmjs.com/package/iobroker.todoist2)
[![Downloads](https://img.shields.io/npm/dm/iobroker.template.svg)](https://www.npmjs.com/package/iobroker.todoist2)
![Number of Installations (latest)](http://iobroker.live/badges/todoist2-installed.svg)
![Number of Installations (stable)](http://iobroker.live/badges/todoist2-stable.svg)
[![Dependency Status](https://img.shields.io/david/rde-master/iobroker.todoist2.svg)](https://david-dm.org/rde-master/iobroker.todoist2)
[![Known Vulnerabilities](https://snyk.io/test/github/rde-master/ioBroker.todoist2/badge.svg)](https://snyk.io/test/github/rde-master/ioBroker.todoist2)

[![NPM](https://nodei.co/npm/iobroker.todoist2.png?downloads=true)](https://nodei.co/npm/iobroker.todoist2/)

**Tests:**: [![Travis-CI](http://img.shields.io/travis/rde-master/ioBroker.todoist2/master.svg)](https://travis-ci.org/rde-master/ioBroker.todoist2.svg?branch=master)

## ioBroker.Todoist

This Adapater is for integrating todoist.
He uses the REST API
https://developer.todoist.com/rest/v1/#overview

Dieser Adaber dient zur zur Integration von todoist.
Er verwendet die Rest API
https://developer.todoist.com/rest/v1/#overview

## Beschreibung

* Adapter liest alle Todolisten aus und legt diese als States an, sodass diese in VIS angezeigt werden können
* Anlage als Text, JSON oder HTML möglich
* Anlage von Projekten, Labels und Sections möglich
* Anlage ist frei Konfigurierbar
* ein "send to" Blockly wurde eingefügt um neue Aufgaben anzulegen
* eine Blacklist steht zur Verfügung
* eine Syncronisierung von Projekten ist möglich
* Todos können per Blockly, sendto, oder per Objekte im Objektbaum angelegt werden
* Alle Funktionen der akutellen Rest API werden unterstützt

* Automatisches Löschen alter Objekte (Beta)


# sendTo
Dieser Adapter verfügt über die Möglichtkeit mit sendTo zu arbeiten:
Hier ist der nötige Ausbau:

 ``` 
 sendTo("todoist2", "send", {
     funktion: {name/string - see below!},
     task: {name/string},
     task_id: {number},
     project: {name/string},
     project_id: {number},
     section: {name/string},
     section_id: {number},
     parent: {number},
     order: {number},
     label: {name/string},
     label_id: {number},
     priority: {number},
     date: JJJJ-MM-TT,
     });
 
```

Hier die Liste der funktion:

 ``` 

add_task --> new Task
del_task --> delete Task
add_project --> new Project
del_project --> delete Project
close_task --> close Task 
reopen_task --> reopen Task
add_section --> new Section
del_section --> delete Section

```


# Blockly
Dieser Adapter fürgt ein Blockly todoist in den Bereich sendTo hinzu:
![Logo](blockly.png)




# Filter
Sie können über die Filter Funktion von Todoist ganz einfach eigene Listen erstellen.
z.B. Filter: "today" gibt alle heute fälligen Todos aus usw...

Wichtig: für diese Funktion ist ein Premium Account bei Todoist nötig! 
Aktiviere diese Funktion nur wenn du einen Premium Account hast.

# Configuration der Listen
## HTML

Example for CSS HTML Table
 ``` 
#task_table {
  font-family: "Trebuchet MS", Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

#task_table td, #task_table th {
  border: 1px solid #ddd;
  padding: 16px;
}

#task_table tr:nth-child(even){background-color: #f2f2f2;}

#task_table tr:hover {background-color: #ddd;}

#task_table th {
  padding-top: 6px;
  padding-bottom: 6px;
  text-align: left;
  background-color: #4CAF50;
  color: white;
}


```

Example for CSS HTML Button
 ``` 
.button {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 8px 16px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
}

```


## Changelog
### 0.7.1
* (rde-master) Bugfix JSON + added Option Naming the HTML Button

### 0.7.0
* (rde-master) added Option to Name all Fields in HTML table and JSON table

### 0.6.7
* (rde-master) Bugfix Prio 

### 0.6.6
* (rde-master) Bugfix

### 0.6.5
* (rde-master) HTML Button added
* (rde-master) closeTask now shows the result immediately

### 0.6.1
* (rde-master) Bugfix

### 0.6.0
* (rde-master) New List Options added

### 0.5.0
* (rde-master) Filter Option added (Premium Todoist needed!!)

### 0.4.0
* (rde-master) Code Cleanup

### 0.3.5
* (rde-master) Translation added

### 0.3.0
* (rde-master) new Backend Structur

### 0.2.0
* (rde-master) added new Sync Projekt option


### 0.1.5
* (rde-master) added new Tasks option
* (rde-master) added beta of remove olt Objects

### 0.1.0
* (rde-master) added Blackist

### 0.0.7
* (rde-master) Update new functions

### 0.0.5
* (rde-master) Update new functions

### 0.0.1
* (rde-master) initial release

## License
The MIT License (MIT)
Copyright (c) 2020 rde-master <info@rde-master.de>


Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
