####  Description:

Most times you require a specific python datetime format string. You might have to get it from a datetime string of a different format. 
It is not always possible to validate if the format that you receive is the same as mentioned previously. 
Some people have the tendency to use multiple dateformats in different places of the same project. 
This even though strictly discouraged, becomes a requirement in certain projects. Here is how to handle them in a better way.

    Requirement : I have the date string that looks like "01/18/2019 12:56:22" that needs to be converted to the format
    "2019-18-01 12:56:22"


### Implementing method one
    
    from datetime import datetime
    
    input_time_string = "01/18/2019 12:56:22"
    input_time_format = "%m/%d/%Y %H:%M:%S"
    output_time_format = "%Y-%m-%d %H:%M:%S"
    input_datetime_obj = datetime.strptime(input_time_string,input_time_format)
    output_time_string = input_datetime_obj.strftime(output_time_format)
    
    print(input_time_string)
    print(output_time_string)
There is a dependancy on the input_time_format for this code to work. In cases where the input time format isn't given or is a constant, you might want to use the method 2.

### Implementing method two

    import dateutil.parser as dp
    from datetime import datetime

    input_time_string = "01/18/2019 12:56:22"
    output_time_format = "%Y-%m-%d %H:%M:%S"
    output_time_string = datetime.strftime(dp.parse(input_time_string), output_time_format)

    print(input_time_string)
    print(output_time_string)

Method two saves you a lot of headache when dealing with inconsistent date format. 

It is always adviced to stick to consistent datetime format throughout though.
