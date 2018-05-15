# Spotify Recsys Challenge
### Cara Van Uden for COSC 69 in 18S

Spotify is an online music streaming service with over 140 million active users and over 30 million tracks. One of its popular features is the ability to create playlists, and the service currently hosts over 2 billion playlists.

This year's challenge focuses on music recommendation, specifically the challenge of automatic playlist continuation. By suggesting appropriate songs to add to a playlist, a recommender system can increase user engagement by making playlist creation easier, as well as extending listening beyond the end of existing playlists. The goal of the challenge is to develop a system for the task of automatic playlist continuation. Given a set of playlist features, my recommender system should generate a list of recommended tracks that can be added to that playlist to ‘continue’ the playlist.

### Dataset

As part of this challenge, Spotify has released the Million Playlist Dataset. The MPD contains a million user-generated playlists that were created during the period of January 2010 through October 2017. Each playlist in the MPD contains a playlist title, the track list (including track metadata such as artist, album, and track duration) editing information (last edit time, number of playlist edits) and other miscellaneous information about the playlist.

### Questions (besides the obvious challenge of building an effective recommender system!)

What are relevant features in playlist creation? Are there specific NLP features (ie, to do with playlist titles/descriptions or track names) that are especially relevant?

Are there natural patterns that fall out of clustering existing playlists?
* For example, do users tend to have genre-specific playlists (such as rock, rap, classical), or do they have "mood" playlists (happy, sad, studying)?

Are there any interesting interactions between different features of playlists that we can exploit to build a better recommender?

Of personal interest for me, because I tend to edit and re-edit my playlists: is there anything special about highly edited/curated playlists? Are those typically easier to recommend for?

### Previous work

There are two basic methods of music recommendation- metadata information retrieval and collaborative filtering. Metadata information retrieval uses textual metadata (editorial information) supplied by the creators, such as the title of the song, artist name, and lyrics to find some target songs. Though it is fast and accurate, the drawbacks are obvious. First of all, the user has to know about the editorial information for a particular music item. Secondly, it is also time consuming to maintain the increasing metadata. Moreover, the recommendation results is relatively poor, since it can only recommend music based on editorial metadata and none of the users’ information has been considered.

Collaborative filtering is able to recommend items via the choice of other similar users. As one of the most successful approaches in recommendation systems, it assumes that if user X and Y rate n items similarly or have similar behavior, they will rate or act on other items similarly. Instead of calculating the similarity between items, a set of ‘nearest neighbor’ users for each user whose past ratings have the strongest correlation are found. Therefore, scores for the unseen items are predicted based on a combination of the scores known from the nearest neighbors.

For this project, I will use a deep neural net (LSTM) to build my playlist recommendation system. I also plan to do some exploratory anaylses, such as playlist clustering and PCA, to find interesting patterns in these user-generated playlists.

### Citations

https://recsys-challenge.spotify.com/dataset
http://webprojects.eecs.qmul.ac.uk/marcusp/papers/SongDixonPearce-CMMR2012.pdf
