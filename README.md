<div align="center">

## Filtered Directory Display


</div>

### Description

This Code can be used to display files that reside in a diredtory on your web server. This example uses regular expression to achieve the filter affect, you can set to show only Php file, or every thing but php. The way you use this script is up to you. The Script was commented where i felt it was needed, i hope you like it. Also vote to make me happy :)
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[tehfatal](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/tehfatal.md)
**Level**          |Beginner
**User Rating**    |5.0 (25 globes from 5 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Files](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/files__8-2.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/tehfatal-filtered-directory-display__8-528/archive/master.zip)

### API Declarations

```
http://fatal.pr3p.com
itz_fatal@hotmail.com
```


### Source Code

```
<?php
# To count the files displayed
$count = 0;
# open the directory you want to use
$directory = opendir(".");
# Gather the files, and put them in a array
while( $file = readdir( $directory ) )
{
$file_array[] = $file;
}
# Blockquote used for displaying purposes
echo"<blockquote><br>";
# Tell php if it finds a directory to
# skip over it
foreach( $file_array as $file )
{
if( $file == ".." || $file == "." )
{
continue;
}
# Regular expression statement to only echo
# back files with a .php extendtion
# the '.php$' tells the Regular expression statement to
# only return files with the .php extendion at the end
if( !ereg( ".php$", $file ) )
{
continue;
}
# Display the file with a link
echo"<font face=\"Tahoma\" size=\"2\">• <a href=\"\php/$file\">$file</a></font><br>";
# Count the file that was displayed
$count++;
}
echo"</blockquote>";
# Display Number of files that were displayed
echo"<font face=\"Tahoma\" size=\"2\">There are <b>$count</b> valid Php Files In the Test Directory</font>";
#close thedirectory you used
closedir($directory);
?>
```

