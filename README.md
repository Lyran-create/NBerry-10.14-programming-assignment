# NBerry-10.14-programming-assignment

import java.util.Calendar;
import java.util.GregorianCalendar;

public class MyDate {
    private int year;
    private int month;
    private int day;

    // No-arg constructor: Creates a MyDate object for the current date
    public MyDate() {
        this(System.currentTimeMillis()); // Delegate to the constructor that takes elapsed time
    }

    // Constructor: Constructs a MyDate object with specified elapsed time since midnight, Jan 1, 1970
    public MyDate(long elapsedTime) {
        setDate(elapsedTime); // Initialize the object with the provided elapsed time
    }

    // Constructor: Constructs a MyDate object with specified year, month, and day
    public MyDate(int year, int month, int day) {
        this.year = year;
        this.month = month;
        this.day = day;
    }

    // Getter method for year
    public int getYear() {
        return year;
    }

    // Getter method for month
    public int getMonth() {
        return month;
    }

    // Getter method for day
    public int getDay() {
        return day;
    }

    // Method to set date using elapsed time
    public void setDate(long elapsedTime) {
        GregorianCalendar calendar = new GregorianCalendar();
        calendar.setTimeInMillis(elapsedTime);

        // Extract the year, month, and day from the GregorianCalendar object
        this.year = calendar.get(Calendar.YEAR);
        this.month = calendar.get(Calendar.MONTH);
        this.day = calendar.get(Calendar.DAY_OF_MONTH);
    }

    // Main method to test the MyDate class
    public static void main(String[] args) {
        // Create a MyDate object for the current date
        MyDate date1 = new MyDate();
        System.out.println("Date1 -> Year: " + date1.getYear() + ", Month: " + date1.getMonth() + ", Day: " + date1.getDay());

        // Create a MyDate object with specified elapsed time
        MyDate date2 = new MyDate(34355555133101L);
        System.out.println("Date2 -> Year: " + date2.getYear() + ", Month: " + date2.getMonth() + ", Day: " + date2.getDay());
    }
}
