####  Description:

Here is a sample SQL query and two ways of writing the same query as string implementation in python.

    SQL Query : SELECT columnOne,columnTwo,columnThree FROM tableOne WHERE columnOne = '4567'
 In a place where the columnOne value and table name and column names could change, how to write the code in the
 optimal way?


### Implementing method one

    table_name = "tableOne"
    value = 4567
    method_one = "SELECT columnOne,columnTwo,columnThree FROM " + str(table_name) + " WHERE columnOne = '" + str(value) + "'"
    
    print("Method One: " + method_one)
### Implementing method two

    columns = ["columnOne", "columnTwo", "columnThree"]
    tables = ["tableOne"]
    columns = ",".join(columns)
    tables = ",".join(tables)
    method_two = '''SELECT {columns} FROM {tables} WHERE columnOne = '{value}' '''.format(columns=columns, tables=tables,
                                                                                      value=value)
    print("Method Two: " + method_two)

Both the methods print the exact same query and method one takes the shorter number of lines, but debugging a query that looks like method two is going to be easier, and always understand that a code should be readable

