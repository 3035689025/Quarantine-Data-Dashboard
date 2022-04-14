## Quarantine-Data-Dashboard

### Vision statement
  For members of the HKSAR Covid Task Force who wish to access an overview of the current quarantine centres easily, the Quarantine Data Dashboard is a webpage that summarises and displays quarantine data, such as availability of quarantine centres and persons quarantined, and check its consistency.

  Unlike the current process to monitor the quarantine situation, members who use the Quarantine Data Dashboard will not need to obtain raw data, nor construct API query strings, then calculate the values manually, which will save them time, allow them to respond to and control the COVID situation in Hong Kong.


### Product Backlog 
#### Story 1 - Checking Availability of Quarantine Centres\
As a member of the COVID task force, I want to see the current availability of quarantine centres so that I can assign people to centres to undergo quarantine without overflowing centres.\

Confirmation:\
-See unoccupied quarantine units available for use, summed across all centres.\
-See quarantine units occupied by persons in quarantine, summed across all centres.\
-See top three centres with highest number of available unoccupied units, highest availability first (listed in decreasing order of availability).\
-See the name and number of unoccupied available units for each centre accordingly.\
-See a warning if no data is available for the past 7 days (8 days including today).\

#### Story 2 - Accessing Data about Persons Quarantined\
As a member of the COVID task force, I want to see the number of persons quarantined and how much of which is "non-close contacts" so that I can assess the potential positive COVID cases in the coming days and monitor the situation in quarantine centres.\

Confirmation:\
-See number of persons quarantined, summed across all centres.\
-See number of persons quarantined who are in the category of "non-close contacts" -See a warning if no data is available for the past 7 days (8 days including today).\
   
#### Story 3 - Verifying Consistency among Datasets\
As a member of the COVID task force, I want to check if the number of persons quarantined is consistent among all datasets, so that I can verify the integrity of our data input, and notify data input workers to re-audit the data in the quarantine centres (if inconsistency exists).\

Confirmation:\
Given data have been entered in both data sets in the past 7 days\
And the data is consistent (i.e. the total number of close contact + non-close contact case = the total number of persons recorded as quarantined across all centres)\
And the data endpoint can be accessed\
When I check the dashboard online\
Then the system displays that the latest data is consistent\

Given data have been entered in both data sets in the past 7 days\
And the data is not consistent (i.e. the total number of close contact + non-close contact case ≠ the total number of persons recorded as quarantined across all centres)\
And the data endpoint can be accessed\
When I check the dashboard online\
Then the system displays a warning that shows the latest data is inconsistent\

Given data have not been entered in both data sets (on the same day) in the past 7 days And the data endpoint can be accessed\
When I check the dashboard online\
Then the system displays a warning that shows no data is available.\
Given the data endpoint cannot be accessed\
When I check the dashboard online\
Then the system displays a warning that shows the endpoint cannot be reached.\
