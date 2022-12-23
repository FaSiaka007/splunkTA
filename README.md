# Fastly NGWAF(Next-Gen WAF) TA for Splunk App

This app is a Technology Add-on that collects data from the Next-Gen WAF.
It collects activity data at corp level, site level and from the request feed.

## Fastly NGWAF(Next-Gen WAF) API calls equivalent

1. https://dashboard.signalsciences.net/api/v0/corps/{{corp}}/activity
2. https://dashboard.signalsciences.net/api/v0/corps/{{corp}}/sites/{{site}}/analytics/events
3. https://dashboard.signalsciences.net/api/v0/corps/{{corp}}/sites/{{site}}/feed/requests

## Installation steps 

1. download the tgz file at SplunkBase https://splunkbase.com/xxxxxx
2. Install In Splunk 
3. Configure Indexes related to each API calls or group into one index( a sample indexes.conf name indexes.conf.sample can be found under $SPLUNK_HOME/etc/apps/TA-fastly-ngwaf/local )

## Configuration Steps
1. Click on the app , go to Configuration > Add-on Settings and Enter your email address, console generated API token and Corp name.
   * **Email Address:** This is the username/email address for the NGWAF dashboard ( Required )
   * **API Token:** Required if you are **not using** your password ( Required )
   * **Corp Name** This is your Corp Name short name in your console ( Required )
  
     ![01.Add-on_Settings](screenshots/01.Add-on_Settings.PNG "Enter Global variable names in the Add-on Settings tab")

2. The logging and Account tab are not currently functional ( leave as is)
     ![02.Logging](screenshots/02.Logging.PNG "Leave these tab as is")

3. The proxy function has not been tested so please feel free to send us feedback should you have any
     ![03.Proxy](screenshots/03.Proxy.PNG "Leave these tab as is")

4. Click on "Create New Input"  
     ![04.Inputs](screenshots/04.Inputs.PNG "Click on the Inputs tab")
     
5. Enter the corresponding values in the prompt 
       
      ### Corp activity
      Enter a unique name for the data input , an interval of data polling , choose and index and leave the Delta(Minutes) value as is.
           ![05.corp-activity](screenshots/05.corp-activity.PNG "Fill in the form as indicated above")
      
      
      ### Site activity      
      Enter a unique name for the data input , an interval of data polling( in seconds) , choose an index and a target site to query
           ![06.site-activity](screenshots/06.site-activity.PNG "Fill in the form as indicated above")
    
      ### Requests data      
      Enter a unique name for the data input , an interval of data polling( in seconds) , choose an index and a target site to query
           ![07.requests-data](screenshots/07.requests-data.PNG "Fill in the form as indicated above")    
           
6. If the credential and Input above are correct , you should see your indexes populated as configured in the interval section.
      ### Corp activity
           ![08.corp-activity](screenshots/08.corp-activity.PNG "Corp activity events")
      
      
      ### Site activity      
           ![09.site-activity-search](screenshots/09.site-activity.PNG "Site activity events")
    
      ### Requests data      
           ![10.requests-search](screenshots/10.requests-search.PNG "Requests data")    
