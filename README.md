<div align="center">

## Sort a List of 20 Names


</div>

### Description

The user enters 20 names (or whatever) into an array and the program outputs the 20 inputs alphabetically. The program also stops and sorts what the user has entered so far if the user does not enter anything.
 
### More Info
 
My code only include <iostream.h> and <string.h>. I also did not use the qsort since it doesn't help explain the principal of sorting.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Dfuse](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/dfuse.md)
**Level**          |Beginner
**User Rating**    |3.5 (14 globes from 4 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Sorting](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/sorting__3-24.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/dfuse-sort-a-list-of-20-names__3-976/archive/master.zip)

### API Declarations

```
#include <iostream.h>
#include <string.h>
```


### Source Code

```
/* By Dfuse
http://dfuse.netfirms.com
molsoncanadians@hotmail.com
*/
#include<iostream.h>
#include <string.h>
void getName(char* name)
{ cout<<"Enter a Name: ";
 cin.getline(name, 20, '\n');
 if(strlen(name)==19)
  cin.ignore(100,'\n');
} //getName
readAllNames(char list [] [20])
{ 	int i=0;
	getName(list[i]);
	while((i<19)&&(strlen(list[i])>0))
	{ i++;
	 getName(list[i]);
	} //while
return i+1;
}//readAllNames
void printAll(char list[][20],int c)
{ for (int i=0;i<c;i++)
  cout<<list[i]<<"\n";
} //printAll
void swap(char *s1, char *s2)
{char* temp;
 strcpy(temp,s1);
 strcpy(s1,s2);
 strcpy(s2,temp);
} //swap
sort(char list[][20], int n)
{ int i, smallPos, pass;
  char temp;
  for (pass=0; pass<n; pass++)
  { smallPos = pass;
		for (i=pass; i<n; i++)
			{ if (stricmp (list[i], list[smallPos])< 0)
			 smallPos = i;
			} //for
  swap(list[smallPos], list[pass]);
  } //for
return;
}
main()
{ char names[20][20];
 int count=0;
 count=readAllNames(names);
//cout<<"Count= "<<count<<"\n";
 sort(names,count);
 printAll(names,count);
 return 0;
} //main
```

