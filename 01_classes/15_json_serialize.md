We often need to map `json` data to our dart classes, so let's learn how to do this in an easy way.

We will create a mock `json` data for a movies list using a dart `map`:

```dart
void main() {
    final moviesJson = [
        {
            "name": "spider-man",
            "rating": 8.5,
        },
        {
            "name": "Frozen",
            "rating": 5.2,
        }
    ];
}
```

Now we need to create a class for the movie:

```dart
class Movie{
    final String name;
    final double rating;
}
```

We create a named constructor:

```dart
class Movie{
    final String name;
    final double rating;
  Movie.fromJson(Map<String, dynamic> json)
      : name = json['name'],
        rating = json['rating'];
}
```

Our map consists of a `key` that is always a `string` and a value that may be a string or a double in our case, thats why our constructor takes a `map` of `string` and `dynamic`, then assigns those values to our class properties.

Now we can map our `jsonMovies` to `Movies` objects using `map`:

```dart
class Movie{
    final String name;
    final double rating;
  Movie.fromJson(Map<String, dynamic> json)
      : name = json['name'],
        rating = json['rating'];
}

void main(){
    final moviesJson = [
        {
            "name": "spider-man",
            "rating": 8.5,
        },
        {
            "name": "Frozen",
            "rating": 5.2,
        }
    ];

  final movies = moviesJson.map((movie)=> Movie.fromJson(movie));
}
```
