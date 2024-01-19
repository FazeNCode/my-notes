

Question 1.)

public class Assignment {
    public static void main(String[] args) {
        
        float f = 3.14159f;
        double d = f;
    
        System.out.println(f);
    }
}

This operation is legal, and will print without any errors.

Breakdown:
float is a data type that can store fractional numbers, approximately 6 ~ 7 decimal digits
double is a data type that also stores fractional numbers, approximately 15 decimal digits.
[ EXAMPLE: of fractional number 4.2069]

variables:
f = 3.14159 

d = f;
we are essentially assign the value of the "f" variable to the "d" variable, 
This works because they both handle fractional number 

LINK FOR REFRENCE DATA TYPES:    https://www.w3schools.com/java/java_data_types.asp

LINK FOR REFERENCE FLOAT VS DOUBLE:  
https://favtutor.com/blogs/java-float-vs-double






Question 2.)
public class Assignment {
    public static void main(String[] args) {
        
       int i = 11223344;
       short s = i;
    
        System.out.println(i);
    }
}

This operation is not legal, it will still present an error: 

Breakdown:
int is a data type that can store -2,147,483,648 to 2,147,483,647 
short is a data type that can store -32,768 to 32,767 

variables: 
i = 11223344
s = i

The "i" variable has been assigned correctly, since int contains numbers only
The "s" variable is where the problem occurs, short data type is a number, 
and we are trying to assign it a string, that’s a no go, instead we need to use a 
char data type


LINK FOR REFRENCE: https://www.w3schools.com/java/java_data_types.asp






Question 3.)
public class Assignment {
    public static void main(String[] args) {
        
       int i = 44;
       char c = i;

       // char c = 'i';    <--- this is the correct way to assign the value using char data type

       System.out.println(c);
        System.out.println(i);

    }
}
No this operation is not legal, and will present us with an error

Breakdown:
This is because the "i" is not in singe quotation 
Char data type Stores a single character/letter or ASCII values







Question 4.)
public class Assignment {
    public static void main(String[] args) {
        
      float f = 3.1345f;
      double d = f;
       System.out.println(d);   

    }
}


This operation is legal, and will print without any errors.

Breakdown:
float is a data type that can store fractional numbers, approximately 6 ~ 7 decimal digits
double is a data type that also stores fractional numbers, approximately 15 decimal digits.
[ EXAMPLE: of fractional number 3.1234567 ]

variables:
f = 3.1345
d = f

we are essentially assign the value of the "f" variable to the "d" variable, 
This works because they both handle fractional number 

LINK FOR REFRENCE: https://www.w3schools.com/java/java_data_types.asp






Question 5.)
public class Assignment {
    public static void main(String[] args) {
        
     char c = 'a';
     int i = (int)c;
        
       System.out.println(i);
       
    }
}

This operation is legal, and will print without any errors.

this is because the data types are correct and assigned correctly.
The "c" variable is being assigned to the 'a' character.
The I variable is being casted and converted to int using the ASCII Table

This method is known as "Type-Casting"

the output is 97, this is because on the ASCII Table, the 'a' char has a value of 97
 
LINK FOR REFERENCE:  
https://www.rapidtables.com/code/text/ascii-table.html








Question 6.)
// We must import the scanner to utilize it, must be Capital S
import java.util.Scanner;

class Assignment2 {
    public static void main(String[] args) {
    
// Println asking the user to enter there name
        System.out.println("Hello, enter your name");

// Created a scanner object named "name", the scanner will take in the users input        
        Scanner name = new Scanner(System.in);

// Made a String object named "Nameobj" to store the users input, which in this case is his name. 
            String Nameobj = name.nextLine();

// Println asking the user to enter there age   
        System.out.println("Hello, enter your Age");

// Created a scanner object named "age", the scanner will take in the users input      
       Scanner age = new Scanner(System.in);

// Made a Int object named "Ageobj" to store the users input, which in this case is his name. 
            int Ageobj = age.nextInt();

System.out.println("**********," + " " + "***" );

// Printing out  "Nameobj" and "Ageobj"  and "\t" is for putting a tab space in the print statement
System.out.print(Nameobj + "\t" + "\t"  + Ageobj );

    }
}


LINK FOR REFERENCE FOR SCANNER OBJECTS:  https://www.w3schools.com/java/java_user_input.asp







Question 7.)
public class Assignment {
	public static void main(String[] args) {
		System.out.printf("[%2s%9.5f] ",  "",  98.3456) ;
	}
}

What does printf do?
printf Allows us to output data in a formatted fashion, to our liking 
% is referred to as the format specifier


EXAMPLES:
System.out.printf("%d This is a format string", 123);

System.out.printf("%s This is where %s for string goes",  argument);



%d is for int data type number (whole number)
%f is for double and float data type number (decimal) 
%c is for characters   
%C is for upper case characters  
%s is for string
%S is for upper case String  
%n is for new line 		You don't need an argument for this  
/n is for new line 		You don't need an argument for this
%% is for percentage 	You don't need an argument for this

LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf








Question 8.)
public class Assignment {
	public static void main(String[] args) {
		System.out.printf("[%07.5f]\n", 98.3456);
		
	}
}

%07 is the field, meaning the output to the console should have a maximum of 7 digits

.5 is the precision, which means how many decimals number  should be rounded 

F is the format specifies for a floating-point number.

\n is for the new line character which will move the cursor to the next line after printing 
9    8    3    4     5    6    0

LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf



Question 9.)
public class Assignment {
	public static void main(String[] args) {
		System.out.printf("[%07.5f]\n", 98.3456);
		
	
}
LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf








Question 10.)
public class Assignment {
	public static void main(String[] args) {

	System.out.printf("[%3s%6d] \n", "" ,123456);
	}
}

%s3s is for putting 3 strings, which will just be empty.
%6d is for 6 decimal places since we have 6 numbers in total we are fine with it.
\n is for new line.


Similarly  you can use the code below and it will perform the same output

System.out.printf("[%9d]\n", 123456);

%9 is for 9 decimal places, at the moment we have 6 numbers in the argument, and we are giving 3 extra decimal places to achieve the space .
\n is for new line.

LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf



Question 11.)
public class Assignment {
	public static void main(String[] args) {

System.out.printf("[%-9d]\n", 123456);

	}
}
LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf









Question 12.)
public class Assignment {
	public static void main(String[] args) {

System.out.printf("[%07d   ]\n", 123456);
	}
}

%07d is for 7 decimal place  with a 0
\n is for new line


LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf










Question 13.)
public class Assignment {
	public static void main(String[] args) {

System.out.printf("[%08d]\n", 123456);

	}
}
%08d is for 8 decimal place we put the 0 there so we get 2  0’s before 
123456 

If we took the 0 out and just put %8d it will give 2 spaces before the number example below
[  123456]

\n is for new line

LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf










Question 14.)
public class Assignment {
	public static void main(String[] args) {

System.out.printf("[   %s]\n", "abc");

	}
}

%s is for putting a string 
\n is for putting a new line


Similarly we can also use the code below for the same task
System.out.printf("[%6s]\n", "abc");

%6s is for 6 string character
\n is for new-line

LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf







Question 15.)

public class Assignment {
	public static void main(String[] args) {

System.out.printf("[%s   ]\n", "abc");

	}
}
%s is for putting a string 

We put two spaces manually, but we can also use %3s instead, example below: Make sure to put a comma for separating 

System.out.printf("[%3s ]\n", “  ”, "abc");
\n is for putting a new line

LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf









Question 16.
// We must import the scanner to utilize it, must be Capital S
import java.util.Scanner;

class Assignment2 {
    public static void main(String[] args) {
    
    // Asking the user to enter a number
   System.out.println("Enter a number");

// utilizing the scanner that we imported
   Scanner Inputnumber = new Scanner(System.in);

// made a variable called userinput to store the data the user inputs
    int userInput = Inputnumber.nextInt();

    if(userInput > 80){
         System.out.println("You have entered a large number");
    } else {
        System.out.println("You have entered a small number");
    }
           
       
    }
}


LINK FOR REFERENCE
https://www.baeldung.com/java-printstream-printf
