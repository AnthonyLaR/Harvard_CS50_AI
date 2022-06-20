# Degrees

A program that determines how many "degrees of separation" apart two hollywood actors are. Each degree consists of a film that two actors both starred in

## Background

According to the [Six Degrees of Kevin Bacon](https://en.wikipedia.org/wiki/Six_Degrees_of_Kevin_Bacon) game, anyone in the Hollywood film industry can be connected to Kevin Bacon within six steps, where each step consists of finding a film that two actors both starred in

In this problem, we’re interested in finding the shortest path between any two actors by choosing a sequence of movies that connects them. For example, the shortest path between Jennifer Lawrence and Tom Hanks is 2: Jennifer Lawrence is connected to Kevin Bacon by both starring in “X-Men: First Class,” and Kevin Bacon is connected to Tom Hanks by both starring in “Apollo 13”

We can frame this as a search problem: our states are people. Our actions are movies, which take us from one actor to another (it’s true that a movie could take us to multiple different actors, but that’s okay for this problem). Our initial state and goal state are defined by the two people we’re trying to connect. By using breadth-first search, we can find the shortest path from one actor to another

## Files

There are two sets of data, one in _small_ folder and another in _large_ folder. Both contain three csv files, _people.csv_, _movies.csv_ and _stars.csv_. Data in _small_ folder is relatively tiny in size comparing to the data in _large_ folder so it can be used to test the functionality of the program. Whereas in the _large_ folder, all the data from IMDb's database is in the csv files <br/>

- _Movies.csv_ contains information each movie's assigned ID, its title and release year
- _People.csv_ contains information about each hollywood movie star's unique ID, corresponding to their ID in the IMDb's database, with their name and birth year
- _Stars.csv_ establishes a relationship between the movie stars in the _people.csv_ and movies in _movies.csv_, stating that which person starred in which movie

The main program is written in the _degrees.py_ file, which utilizes some useful classes and functions in the _util.py_ file

## How to Use

In the _degrees_ directory, run the _degrees.py_ file. If you are using the large dataset, it will take some time for the data to load in. Then enter the hollywood movie star names as the program prompts, wait a bit for the program to search, and you will see the results

## Example Output

```Python
$ python degrees.py large
Loading data...
Data loaded.
Name: Emma Watson
Name: Jennifer Lawrence
3 degrees of separation.
1: Emma Watson and Brendan Gleeson starred in Harry Potter and the Order of the Phoenix
2: Brendan Gleeson and Michael Fassbender starred in Trespass Against Us
3: Michael Fassbender and Jennifer Lawrence starred in X-Men: First Class
```