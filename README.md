# FireStation


## Background
==============

This is a Jupyter notebook file with an incomplete analysis of the FireStation data found at 
https://data.sfgov.org/Public-Safety/Fire-Department-Calls-for-Service/nuek-vuh3

Currently,the code primarily processes turnout time:  turnout time=enroute time- dispatch time. It looks at relationships between turnout time and the time of day and back-to-back responses. A back to back response is defined by a unit being dispatched within 10 minutes of becoming available since the previous incident. 

## To Run

this project references a folder stored on a local harddrive.  You need to download the file and and change the code to reference the location on your local harddrive.  Alternatively, you could pull directly from the url (using the commented out code), but this can be slow.



## Data Observations and Asumptions
While doing assessing outputs and looking at outliers, I noticed two data anomolies
  1) There are time when the eroute time is earlier then the dispatch time.  
      a) This means that the unit has left for the emergency before being dispatch
      b) I'm not sure if this in an input error or real.  
      c) Currently the data processing does not not include these cases when calculating turnout time.  But, this assumption could lead to erroneous results if there is a corelation between this anomoly and the time of day or back to back responses.
      d)  I would need operationaling information in order to adequately accomodate anomoly into data processing
      
  2) There are times when a Unit is dispatched before it becomes available
      a) This can result in a large turn out time and possibly incorrect identifiaton of back-to-back responses
      b) I have no operational understanding of how this occurs and or how to alter the evaluations of turntime and back-to-back responses
      c) I did not drop of alter values for turntime or the back-to-back response flag when this condition occurred.
      
      
## Evalution of Turnout time
  1) Both the time of day and the presence of back-to-back responses affect turnout tim
      a) the differences are statistically significant but may not be operationally relevant, because the difference is small
      b) turnout time is larger at night 
      c) turnout tim is smaller for back to back responses
   2)  This is an intermediate result.  The two anamolies above should be explored or understood before further cleaning the data and producing a final processing
   
   
 ## Assessment
Looking at the small (albeit statistically significat) changes that time of day and back-ot-back responses have on turnout time, I question the value of focusing on turnout time.  What larger issue of question is analysis of this data trying to address.  An assessment of incident completion rate as a function of incident priority may be more relevant.  A simple simulation or model showing  how changes in conditions (e.g. number of units available, tunrout time, etc) would affect the completion rate, would probably be more valueable than looking for statistically significant differences in different times base upon categorical factors.

Again, I don't trust my turnout time evaluation results, until the two identified anomolies have been further explored to understood.  The way the code handles them could be affecting the results.

  
