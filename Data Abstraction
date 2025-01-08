// Abstract Base Class: Entity
public abstract class Entity {
    @Override
    public String toString() {
        return "Entity: " + this.getClass().getSimpleName();
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;
        return true;
    }

    @Override
    public int hashCode() {
        return super.hashCode();
    }
}

// Movie Class
public class Movie extends Entity {
    private String title;
    private String genre;
    private int duration; // In minutes

    // Constructor
    public Movie(String title, String genre, int duration) {
        this.title = title;
        this.genre = genre;
        this.duration = duration;
    }

    // Getters and setters
    public String getTitle() {
        return title;
    }

    public void setTitle(String title) {
        this.title = title;
    }

    public String getGenre() {
        return genre;
    }

    public void setGenre(String genre) {
        this.genre = genre;
    }

    public int getDuration() {
        return duration;
    }

    public void setDuration(int duration) {
        this.duration = duration;
    }

    @Override
    public String toString() {
        return "Movie: " + title + " [" + genre + ", " + duration + " mins]";
    }
}

// Viewer Class
public class Viewer extends Entity {
    private String name;
    private String contactInfo;

    // Constructor
    public Viewer(String name, String contactInfo) {
        this.name = name;
        this.contactInfo = contactInfo;
    }

    // Getters and setters
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getContactInfo() {
        return contactInfo;
    }

    public void setContactInfo(String contactInfo) {
        this.contactInfo = contactInfo;
    }

    @Override
    public String toString() {
        return "Viewer: " + name + " (" + contactInfo + ")";
    }
}

// Cinema Class
public class Cinema extends Entity {
    private String name;
    private String location;

    // Constructor
    public Cinema(String name, String location) {
        this.name = name;
        this.location = location;
    }

    // Getters and setters
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getLocation() {
        return location;
    }

    public void setLocation(String location) {
        this.location = location;
    }

    @Override
    public String toString() {
        return "Cinema: " + name + " (" + location + ")";
    }
}

// CinemaUtils Class
import java.util.*;
import java.util.stream.Collectors;

public class CinemaUtils {
    public static List<Movie> filterMoviesByGenre(List<Movie> movies, String genre) {
        return movies.stream()
                     .filter(movie -> movie.getGenre().equalsIgnoreCase(genre))
                     .collect(Collectors.toList());
    }

    public static Movie searchMovieByTitle(List<Movie> movies, String title) {
        return movies.stream()
                     .filter(movie -> movie.getTitle().equalsIgnoreCase(title))
                     .findFirst()
                     .orElse(null);
    }

    public static List<Movie> sortMoviesByDuration(List<Movie> movies) {
        return movies.stream()
                     .sorted(Comparator.comparingInt(Movie::getDuration))
                     .collect(Collectors.toList());
    }
}

// Main Class
import java.util.*;

public class Main {
    public static void main(String[] args) {
        // Create some movies
        Movie movie1 = new Movie("Inception", "Sci-Fi", 148);
        Movie movie2 = new Movie("Titanic", "Romance", 195);
        Movie movie3 = new Movie("Avatar", "Action", 162);

        // Create a viewer
        Viewer viewer = new Viewer("Alice", "alice@example.com");

        // Create a cinema
        Cinema cinema = new Cinema("Galaxy Cinema", "Downtown");

        // Add movies to a list
        List<Movie> movies = Arrays.asList(movie1, movie2, movie3);

        // Test CinemaUtils methods
        System.out.println("Movies sorted by duration:");
        CinemaUtils.sortMoviesByDuration(movies).forEach(System.out::println);

        System.out.println("\nMovies filtered by genre 'Sci-Fi':");
        CinemaUtils.filterMoviesByGenre(movies, "Sci-Fi").forEach(System.out::println);

        System.out.println("\nSearch for movie by title 'Avatar':");
        System.out.println(CinemaUtils.searchMovieByTitle(movies, "Avatar"));

        // Display other entities
        System.out.println("\nViewer Details:");
        System.out.println(viewer);

        System.out.println("\nCinema Details:");
        System.out.println(cinema);
    }
}
