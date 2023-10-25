# wiki-branches
Python script that takes an Excel document of Wikipedia pages and creates a JSON tree to show the paths taken on


First you need to locate your history file from your browser, roughly here:
C:\Users\USERNAME\AppData\Local\Microsoft\Edge\User_Data\Default should just be called history

Use this tool to actually read the jarbled mess of the history file.
https://inloop.github.io/sqlite-viewer/
This thread is helpful for the following steps:
https://www.reddit.com/r/edge/comments/qyyfus/is_it_possible_for_me_to_export_all_ms_edge/

Select urls in the drop down.
Up the limit from 30 per page to the max urls you have.
SELECT * FROM 'urls' LIMIT 0,30

Carefully copy all those rows into an Excel Macro enabled sheet. 
Separate the columns into excel columns using seperate by space. I think it's called Text to Columns under the Data tab in Excel.
Add coliumn titles and such, matching my History File.
You can also add the actual date calculation but I never used that.
Write a quick VBA script that deletes all rows not containing 'wikipedia'
You may be able to aceses script in History2.xlsm.
Then there is some manual filtering/deleting of rows to be done. For example deleting wiki picture URLs.

Edit my python file a bit to use your excel document file path
Add your known starting page to the line: urlTree = treeClimber('https://en.wikipedia.org/wiki/Drug_policy_of_South_Korea')

Run the python file. It takes a bit. Check and try to minimize unused link length.
Once, you are happy, copy paste json tree into flare-2.json here:
https://vizhub.com/Christian-D2/32e6f8836cac463888b16718c2ee01b7
