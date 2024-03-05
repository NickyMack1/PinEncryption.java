# PinEncryption.java

import java.util.Random;
import java.util.Scanner;

public class PinEncryption {
    public static void main(String[] args) {
        // Create a scanner object to read input from the user
        Scanner scanner = new Scanner(System.in);

        // Prompt the user to enter a 4-digit pin number
        System.out.print("Enter a 4-digit pin number to encrypt: ");
        int pin = scanner.nextInt();

        // Generate two random numbers greater than 1000 and less than 65536
        Random random = new Random();
        int random1 = random.nextInt(64535) + 1001; // Random number between 1001 and 65535
        int random2 = random.nextInt(64535) + 1001; // Random number between 1001 and 65535

        // Convert pin number to hexadecimal
        String pinHex = Integer.toHexString(pin);

        // Convert random numbers to hexadecimal
        String random1Hex = Integer.toHexString(random1);
        String random2Hex = Integer.toHexString(random2);

        // Construct the encrypted pin by sandwiching the pin between the two random hexadecimal numbers
        String encryptedPin = random1Hex + pinHex + random2Hex;

        // Output the encrypted pin
        System.out.println("Your encrypted pin number is " + encryptedPin);
    }
}

Enter a 4-digit pin number to encrypt: 3189
Your encrypted pin number is 1155c75bdf3
