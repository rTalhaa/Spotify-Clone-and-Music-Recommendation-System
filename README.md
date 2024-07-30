# Spotify Clone and Music Recommendation System

## Front-End: Spotify Clone
As part of my journey to learn coding, I developed a basic Spotify clone using HTML, CSS, and JavaScript to showcase my skills in front-end web development. This project resulted in a responsive and user-friendly web application that allows users to play music. Key features include:

- **Play/Pause**: Start or pause the playback of the currently selected track.
- **Next/Previous**: Skip to the next or previous track in the playlist or album.
- **Seek**: Manually move forward or backward within a track using a slider or progress bar.
- **Display**: Show the currently playing song and album artwork.

In addition to honing my skills in HTML, CSS, and JavaScript, I also gained experience with version control tools such as Git and GitHub.

## Back-End: Music Recommender System
To complement the front-end project, I built and evaluated a collaborative-filter based recommender system for a music dataset. This project involved:

- **Dataset**: Utilizing the Million Song Dataset (MSD) and the user interaction data from the Million Song Dataset Challenge, which includes play count data for approximately one million users.
- **Model**: Implementing Spark's alternating least squares (ALS) method to learn latent factor representations for users and items, with hyper-parameter tuning for optimal performance.
- **Evaluation**: Measuring model accuracy using mean Average Precision (mAP) on validation and test data, predicting the top 500 items for each user.
- **Infrastructure**: Training the model on the Peel Big Data cluster at NYU High Performance Computing, which includes 18 data nodes running Cloudera CDH version 6.3.4.
- **Baseline Comparison**: Implementing a popularity-based model to serve as a baseline for comparing the performance of the collaborative-filter based model.

These projects demonstrate my ability to integrate front-end and back-end technologies to create comprehensive and functional applications.
