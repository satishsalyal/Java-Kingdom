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
 
@SuppressWarnings("ALL")
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
