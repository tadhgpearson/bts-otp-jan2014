OTP January 2014 Dataset analysis
=================================

Looking at the on-time performance dataset from the US Bureau of Transportation Statistics.
Analysis was conducted using R Studio.


Dataset Summary
---------------
The dataset details 471,949 flights, for the month of Januaray 2014. 

There were more flights on Thursdays and Fridays this month, and less on a Saturday (see day-of-week histogram).
It's sorted by carrier. There are 14 unique carriers, the largest of which is WN, which accounted for 19% share of all traffic.

There are 301 origin airports in the network, of which ATL, DFW, ORD, LAX, DEN and IAH are the busiest. 
ATL (the busiest) accounts for more than twice as much traffic as IAH (the 6th busiest), so we can clearly see the importance of these hubs in their network.

Taking ATL as an example we can see that certain airports are dominated by certain carriers. 
DL accounts for 17,073 flights originating from ATL, about 57% of all traffic to that airport. See atl-carriers plot.
No surprise, ATL is hugely important to Delta's network. Of 59,030 DL flights, 34,142 (57%) of them originated from or terminated in ATL. 

ATL and DL are dependant on each other for success, and we can imagine that geography and the success of a hub airport plays a large role in the success of an airline.

On Time Performance
===================
Some of the flights in the dataset do not have OTP statistics. 
Let's only consider flights where ArrDelayMinutes >= 0 to ensure we're working with clean data. 
This leaves us with 439,620 rows, meaning that we removed 7% of the dataset. 
A cursory analysis shows that this does not impact the major carriers or origin airports, which remain in the same order. 
It does bias against early dates in the month, see the flight-date-dirty and flight-date-clean plot images to indicate how this influenced the composition of the data set.
Cancellations could be a large reason for this.

233,128 (53%) flights in the clean dataset arrived without delay. 
Needless to say, departing on-time correlates highly with arriving on-time, but one flight did recover from a 68 minute departure delay - an error in the dataset perhaps? :)
Airports seemed to be strongly tied to delays, flying from ORD or DEN in January is much more to result in a delayed flight than flight for ATL or LAX.