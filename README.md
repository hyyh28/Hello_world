# Hello_world
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package exercise2;
import java.text.DateFormatSymbols;
import java.util.*;

/**
 *
 * @author hyyh2
 */
public class Exercise2 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        Locale.setDefault(Locale.US);
        Scanner in = new Scanner(System.in);
        System.out.println("Please type in the year ");
        int year = in.nextInt();
        System.out.println("Please type in the month ");
        int month = in.nextInt();
        GregorianCalendar d = new GregorianCalendar(year,month-1,1);
        String[] weekdayName = new DateFormatSymbols().getShortWeekdays();
        for(int i = 1; i <= 7; i++)
        {
            System.out.printf("%4s" , weekdayName[i]);
        }
        int weekday = d.get(Calendar.DAY_OF_WEEK);
        int firstDay = d.getFirstDayOfWeek();
        int index = weekday - firstDay;
        System.out.println();
        for(int j = 0; j< index;j++) 
            System.out.printf("    ");
        do
        {
            int day = d.get(Calendar.DAY_OF_MONTH);
            System.out.printf("%4d", day);
            d.add(Calendar.DAY_OF_MONTH, 1);
            weekday = d.get(Calendar.DAY_OF_WEEK);
            if(weekday == firstDay) System.out.println();
        }
        while(d.get(Calendar.MONTH ) == month-1);
        if(weekday != firstDay) System.out.println();
    }
}
