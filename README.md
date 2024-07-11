# Movie Recommendation System

This project is a Movie Recommendation System built using Streamlit. It provides personalized movie recommendations based on a selected movie, utilizing The Movie Database (TMDB) API for fetching movie posters and additional details.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
- [Requirements](#requirements)

## Features

- Select a movie from a predefined list.
- Get a list of recommended movies based on the selected movie.
- View posters of recommended movies.
- User-friendly interface built with Streamlit.

## Installation

To run this project locally, follow these steps:

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/movie-recommendation-system.git
   cd movie-recommendation-system
   ```

2. Install the required dependencies:
   ```sh
   pip install -r requirements.txt
   ```

3. Ensure you have the necessary data files (`movies_list.pkl` and `similarity.pkl`) in the same directory as the script. These files should contain the movie data and similarity matrix, respectively.

4. Set up your TMDB API key:
   - Replace the placeholder API key in the script (`API_KEY = "your_api_key"`) with your actual TMDB API key.

## Usage

Run the Streamlit application:
```sh
streamlit run app.py
```

This will start a local Streamlit server, and you can access the application in your web browser.

## Code Explanation

The main components of the code are explained below:

### Constants and Configuration

```python
API_KEY = "your_api_key"
BASE_URL = "https://api.themoviedb.org/3"
IMAGE_BASE_URL = "https://image.tmdb.org/t/p/w500"
```

- `API_KEY`: Your TMDB API key.
- `BASE_URL`: Base URL for TMDB API requests.
- `IMAGE_BASE_URL`: Base URL for fetching movie posters.

### Data Loading

```python
@st.cache_resource
def load_data():
    # Load movie data and similarity matrix from pickle files
    ...
movies, similarity = load_data()
```

The `load_data` function loads the movie data and similarity matrix from pickle files and caches the data for efficient use.

### Fetching Movie Posters

```python
def fetch_poster(movie_id: int) -> str:
    # Fetch movie poster using TMDB API
    ...
```

The `fetch_poster` function fetches the movie poster URL from the TMDB API.

### Getting Recommendations

```python
def get_recommendations(movie: str) -> Tuple[List[str], List[str]]:
    # Get movie recommendations based on similarity
    ...
```

The `get_recommendations` function generates a list of recommended movies based on the selected movie.

### Displaying Recommendations

```python
def display_recommendations(movie_names: List[str], movie_posters: List[str]):
    # Display movie recommendations in a grid format
    ...
```

The `display_recommendations` function displays the recommended movies and their posters in a grid format using Streamlit columns.

### Main Function

```python
def main():
    st.title("🎬 Movie Recommendation System")
    ...
if __name__ == "__main__":
    main()
```

The `main` function sets up the Streamlit interface, handles user inputs, and displays the recommendations.

## Requirements

- Python 3.6 or higher
- Streamlit
- Pickle
- Requests

Ensure all required dependencies are installed by running `pip install -r requirements.txt`.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgements

- The Movie Database (TMDB) API for providing movie data and posters.
- Streamlit for the interactive web app framework.

Feel free to contribute to this project by opening issues or submitting pull requests. Enjoy exploring and discovering new movies!
