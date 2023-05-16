import java.time.LocalDateTime;
import java.time.ZoneId;
import java.time.format.DateTimeFormatter;
import java.util.*;

public class TimeConverter {
    public static void main(String[] args) {
      // Specify the source time and timezone
      LocalDateTime sourceTime = LocalDateTime.now();
	Scanner sc=new Scanner(System.in);
	System.out.println("enter the source country:");
	String from=sc.nextLine();
      ZoneId sourceZone = ZoneId.of(from);
	System.out.println("enter the country name to convert the time accordingly:");
	String to=sc.nextLine();
      // Specify the target timezone
      ZoneId targetZone = ZoneId.of(to);
        
      // Convert the source time to the target timezone
      LocalDateTime convertedTime = sourceTime.atZone(sourceZone).withZoneSameInstant(targetZone).toLocalDateTime();
        
      // Format the converted time using a specific pattern
      DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
      String formattedTime = convertedTime.format(formatter);
        
      // Print the converted time
      System.out.println("Converted time: " + formattedTime);
    }
}
