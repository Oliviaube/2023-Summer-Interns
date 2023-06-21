# Average Calc

This notebook will take as input a (variable length) list of values from the user.

The following should be calculated and clearly displayed:
- the number of values supplied
- the mean of the values
- the standard deviation of the values

## Functions to Consider
* len(x) - returns the number elements in list *x*
* string.split(separator, maxsplit) - splits a string into a list
	* separator - Specifies the separator to use when splitting the string (optional)
	* maxsplit -  Specifies how many splits to do. Default value is -1, which is "all occurrences" (optional)
* statistics.stdev(x) - returns the standard deviation of the values in *x*, requires `import statistics` prior to using
* Note on *f-string* (`f"text...{variable}"`) vs. *print*(f"text...{variable}"). JupyterLab always prints the result of the last line in the cell, so an *f-string* will print **if** it is the last line in the cell (*See cells 1-4*). If you need to print multiple lines, you will need to use *print*. (*See cell 5.*)
