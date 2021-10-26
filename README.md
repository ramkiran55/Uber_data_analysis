# Uber Exploratory Data Analysis

### PROBLEM STATEMENT 1

From the Mapper, we will take the combination of the basement and the day of the week as key and the number of trips as value.

First, we will parse the date, which is in string format into date format using SimpleDateFormat class in Java. Now, to take out the day of the date, we will use the getDay() which will return an integer value with the day of the week’s number. So, we have created an array which consists of all the days from Sunday to Monday and have passed the value returned by getDay() into the array in order to get the day of the week.

Now, after this operation, we have returned the combination of Basement_number+Day of the week as key and the number of trips as value.

Reducer Class:

In the reducer, we will calculate the sum of trips for each basement and for each particular day, by using the below lines of code.


Running the Program:

First, we need to build a jar file for the above program and we need to run it as a normal Hadoop program by passing the input dataset and the output file path as shown below.

hadoop jar uber1.jar /uber /user/output1

In the output file directory, a part of the file is created and contains the output


### PROBLEM STATEMENT 2

From the Mapper, we will take the combination of the basement and the day of the week as key and the number of active vehicles as value.

First, we will parse the date which is in string format to date format using SimpleDateFormat class in Java. Now, to take out the day of the date, we will use the getDay(), which will return an integer value with the day of the week’s number. So, we have created an array which consists of all the days from Sunday to Monday and have passed the value returned by getDay(), into the array in order to get the day of the week.

Now, after this operation, we have returned the combination of Basement_number+Day of the week as key and the number of active vehicles as value.

Reducer Class:

Now, in the reducer, we will calculate the sum of active vehicles for each basement and for each particular day, using the below lines of code.

##### Problem Statement 1

1) Save the uber txt file and script file uber.java on desktop.
2) open nano ~/.bashrc and add the above given java class in the end (export HADOOP_CLASSPATH=$JAVA_HOME/lib/tools.jar) if this class is already exist then no need to add.
2) Make directory in hadoop from below given command.

hadoop fs -mkdir /uber

3) Put the Uber text file in uber directory from below command.

hadoop fs -put Desktop/uber

4) save uber.java script on desktop

5) Complile the code
	1) change drive "cd Desktop/"
	2) hadoop com.sun.tools.javac.main uber.java # this command will create three files 1)uber.class 2)Uber$TokenizerMapper.class 3)Uber$IntSumReducer.class ( If the above command fails then run the below mention command)
	3) source ~/.bashrc # Run the above command to check whether java class has been added correctly
	4) zip all the three files from above given command "jar.cf ub.jar uber*.class --- this command will merge 3 files into one file ub.jar on desktop

6) Exceute

hadoop jar ub.jar uber /uber /uberoutput  ( We have created uberoutput directory on hadoop and output reflects in this directory)
from the above command show the number of splits and Total input paths to process then mapping will done after that reducer.

7) now check for sucess logs created on hadoop or not from above command (hadoop fs -ls /) shows 2 items

8) now run the above command for reducer part ( hadoop fs -cat /uberoutput/*


Same we have to do for Problem Statement 2
