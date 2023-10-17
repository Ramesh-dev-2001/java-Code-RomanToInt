//# java-Code-RomanToInt
//RomanNum to Integer
import java.util.*;

public class RomanToInteger {
    public static int romanToInt(String s) {
        Map<Character, Integer> romanMap = new HashMap<>();
        romanMap.put('I', 1);
        romanMap.put('V', 5);
        romanMap.put('X', 10);
        romanMap.put('L', 50);
        romanMap.put('C', 100);
        romanMap.put('D', 500);
        romanMap.put('M', 1000);

        int a = 0;
        int prevValue = 0;

        for (int i = s.length() - 1; i >= 0; i--) {
            int currentValue = romanMap.get(s.charAt(i));
            if (currentValue < prevValue) {
                a -= currentValue;
            } else {
                a += currentValue;
            }
            prevValue = currentValue;
        }

        return a;
    }

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.print("Enter a Roman number: ");
        String romanNumeral = scan.nextLine().toUpperCase();
        int integerEquivalent = romanToInt(romanNumeral);
        System.out.println("Integer equivalent: " + integerEquivalent);
        scan.close();
    }
}
