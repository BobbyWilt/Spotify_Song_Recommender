# Spotify Song Recommender
This project leverages spotify's api and provided user playlists to create and tune a neural network model that generates song recommendations based off of song data in provided playlists.  The notebook python files can be copied and used by anyone to create their own song-recommender using their song data.

See the model notebook file for instructions on code usage.  As a general requirement, a user will need to have their own spotify account and spotify developer account (detailed steps in notebook).  The development account is free and easy to obtain.

Currently the notebook file will be able to read, process, generate a model, generate song predictions, and visualize song data from user provided playlists.  You can currently use a simple or complex model to generate recommendations or tune your own.  It is highly recommended to create a playlist of songs that you dislike in order to help the model create more accurate song recommendations.  If you do not have one, you can now specify a few music genres that you dislike and a dislike playlist will be created for you.

If you have any questions or encounter any bugs, feel free to email me at: bobbywilt1@gmail.com

Roadmap:
1. Add updated code to github which includes pipeline for creating database, tuning 4 time-series based models and 2 sequential, integrating 6 model outputs into one model, generating recommendations, and output results.  New setup works on local setup only using wsl, but legacy code will be retained.
2. Update readme with visualizations and example playlists
3. Extend code functionaility to Colab
