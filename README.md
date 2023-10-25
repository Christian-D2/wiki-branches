# wiki-branches
Python script that takes an Excel document of Wikipedia pages and creates a JSON tree to show the paths taken on


First you need to locate your history file from your browser
roughly here:
C:\Users\USERNAME\AppData\Local\Microsoft\Edge\User_Data\Default should just be called history

use this tool to actually read the jarbled mess of the history file
https://inloop.github.io/sqlite-viewer/
this thread is helpful
https://www.reddit.com/r/edge/comments/qyyfus/is_it_possible_for_me_to_export_all_ms_edge/

select urls in the drop down
up the limit from 30 per page to the max you have
SELECT * FROM 'urls' LIMIT 0,30

carefully copy all those rows into an Excel Macro enabled sheet. 
separate the columns into excel columns using seperate by space. I think it's called Text to Columns under the data tab in Excel
add titles and such, matching my History File.
you can also add the real date calculation but I never used that
Write a quick VBA script that take out all urls not containing 'wikipedia'
you may be able to use my script in History2.xlsm
then there is some manual filtering to be done

edit my python file a bit to use your excel document file path
add your known starting page to the line: urlTree = treeClimber('https://en.wikipedia.org/wiki/Drug_policy_of_South_Korea')

run the python file. takes a bit
copy paste json tree into 
