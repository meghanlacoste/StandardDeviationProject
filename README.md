# StandardDeviationProject
package com.company;
public final class ProjConstants {
    // Define Integer Constants
    public static final int INVALID = -1;
    public static final int MAXDATA = 2000;


    // Declare as a private constructor to prevent the caller from being able to construct
    // objects using the class
    private ProjConstants(){
        //this prevents even the native class from calling this constructor as well
        throw new AssertionError();
    }


    import static com.company.ProjConstants.*;

public class Main {


    public class StDeviation {


        // ---------*---------*---------*---------*---------*---------*---------*---------*
        // As discussed in class we are using a class populated with Project Constants to
        // ensure help manage the project data. This ensures that each class can access the
        // constant values, but in the event that a change is needed/required that this will
        // only need to be made in one location, or file.
        //
        // Notice: If I had not done the "static import com.company.ProjConstants.*;" then
        //         the use of the constant would have been written as:
        //
        //         private int[] Data = new int[ProjConstants.MAXDATA];
        //
        private int[] Data = new int[MAXDATA];

        // ---------*---------*---------*---------*---------*---------*---------*---------*
        // The following method will take a new data item and add it into the 1 Dimensional
        // Array of data values to be used later.
        //
        // You MUST write this method and I will use it during testing
        //
        public void addNewDataItem(double dataItem){

        }

        // ---------*---------*---------*---------*---------*---------*---------*---------*
        // The following method will return the total number of data items currently stored
        //
        // You MUST write this method and I will use it during testing
        //
        public int getNumberOfDataItems(){

            // temporary value
            return INVALID;
        }

        // ---------*---------*---------*---------*---------*---------*---------*---------*
        // The following method returns a double precision value which is the average of all
        // of the data values
        //
        // You MUST write this method and I will use it during testing
        //
        public double calcAverage(){

            // temporary value
            return INVALID;
        }

        // ---------*---------*---------*---------*---------*---------*---------*---------*
        // The following method returns a double precision value which is the Variance of all
        // of the data values
        //
        // You MUST write this method and I will use it during testing
        //
        public double calcVariance(){

            // temporary value
            return INVALID;
        }


        // ---------*---------*---------*---------*---------*---------*---------*---------*
        // The following method returns a double precision value which is the Standard
        // Deviation of all of the data values
        //
        // You MUST write this method and I will use it during testing
        //
        public double calcStandardDeviation(){

            // temporary value
            return INVALID;
        }

    }// end main method
}// end main class
