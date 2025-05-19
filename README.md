# Advanced-java
Write a program using map() method, to convert a list of Strings into uppercase. If the
given List is: Stream names = Stream.of(“abc”, “d”, “ef”);

import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;

public class ConvertToUppercase {

    public static void main(String[] args) {
        // Create a stream of strings
        Stream<String> names = Stream.of("abc", "d", "ef");

        // Convert each string to uppercase using map() and collect to a list
        List<String> upperCaseNames = names
                                        .map(String::toUpperCase)
                                        .collect(Collectors.toList());

        // Print the result
        System.out.println("Uppercase Strings: " + upperCaseNames);
    }
}
2. Write a program to check whether the Strings in the List are empty or not and print the list having non-empty strings. If the given List is: Liststrings Arrays.asList(“abc”, “”, “bc”, “efg”, “abcd”,””, “jkl”);

import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class FilterNonEmptyStrings {

    public static void main(String[] args) {
        // Given list of strings with some empty elements
        List<String> strings = Arrays.asList("abc", "", "bc", "efg", "abcd", "", "jkl");

        // Filter non-empty strings using stream and collect into a new list
        List<String> nonEmptyStrings = strings.stream()
                                              .filter(s -> !s.isEmpty())
                                              .collect(Collectors.toList());

        // Print the result
        System.out.println("Non-Empty Strings: " + nonEmptyStrings);
    }
}
3. You are a teacher in school In your class there are 10 students, you have decided to give special gifts to those students whose names start with “A” you are asked to separate those students with the help of a java program.

Requirement:

Use List interface to store the student name

Use a lambda expression and the Stream API to filter the students

import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class StudentsWithAGift {

    public static void main(String[] args) {
        // List of 10 student names
        List<String> students = Arrays.asList(
            "Amit", "Bhavya", "Anjali", "Raj", "Aryan",
            "Kiran", "Ansh", "Ravi", "Neha", "Arjun"
        );

        // Use Stream API with lambda to filter names starting with "A"
        List<String> aStudents = students.stream()
                                         .filter(name -> name.startsWith("A"))
                                         .collect(Collectors.toList());

        // Print the list of students receiving gifts
        System.out.println("Students receiving gifts: " + aStudents);
    }
}
4. Rajesh has been given a task to create an app which takes the user’s birthdate as input and calculates their age you have to help him to build this app using the java.time.LocalDate class.

Input:

Enter your birthdate (yyyy-mm-dd): 1990–05–15

Output:

Your age is: 33 years, 4 months, and 13 days.

import java.time.LocalDate;
import java.time.Period;
import java.util.Scanner;

public class AgeCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        
        System.out.print("Enter your birthdate (yyyy-mm-dd): ");
        String inputDate = scanner.nextLine();

    
        LocalDate birthDate = LocalDate.parse(inputDate);

        LocalDate currentDate = LocalDate.now();

       
        Period age = Period.between(birthDate, currentDate);

 
        System.out.printf("Your age is: %d years, %d months, and %d days.%n",
                          age.getYears(), age.getMonths(), age.getDays());

        scanner.close();
    }
}


