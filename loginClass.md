

import java.util.Scanner;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class loginClass {

    public static void main(String[] args) {
        registerUser();
        LoginUser();
        returnLoginStatus();
    }

    public static boolean checkUserName() {
        Scanner input = new Scanner(System.in);
        Matcher M;
        do {
            // This part runs the scanner for User Input
            System.out.println("Enter UserName");
            String User = input.nextLine();
            // This part checks to see whether the pattern matches the compiler's condition
            Pattern P = Pattern.compile("((?=.*[_]).{5})");
            M = P.matcher(User);

            // The IF statement checks to see if the Input Matches the condition and gives the following statement
            if (M.matches()) {
                System.out.println("true");
                return true;
            } else {
                System.out.println("false");
            }
        } while (!M.matches());
        return false;
    }

    public static boolean checkPasswordComplexity() {
        Scanner input = new Scanner(System.in);
        Matcher K;
        do {
            // This part runs the scanner for User Input
            System.out.println("Enter Password");
            String User = input.nextLine();
            // This part checks to see whether the pattern matches the compiler's condition
            Pattern Pas = Pattern.compile("((?=.*[!@#$%^&*~])(?=.*[0-9])(?=.*[A-Z]).{8,20})");
            K = Pas.matcher(User);

            if (K.matches()) {
                System.out.println("true");
                return true;
            } else {
                System.out.println("false");
            }
        } while (!K.matches());
        return false;
    }

    public static void registerUser() {
        Scanner input = new Scanner(System.in);
        Matcher M;
        do {
            System.out.println("Enter UserName");
            String User = input.nextLine();
            Pattern P = Pattern.compile("((?=.*[_]).{5})");
            M = P.matcher(User);

            if (M.matches()) {
                System.out.println("Username successfully captured");
            } else {
                System.out.println("Username is not correctly formatted, please ensure that your username contains an underscore and is no more than 5 characters in length.");
            }
        } while (!M.matches());

        Matcher G;
        do {
            System.out.println("Enter Password");
            String User4 = input.nextLine();
            Pattern Pas = Pattern.compile("((?=.*[!@#$%^&*~])(?=.*[0-9])(?=.*[A-Z]).{8,20})");
            G = Pas.matcher(User4);

            if (G.matches()) {
                System.out.println("Password successfully captured");
            } else {
                System.out.println("Password is not correctly formatted, please ensure that the password contains at least 8 characters, a capital letter, a number and a special character.");
            }
        } while (!G.matches());
    }

    public static boolean LoginUser() {
        // The information below is the User's Login details
        String UserNameL = "kyl_1";
        String PasswordL = "Ch&&sec@ke99!";

        // This code runs a scanner to allow the user to Input their User Name and Password
        Scanner input = new Scanner(System.in);
        String UserName1;
        String Password1;
        do {
            System.out.println("Enter User Login");
            UserName1 = input.nextLine();

            System.out.println("Enter Password");
            Password1 = input.nextLine();

            // This part of the code checks to see if the conditions for the Login have been met and outputs the correct response
            if (UserName1.equals(UserNameL) && Password1.equals(PasswordL)) {
                System.out.println("true");
                return true;
            } else {
                System.out.println("false");
            }
        } while (!UserName1.equals(UserNameL) || !Password1.equals(PasswordL));
        return false;
    }

    public static String returnLoginStatus() {
        String UserNameL = "kyl_1";
        String PasswordL = "Ch&&sec@ke99!";

        // This code runs a scanner to allow the user to Input their User Name and Password
        Scanner input = new Scanner(System.in);
        String UserName1;
        String Password1;
        do {
            System.out.println("Enter User Login");
            UserName1 = input.nextLine();

            System.out.println("Enter Password");
            Password1 = input.nextLine();

            // This part of the code checks to see if the conditions for the Login have been met and outputs the correct response
            if (UserName1.equals(UserNameL) && Password1.equals(PasswordL)) {
                System.out.println("Welcome <user first name> ,<user last name> it is great to see you again.");
                return "Login successful";
            } else {
                System.out.println("Username or password incorrect, please try again");
            }
        } while (!UserName1.equals(UserNameL) || !Password1.equals(PasswordL));

        return "Login failed";
    }
}
