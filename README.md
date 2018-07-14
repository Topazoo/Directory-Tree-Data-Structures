# Python Directory Tree Objects

## Overview:
	The Root object will store the store all files and directories
	(including sub-file and directories) in the same tree structure
	that they are stored in on the operating system. 

## Functionality:
### 	Creation: 
	root = Root()
###		Store Directory:
	root.populate(directory_to_store)
###		Print Directory:
	root.print_contents()
###		Print Directory with Paths:
	root.print_paths()
###		Clear Directory:
	root.clear()
	
## Usage:
### 	Directory:
    Example
    ├── File 1.txt
    └── 1
        └── 2
            ├── 3.1
            │   └── File 2.txt 
            └── 3.2
                └── File 3.txt
				  
###		Example:
``` 
>>> root = Root()
>>> root.populate("Example")
>>> root.print_contents()
Example/
  - File 1.txt
  1/
    2/
      3.1/
        - File 2.txt
      3.2/
        - File 3.txt
```

## Templates for Django:
This object can be used to render directory hierarchies on Django
web applications with the templates provided in /templates/.
	
Render view_hierarchy.html from a view and pass it a Root
object named 'root' to render the directory.

The templates and view will need to reflect the name of the
Django application you are using them for. Replace "YOURAPP"
with the application name.
	
### Example View:
```	
def view_hierarchy(request):
    root = Root()
    root.populate("Example")  
    return render(request, 'YOURAPP/view_hierarchy.html', {'root':root})
```