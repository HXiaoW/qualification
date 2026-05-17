LitReview writing: 
~5hour

Setup+ Running Script: 
~4 hour
Most of my time were stucked on trying to correctly run the python script. First I started with following the github readme, but errors about LLM Provider NOT provided. Pass in the LLM provider you are trying to call and incorrect input for model repeatedly showing up--- the LLM provider error requires I specify deepseek/deepseek-v4-flash instead of deepseek-v4-flash, but the incorrect model input tells to only have deepseek-v4-flash. 
At this point I started to ask claude to debug and see what I can do, but soon I realize that it is overcomplicating things and continuously outputting incorrect information that are unecessary---rather than fixing the command line, it is trying to fix the patch behind it. 
Therefore, I stopped using it, and checked my models again, and found out the CellVoyager's repo is using OPENAI_API_KEY for the API key, rather than DEEPSEEK_API_KEY, at the same time ChatGPT suggested me to use deepseek/deepseek-chat, it did run succesfully, but after doing more searching, I saw it is not exactly using the v4 flash version, so I decided to run again with the correct version, and ended up with my final result. I think this is the most intimidating process for this entire project, where minor fix for syntax and details are constantly popping up, but the overall results are good. This part took me around 3 and a half hours. 

Vizualization of Results and markdown file drafting: 
~4 hour
After I started writing the markdown files, I soon realized that although the analysis was shown finished, but I cannot see any results the LLM runs,in the output it only shows the future planning but not the real results or agent interpretation. I have been trying to see what I can do to see the output. 
Starting with running the output notebook from both vscode directly or command line in terminal it all leads to a crash in kernel. 