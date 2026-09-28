#include <iostream>
#include <string>
using namespace std;

// Function to determine the grade
char calculateGrade(double mark)
{
    if (mark >= 80)
        return 'A';
    else if (mark >= 70)
        return 'B';
    else if (mark >= 60)
        return 'C';
    else if (mark >= 50)
        return 'D';
    else if (mark >= 40)
        return 'E';
    else
        return 'F';
}

int main()
{
    int numberOfStudents;
    string moduleName;

    cout << "========================================" << endl;
    cout << "       SMART GRADING SYSTEM" << endl;
    cout << "========================================" << endl;

    // Ask for the subject/module
    cout << "\nEnter subject/module name: ";
    getline(cin, moduleName);

    // Ask for number of students
    cout << "Enter number of students: ";
    cin >> numberOfStudents;

    // Arrays to store student information
    string names[100];
    double marks[100];
    char grades[100];

    // Input student information
    for (int i = 0; i < numberOfStudents; i++)
    {
        cout << "\n----------------------------------------" << endl;
        cout << "Student " << i + 1 << endl;

        cout << "Enter student name: ";
        cin >> names[i];

        cout << "Enter final mark (%): ";
        cin >> marks[i];

        // Automatically calculate grade
        grades[i] = calculateGrade(marks[i]);
    }

    // Display results
    cout << "\n\n========================================" << endl;
    cout << "           FINAL RESULTS" << endl;
    cout << "========================================" << endl;

    cout << "Module: " << moduleName << endl;

    cout << "\nStudent\t\tMark\tGrade" << endl;
    cout << "----------------------------------------" << endl;

    for (int i = 0; i < numberOfStudents; i++)
    {
        cout << names[i] << "\t\t"
             << marks[i] << "%\t"
             << grades[i] << endl;
    }

    cout << "========================================" << endl;

    return 0;
}
