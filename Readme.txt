Operation Steps:
1. Input API keys and secrets into .env file
2. Input playlist URI's into .env and pick target playlists.
3. Launch Database_Creation.ipynb and run imports, and environmental variables
4. Run first cell in config and select "create initial basic dataset".  Select balanced weights if you want automatic playlist rating or select custom to pick your own
5. Run Rest of config cells.  Run authorization and function sections
6. Run Playlist links and pick your ratings for your playlists.  Have less liked songs in playlists have a lower rating and more liked songs have a higher rating (ie: dislike -5, ok -3, neutral 0, liked 3, favorite 5)
7. Run create initial dataset
8. re-run Config cell and pick "generate raw td dataset".  Run rest of config cells
9. Run "Generate Raw TD Dataset" section.  Note this section will ingest your spotify api's and will require you to authenticate each api after every 1700 or so songs so keep an eye on it.
10. re-run Config cell and pick "create feature tables"
11. Run all cells in "Create Feature Tables" section 
12. Load "Tuning.ipynb" notebook to start model tuning
13. Run Imports and Environment Variables sections on tuning notebook.
14. Run first cell of config and select your model to tune (genre, general, big_data, or final_lr).  Note you want to have ran genre, general and big_data before running final lr. Run rest of cells in config.  It is recommded to run genre, general and then big_data for 200-500 iterations to get a good model for each.
15. Run the rest of the cell sections
16. Either wait for your model to reach 500 tuning iterations or stop the notebook when you are ready for a break.  The model tuning process will save after each tuning iteration and can be picked up whenever you are ready.
17. Once you have a genre, general, and big_data model tuned then load "Database_Creation.ipynb" notebook
18. Like before, run Imports, Environment Variables, Config.  Select create "final_data_table".  Run rest of cells in config section
19. Run all cells in Create Final Data Table section.
20. Load up "Tuning.ipynb" file again.  Run Imports, Environment Variables sections.
21. Under config select 'final_lr' for your tuning model. Run rest of config cells.  Run Functions, Custom Tuner, Custom Callback, Time Hypermodel, Hypermodel, and Tuner sections.
22. Under Linear Regression Regularization, run all cells.
23. You now have all your models tuned and it's time to generate song recommendations Open "Recommendations.ipynb" notebook file.
24. Run Imports and Environmental Variables sections. Run first cell in Config section.
25. Select "Initial Reocmmend Data Prep" and run rest of cells in config.
26. Run Authorization and Initial Reocommendation Data Prep Sections.
27. Run first cell in config and select "Get Rec Song Ids" and select the number of api's you want to cycle through.  This step is getting the song_id's for recommended songs and spotify api's are needed.  The number of api's sets the number of api's to cycle through.  It is recommended to select 5+ api's to get a good starting dataset. Then run rest of cells in Config section.
28. Run all cells in Get Song Recommendation Ids section
29. Run first cell in Config section and select "Process Recommendations" and number of api's to cycle through.  Each api can get data for 1700 songs and takes about 10 minutes, so pick the number of api's based on how long you can watch the code since each api change needs to be authenticated manually.  Run rest of cells in Config section.
30. Run all cells in Process Song Recommendations.  Check every 10 minutes for spotify api validation to keep the function running and getting data.
31. Once you have a sufficient number of songs processed (20-50k recommended). Select "Populate Playlist" in the first cell of config section.  You can select how you want songs sent your playlist, but selecting top n songs is the simplest. Run rest of cells in config section.
32. Run all cells in Populate Playlist section. If you want more songs in your playlist, just re-run step 31.  If you run out of processed songs, then re-run steps 28-31.
33. You now are done and have songs
 