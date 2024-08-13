# CodeAlpha_StudentGradeTracker
import java.util.ArrayList;
import java.util.Scanner;

public class StudentGrades {

    public static void main(String[] args) {
        ArrayList<Double> grades = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        String input;

        System.out.println("Enter student grades. Type 'done' to finish:");

        while (true) {
            System.out.print("Enter grade: ");
            input = scanner.nextLine();
            if (input.equalsIgnoreCase("done")) {
                break;
            }
            try {
                double grade = Double.parseDouble(input);
                grades.add(grade);
            } catch (NumberFormatException e) {
                System.out.println("Invalid input. Please enter a number or 'done' to finish.");
            }
        }


        if (!grades.isEmpty()) {
            double sum = 0;
            double highest = grades.get(0);
            double lowest = grades.get(0);

            for (double grade : grades) {
                sum += grade;
                if (grade > highest) {
                    highest = grade;
                }
                if (grade < lowest) {
                    lowest = grade;
                }
            }

            double average = sum / grades.size();

            System.out.println("Average grade: " + average);
            System.out.println("Highest grade: " + highest);
            System.out.println("Lowest grade: " + lowest);
        } else {
            System.out.println("No grades were entered.");
        }

        scanner.close();
    }
}
