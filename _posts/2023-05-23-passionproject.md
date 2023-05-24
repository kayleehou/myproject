<html>
<head>
    <title>Song Recommendation</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
    <h1>Song Recommendation</h1>
    <input type="text" id="songInput" placeholder="Enter a song title">
    <button onclick="recommendSongs()">Recommend</button>
    <div id="recommendations"></div>

<script>
        function recommendSongs() {
            var userInput = document.getElementById("songInput").value;

            // Call the new JavaScript function for song recommendation
            recommendSimilarSongs(userInput);
        }

        function recommendSimilarSongs(title) {
            // Define the features to use for similarity calculation
            var features = ['Beats Per Minute (BPM)', 'Energy', 'Danceability', 'Loudness (dB)', 
                            'Liveness', 'Valence', 'Length (Duration)', 'Acousticness', 'Speechiness'];

            // Fetch the song data from your API
            fetch('http://172.25.189.122:8080/songdatabase')
                .then(response => response.json())
                .then(data => {
                    // Use the fetched song data for recommendation
                    var songData = data;

                    // Find the song with the given title
                    var song = songData.find(song => song.title.toLowerCase() === title.toLowerCase());

                    if (!song) {
                        console.log("The title you entered is not in our database. Try another, or fix spelling");
                        return;
                    }

                    // Calculate the cosine similarity between the given song and all other songs
                    var similarities = songData.map(function (otherSong) {
                        var otherFeatures = features.map(function (feature) {
                            return otherSong[feature];
                        });
                        var songFeatures = features.map(function (feature) {
                            return song[feature];
                        });
                        return cosineSimilarity(otherFeatures, songFeatures);
                    });

                    // Get the indices of the top 5 most similar songs
                    var topIndices = getTopIndices(similarities, 5);

                    // Display the top 5 most similar songs
                    var recommendationsDiv = document.getElementById("recommendations");
                    recommendationsDiv.innerHTML = "<p>Based on the song you like: " + title + ", we recommend these five songs for your new playlist:</p><hr>";
                    for (var i = 0; i < topIndices.length; i++) {
                        var index = topIndices[i];
                        var recommendedSong = songData[index];
                        var songTitle = recommendedSong.title;
                        var songArtist = recommendedSong.artist;
                        var recommendation = document.createElement("p");
                        recommendation.textContent = (i + 1) + ". " + songTitle + " by " + songArtist;
                        recommendationsDiv.appendChild(recommendation);
                    }
                })
                .catch(error => {
                    console.error("Error fetching data:", error);
                });
        }

        function cosineSimilarity(arr1, arr2) {
            var dotProduct = 0;
            var magnitude1 = 0;
            var magnitude2 = 0;
            for (var i = 0; i < arr1.length; i++) {
                dotProduct += arr1[i] * arr2[i];
                magnitude1 += arr1[i] * arr1[i];
                magnitude2 += arr2[i] * arr2[i];
            }
            magnitude1 = Math.sqrt(magnitude1);
            magnitude2 = Math.sqrt(magnitude2);
            return dotProduct / (magnitude1 * magnitude2);
        }

        function getTopIndices(arr, count) {
            var indices = arr.map(function (value, index) {
                return index;
            });
            indices.sort(function (a, b) {
                return arr[b] - arr[a];
            });
            return indices.slice(0, count);
        }
    </script>
</body>
</html>
