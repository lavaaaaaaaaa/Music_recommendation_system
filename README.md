Music Recommendation System with Spotify Dataset

A clustering-based song recommendation system powered by Flask API

Overview

This project implements a music recommendation system using the Spotify Dataset where songs are clustered according to their audio features and metadata, and recommendations are provided via a REST API built with Flask.
Users can input a song (or song ID/name) and receive a list of similar tracks based on cluster membership and feature similarity.
Key Features

Uses unsupervised machine-learning (clustering) to group songs with similar audio characteristics.

Built on the Spotify dataset (audio features + metadata) for a more realistic music domain.

Exposes a simple Flask API endpoint(s) for front-end or external integration.

Enables quick retrieval of songs from the same cluster (i.e., “If you like this song, you may like these”).

HTML front-end (index.html) present for demonstration but backend is decoupled.

Tech Stack & Tools

Language: Python

Framework: Flask

Libraries: Pandas, NumPy, Scikit-learn (for clustering)

Dataset: Spotify Tracks Dataset (audio features + metadata)

Web: HTML + JS (simple frontend interface)

Modeling Approach: Clustering (e.g., K-Means or similar) + nearest neighbours logic within clusters.

Project Structure
Music-Recommendation-System-using-Spotify-Dataset/
│
├── app.py                   # Flask API server
├── index.html               # Simple frontend UI (optional)
├── clustered_df.csv         # Preprocessed dataset with cluster labels
├── Untitled.ipynb           # Jupyter notebook for data exploration & modelling
├── README.md                # Project documentation (this file)
└── requirements.txt         # Python dependencies (if present)

How It Works

Data Preparation & Clustering

Load the Spotify dataset containing audio features (tempo, energy, danceability, loudness, etc.).

Preprocess: clean, scale/normalize features.

Apply clustering algorithm to group songs into clusters of similar audio-feature composition.

Export the clustered dataset (clustered_df.csv) with cluster labels.

Recommendation Logic

Given a user’s input song (by name or ID), find its corresponding record and cluster label.

Retrieve other songs from the same cluster (optionally ranked by feature similarity) as recommendations.

Return a list of recommended tracks.

Flask API

app.py runs a Flask server exposing endpoints (e.g., /recommend) for clients to query.

The endpoint takes JSON input (song name or metadata) and returns JSON output (list of recommended songs).

Optionally front-end (index.html) allows UI interaction.
