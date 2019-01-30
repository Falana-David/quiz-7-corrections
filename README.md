# quiz-7-corrections

Q1: Consider the following code segment.

ArrayList<Integer> numbers = new ArrayList<Integer>();
System.out.println(numbers.get(0));
What is printed to the console as a result of executing this code?

My Answer: null


Correct Answer:  
An IndexOutOfBoundsException will be thrown.

Why It;s Correct: It is correct because the arraylist is empty. It is seraching for a value that does not exist. So since there is nothing at index 0 nothonig is returned.


Q3: I need to write a method designed to compute and return a student's average based on a list of grades. Which of the following methods will accomplish this task for all possible inputs (including null or empty ArrayLists)? Select all that apply.

My Answer: public double getAverage(ArrayList<Double> grades) {
    double sum = 0;

    for (int i = 0; i < grades.size(); i++) {
        sum = sum + grades.get(i);
    }

    return sum / grades.size();
}
public double getAverage(ArrayList<Double> grades) {
    double sum = 0;

    if (grades != null) {
        for (int i = 0; i < grades.size(); i++) {
            sum = sum + grades.get(i);
        }

        if (grades.size() > 0) {
            return sum / grades.size();
        }
    }

    return -1;
}

public double getAverage(ArrayList<Double> grades) {
    double sum = 0;

    if (grades != null) {
        for (double grade : grades) {
            sum = sum + grade;
        }

        if (grades.size() > 0) {
            return sum / grades.size();
        }
    }

    return -1;
}

Correct Answer:public double getAverage(ArrayList<Double> grades) {
    double sum = 0;

    if (grades != null) {
        for (int i = 0; i < grades.size(); i++) {
            sum = sum + grades.get(i);
        }

        if (grades.size() > 0) {
            return sum / grades.size();
        }
    }

    return -1;
  
public double getAverage(ArrayList<Double> grades) {
    double sum = 0;

    if (grades != null) {
        for (double grade : grades) {
            sum = sum + grade;
        }

        if (grades.size() > 0) {
            return sum / grades.size();
        }
    }

    return -1;
}

Why It;s Correct: These two check for values in grade. If there is a value then it will add it starting with the value 0 for sum. And it will counitinue to do that to get the total. Then it returns the amount of students divided by the average.

Q6: Consider the following code segment.

String[] data = new String[] {
    "New York", "Boston", "Philadelphia", "Washington, D.C.", "Chicago", "Los Angeles"
};
ArrayList<String> cities = new ArrayList<String>();

for (String city : data) {
   cities.add(city);
}
System.out.println(cities.get(1));
What is printed to the console as a result of executing this code?

My Answer:  Nothing, because a compilation error occurs. 


Correct ANswer:Boston

Why It's Correct: It is correct because it is asking for the value at index 1. The for loop in this question is irrelevant only adding more values. So the value at index 1 is boston which is the answer.

Q7: Consider the following code segment, which is designed to print only those values in an array that are multiples of 5.

for (int i = 0; i < numbers.size(); i++) {
    if (numbers.get(i) % 5 == 0) {
        System.out.println(numbers.get(i));
    }
}
Which of the following code snippets represents the equivalent behavior? You may assume (in both the question and answer options) that numbers is properly declared and initialized. Select all that apply.

My Answer: for (int number : numbers) {
    if (number % 5 == 0) {
        System.out.println(number);
    }
}

Correct ANswer: 
for (int number : numbers) {
    if (number % 5 == 0) {
        System.out.println(number);
    }
}

numbers.forEach((number) -> System.out.println(number));

Why It's Correct: It is correct because the for loop checks each number in the array. Then it checks if it is a multiple in the if statment. If yes it prints out the values. WHile the other loop does it in a similar fashion.

Q9: Although their behaviors are identical, length is a  of an array whereas size is a  of the ArrayList class. Syntactically, this difference is shown by either the presence of absence of parentheses .

My Answer: property , function, parethesis
Correct Answer: Property, method, parthesis

Why Its Correct: This is because length is a propery of an array. And size is a method it is not a funciton. A function would be something that would have cause to run in java.

Q15: Consider the following method, which is designed to return the maximum value in an ArrayList.

/**
 * Returns the maximum value in the ArrayList.
 * Precondition: values != null && values.size() > 0
 */

public int findMaximum(ArrayList<Integer> values) {
    int max = 0;

    for (int i = 0; i < values.size(); i++) {
        if (values.get(i) > max) {
            max = values.get(i);
        }
    }

    return max;
}
Which of the following calls to findMaximum demonstrates that it does not work as expected?

My Answer: ArrayList<Integer> data = new ArrayList<Integer>();
for (int i = 0; i < 5; i++) {
    data.add(0);
}

findMaximum(data);

Correct Answer: ArrayList<Integer> data = new ArrayList<Integer>();
data.add(-5);
data.add(-1);
data.add(-4);
data.add(-2);
data.add(-3);

findMaximum(data);

Why Its Correct: It is correct because negatives never work correctly with java. Inside functions in java negative values are meant to be handled diffrently.
