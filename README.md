# CGPA-BY-JAVA
import java.util.Scanner;

public class ResultCalculator {

    // Method to convert marks to grade point
    public static double gradePoint(double marks) {
        if(marks >= 80) return 4.00;
        else if(marks >= 75) return 3.75;
        else if(marks >= 70) return 3.50;
        else if(marks >= 65) return 3.25;
        else if(marks >= 60) return 3.00;
        else if(marks >= 55) return 2.75;
        else if(marks >= 50) return 2.50;
        else if(marks >= 45) return 2.25;
        else if(marks >= 40) return 2.00;
        else return 0.00;
    }

    // Method to convert CGPA to grade letter
    public static String letterGrade(double gpa) {
        if(gpa == 4.00) return "A+";
        else if(gpa >= 3.75) return "A";
        else if(gpa >= 3.50) return "A-";
        else if(gpa >= 3.25) return "B+";
        else if(gpa >= 3.00) return "B";
        else if(gpa >= 2.75) return "B-";
        else if(gpa >= 2.50) return "C+";
        else if(gpa >= 2.25) return "C";
        else if(gpa >= 2.00) return "D";
        else return "F";
    }

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        String studentID;
        int[] credit = new int[3];
        double ct, at, fe, marks;
        double[] gp = new double[3];
        double totalCredit = 0, weightedGP = 0;

        System.out.print("Enter Student ID: ");
        studentID = input.nextLine();

        for(int i = 0; i < 3; i++) {
            System.out.println("\nCourse " + (i+1) + ":");
            System.out.print("Credit (Max 3): ");
            credit[i] = input.nextInt();

            System.out.print("CT (Max 30): ");
            ct = input.nextDouble();

            System.out.print("AT (Max 10): ");
            at = input.nextDouble();

            System.out.print("FE (Max 60): ");
            fe = input.nextDouble();

            marks = ct + at + fe;
            gp[i] = gradePoint(marks);

            totalCredit += credit[i];
