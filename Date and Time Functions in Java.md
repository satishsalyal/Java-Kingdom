# Date and Time Functions in Java

- Java provides the **Date** class available in **java.util** package, this class encapsulates the current date and time. 
- Java Dates are LocalDate, Represents a date (year, month, day (yyyy-MM-dd)). 
- Java Time are LocalTime, Represents a time(hour, minute, second and nanoseconds (HH-mm-ss-ns)). 
- Calendar class in Java is an abstract class that provides methods for 
converting date between a specific instant in time and a set of calendar fields such as MONTH, YEAR, HOUR, etc

this program demonstrates the usage of Date and Calendar classes to work with dates and times in Java.

### Source Code
```java
import java.util.Calendar;
import java.util.Date;
import java.util.Calendar;
 

public class DataTimeDemo {
    public static void main(String[] args) {
 
        System.out.println(System.currentTimeMillis());
        long year=(System.currentTimeMillis()/1000/60/60/24/365);
        System.out.println(year);
      
        Date d =new Date();//MM-DD-YYYY
        System.out.println(d);
        System.out.println("Date    : "+d.getDate());
        System.out.println("Day     : "+d.getDay()); //0 Sunday to 7-Saturday
        System.out.println("Month   : "+d.getMonth());//0 Jan to 11 Dec
        System.out.println("Year    : "+(d.getYear()+1900));
        System.out.println("Time    : "+d.getTime());
        System.out.println("Hours   : "+d.getHours());
        System.out.println("Minutes : "+d.getMinutes());
        System.out.println("Seconds : "+d.getSeconds());
 
 
        Calendar o =new Calendar();
        //System.out.println(o);
        System.out.println(o.isLeapYear(2020));
        System.out.println("Date  : "+o.get(Calendar.DATE));
        System.out.println("Month : "+o.get(Calendar.MONTH));
        System.out.println("Year  : "+o.get(Calendar.YEAR));
        System.out.println("Day of Week  : "+o.get(Calendar.DAY_OF_WEEK)); //1-Sun to 7-Sat
        System.out.println("Day of Year  : "+o.get(Calendar.DAY_OF_YEAR));
 
    }
}
```
## Also
In Java, handling dates and times is commonly done through the *java.time* package, introduced in Java 8 as part of the new Date and Time API.
This API provides classes to represent dates, times, durations, and intervals, along with methods to perform various operations on them. 
Here's an overview of some key classes and functions:

### LocalDate: Represents a date without a time zone.
```java

import java.time.LocalDate;

// Create a LocalDate object representing today's date
LocalDate today = LocalDate.now();

// Create a LocalDate object for a specific date
LocalDate specificDate = LocalDate.of(2024, 4, 30);

// Get year, month, and day from a LocalDate object
int year = today.getYear();
int month = today.getMonthValue();
int day = today.getDayOfMonth();
```
### LocalTime: Represents a time without a date.

```java

import java.time.LocalTime;

// Create a LocalTime object representing the current time

LocalTime currentTime = LocalTime.now();

// Create a LocalTime object for a specific time
LocalTime specificTime = LocalTime.of(12, 30, 45);

// Get hour, minute, and second from a LocalTime object
int hour = currentTime.getHour();
int minute = currentTime.getMinute();
int second = currentTime.getSecond();
```

### LocalDateTime: Represents both date and time without a time zone.

```java

import java.time.LocalDateTime;

// Create a LocalDateTime object representing the current date and time
LocalDateTime currentDateTime = LocalDateTime.now();

// Create a LocalDateTime object for a specific date and time
LocalDateTime specificDateTime = LocalDateTime.of(2024, 4, 30, 12, 30, 45);

```
### DateTimeFormatter: Formats date and time objects into strings and parses strings into date and time objects.

```java

import java.time.format.DateTimeFormatter;

// Format a LocalDateTime object into a string
DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");
String formattedDateTime = currentDateTime.format(formatter);
System.out.println("Formatted DateTime: " + formattedDateTime);

// Parse a string into a LocalDateTime object
LocalDateTime parsedDateTime = LocalDateTime.parse("2024-04-30T12:30:45");
```
### Duration and Period: Represent durations and periods of time, respectively.

```java

import java.time.Duration;
import java.time.Period;

// Calculate the duration between two LocalDateTime objects
Duration duration = Duration.between(startDateTime, endDateTime);
long seconds = duration.getSeconds();

// Calculate the period between two LocalDate objects
Period period = Period.between(startDate, endDate);
int years = period.getYears();
int months = period.getMonths();
int days = period.getDays();
```
