# StandardDeviationProject
package com.company;

// ---------*---------*---------*---------*---------*
// The use of static imports is something that should be used carefully.
// I have only ever used this technique for the project wide constants.
//
import java.io.File;
import java.io.FileNotFoundException;
import java.text.DecimalFormat;
import java.util.Scanner;

import static com.company.ProjConstants.*;

public class Main {

    public static void main(String[] args) {

        boolean fileDone = false;
        boolean proceed = true;
        double theAverage = 0;
        double theVariance = 0;
        double theStDeviation = 0;
        int numberItems = 0;
        int theNumberObservations = 0;
        int counter = 0;
        String userFileName;
        String userInput;

        StDeviation calcSDev =  new StDeviation();

        while (proceed == true) {
            try {

                System.out.println("");
                System.out.println("Please type in the file name\n");

                Scanner scanSystemIn = new Scanner(System.in);
                userFileName = scanSystemIn.next();

                File userFile = new File(userFileName);
                Scanner scanUserFile = new Scanner(userFile);

                System.out.println("\nThe user input: " + userFileName);

                while (!fileDone) {

                    if (scanUserFile.hasNext()) {
                        counter = scanUserFile.nextInt();
                        System.out.print(" -- " + counter);

                        calcSDev.addNewDataItem(counter);
                        if (counter > MAXDATA) {
                            System.out.printf("The file chosen is too large; the file was not completely read into array");
                        }// end if (counter>= MAXDATA)
                    }// end (scanUserFile.hasNext())
                    else {
                        System.out.println();
                        // System.out.println("==================================================================\n");
                        System.out.print("\n\n The file has been completely read");
                        scanUserFile.close();
                        System.out.println();
                        fileDone = true;
                    }// end else
                }// end while

            } catch (FileNotFoundException e) {

                System.out.println("------------------------------------------------");

                System.out.println(e);
                e.printStackTrace();
            }

            theAverage = calcSDev.calcAverage();

            theVariance = calcSDev.calcVariance();

            theStDeviation = calcSDev.calcStandardDeviation();

            numberItems = calcSDev.getNumberOfDataItems();


            // show the range of values that contain 68% of the observations, 95% of the observations, and 99% of the observations.

           // double theRange68 = (theAverage + theStDeviation) - (theAverage - theStDeviation);
           // double theRange95 = (theAverage + 2 * theStDeviation) - (theAverage - 2 * theStDeviation);
            //double theRange99 = (theAverage + 3 * theStDeviation) - (theAverage - 3 * theStDeviation);

            DecimalFormat numberFormat = new DecimalFormat("#.0000");

            // if counter> MaxData, print "The file chosen is too large; file not completely read into array"
            // print within 4 decimal point
            System.out.println("------------------------------------------------");
            System.out.printf("For the values found in file:");
            System.out.println(" ");
            System.out.println(" ");
            System.out.printf("\t Number of Items..........", numberItems);
            System.out.println(" ");
            System.out.println(" ");
            System.out.printf("\t Mean....................%10.4f", theAverage);
            System.out.println(" ");
            System.out.println(" ");
            System.out.printf("\t Variance................%10.4f\n", theVariance);
            System.out.println(" ");
            System.out.printf("\t Standard Deviation .....%10.4f\n", theStDeviation);
            System.out.println(" ");

            //"First Name: %s\nLast Name: %s",firstname, lastname);
            System.out.println("==================================================================\n");
            System.out.printf("\t\t\t\t\t\t\t\tLower\t\t Mean\t\tUpper");
            System.out.println();

            System.out.printf("68 percent of the data is:\t");
            System.out.printf("%10.4f\n", (theAverage - theStDeviation));
            System.out.printf("%10.4f\n", theAverage);
            System.out.printf("%10.4f\n", (theAverage + theStDeviation));

            System.out.println();
            System.out.printf("95 percent of the data is:\t");
            System.out.printf("%10.4f\n", (theAverage - 2 * theStDeviation));
            System.out.printf("%10.4f\n", theAverage);
            System.out.printf("%10.4f\n", (theAverage + 2 * theStDeviation));

            System.out.println(" ");
            System.out.printf("99 percent of the data is:\t");
            System.out.printf("%10.4f\n", (theAverage - 3 * theStDeviation));
            System.out.printf("%10.4f\n", theAverage);
            System.out.printf("%10.4f\n", (theAverage + 3 * theStDeviation));
            System.out.println();

            System.out.println();
            System.out.println("==================================================================\n");
            System.out.println();


            //ask the user if they would like to continue, if they press N or n then the boolean proceed= false and it will break out of the main while loop
            System.out.println("");
            System.out.println("Would you like to continue? Press 'n' or 'N' if you would like to exit\n");

            Scanner scanSystemIn = new Scanner(System.in);
            userInput = scanSystemIn.next();

                    while (!(scanSystemIn.hasNext("N") || scanSystemIn.hasNext("n"))) {
                       proceed = false;
                    }

        }// end while proceed=true

            System.out.println("process finished");
            System.out.println("------------------------------------------------");

}// end main method
}// end main class
