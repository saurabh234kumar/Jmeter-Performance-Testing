# Amazon-Load-Performance-Testing-Using-jMeter
Apache JMeter is an Apache project that can be used as a load testing tool for analyzing and measuring the performance of a variety of services, with a focus on web applications. Here we used the JMeter tool to test two different ecommerce websites load/performance testing.
Apache JMeter is an Apache project that can be used as a load testing tool for analyzing and measuring the
performance of a variety of services, with a focus on web applications. Here we used the JMeter tool to test
Here we used ecommerce websites Amazon.com for their load testing performance. For the websites we set 100 users thread group with 5 seconds ramp-up time period. Basically, the ramp-up period tells JMeter how long to take to "ramp-up" to the full number of threads chosen. Here 10 threads are used, and the ramp-up period is 5 seconds, then JMeter
will take 5 seconds to get all 100 threads up and running. Each thread will start 25 (100/5) seconds after the previous thread was begun. If there are 30 threads and a ramp-up period of 120 seconds, then each successive thread will be delayed by 4 seconds.
Ramp-up needs to be long enough to avoid too large a work-load at the start of a test, and short enough that the last threads start running before the first ones finish (unless one wants that to happen).

𝑺𝒕𝒂𝒓𝒕 𝒘𝒊𝒕𝒉 𝑹𝒂𝒎𝒑 − 𝒖𝒑 = 𝒏𝒖𝒎𝒃𝒆𝒓 𝒐𝒇 𝒕𝒉𝒓𝒆𝒂𝒅𝒔 𝒂𝒏𝒅 𝒂𝒅𝒋𝒖𝒔𝒕 𝒖𝒑 𝒐𝒓 𝒅𝒐𝒘𝒏 𝒂𝒔 𝒏𝒆𝒆𝒅𝒆𝒅

By default, the thread group is configured to loop once through its elements. For Amazon.com ecommerce
website we test different pages. Homepage, Today's Deals, Cart Page,Category page: Smart Home/Television and SLP: Search listing Page.
Here we use an assertion named response assertion script. We used it because, while testing performance of
websites/ web applications we would want to verify the pages are functioning as expected. But sometimes the
page is too huge for the JMeter test client to download, or sometimes we are not concerned about the contents
of the response page, rather we just want to make sure the page is delivered. So here we used response code
is 200 which means OK.

------------------------------------HTML REPORT----------------------------------
Amazon Home Page: JMeter HTML report generation

Either download htmlReport.zip file from Jmeter-Performance-Testing repositery to view HTML report or follow below steps

Basic steps of creating a JMeter file(.jmx) are as follows:
Step 1: Thread group creation.
Step 2: Sending request (HTTP Request).
Step 3: Viewing the results using Listeners (Results in Tree or Table).
Step 4: Run jmx file into Non GUI mode and generating the HTML reports.
Step 5: Create Tradeling folder in Documents and place Amazon.jmx file over their Ex: - /Users/sk/Documents/Tradeling/ Jmeter-Performance-Testing/Amazon.jmx
Step 6: Create htmlReport folder inside Tradeling folder and make sure folder is empty otherwise you will get error during execution  /Users/sk/Documents/Tradeling/ Jmeter-Performance-Testing/htmlReport
Step 7: Create Result folder inside Tradeling folder and create Book.CSV file but make sure .CSV file is empty /Users/sk/Documents/Tradeling/ Jmeter-Performance-Testing/htmlReport


Approach: to create report at the end of the test
————————————— — — — — — — — —
jmeter -n -t(path of .jmx file) -l(path of examples folder along with name of csv file where you want to keep the results) -e -o(path of output folder where you want to save the results)

Non GUI commands with explanation:
# Jmeter -n : This command tells the command prompt I want to run my Jmeter script in Non GUI mode.
#Jmeter -t : This will pick the Jmeter .jmx file and execute it. Here we give the path of jmx file which is under bin folder by default or could be in other folder.
# Jmeter -l : Here we give the path where we want to save the executed results into .csv format. We give the path of bin/example folder along with the same name of csv file. Better to create a folder named “csv” in bin/example folder to keep separate your csv and html files.
# Jmeter -e : This command is used to convert the .csv results into HTML format at the end of the test.
# Jmeter -g : [path to CSV file] generate report dashboard only.
# Jmeter -o : This command saves the html results into given output folder. Better to create a folder named “html” in bin/example folder to keep separate your csv and html files.

Approach :
To run the command first you have to go to the drive in which you kept the Jmeter. Let’s say I kept my Jmeter in Download folder .
Command: Now go to the bin folder of your Jmeter.
sk@Saurabhs-MBP ~ % cd Downloads/Exe/apache-jmeter-5.3/bin Hit Enter
Now execute the full command.
Command:  sk@Saurabhs-MBP bin % jmeter -n -t /Users/sk/Documents/Tradeling/ Jmeter-Performance-Testing/Amazon.jmx -l /Users/sk/Documents/Tradeling/ Jmeter-Performance-Testing/Result/Book.csv -e -o /Users/sk/Documents/Tradeling/ Jmeter-Performance-Testing/htmlReport

 

Now go to the csv folder and you will find the Book.csv file then go to the htmlReport>(output folder) and you will get there a index.html file which is your required html report.




