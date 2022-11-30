# Migration script

Script for migrating md to txt files

```ps
Dir *.md | rename-item -newname {  $_.name  -replace ".md",".txt"  }
Dir *.txt | rename-item -newname {  $_.name  -replace "_","-"  }
Dir *.txt | rename-item -newname {  $_.name  -replace "_","-"  }
get-childitem *.txt | foreach { if ($_.Name -cne $_.Name.ToLower()) { ren $_.FullName $_.Name.ToLower() } }
```