# basic-calculator-
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    double num1, num2, result;
    int choice;

    do {
        // Display menu
        cout << "\n==============================\n";
        cout << "       BASIC CALCULATOR\n";
        cout << "==============================\n";
        cout << "1. Addition (+)\n";
        cout << "2. Subtraction (-)\n";
        cout << "3. Multiplication (*)\n";
        cout << "4. Division (/)\n";
        cout << "5. Modulus (%)\n";
        cout << "6. Exit\n";
        cout << "==============================\n";

        // Get menu choice with validation
        cout << "Enter your choice (1-6): ";

        if (!(cin >> choice)) {
            cout << "Invalid input! Please enter a number from 1 to 6.\n";
            cin.clear();
            cin.ignore(10000, '\n');
            continue;
        }

        // Exit option
        if (choice == 6) {
            cout << "\nThank you for using the calculator!\n";
            break;
        }

        // Validate menu choice
        if (choice < 1 || choice > 6) {
            cout << "Invalid choice! Please select 1 to 6.\n";
            continue;
        }

        // Input numbers
        cout << "Enter first number: ";
        if (!(cin >> num1)) {
            cout << "Invalid input! Please enter a valid number.\n";
            cin.clear();
            cin.ignore(10000, '\n');
            continue;
        }

        cout << "Enter second number: ";
        if (!(cin >> num2)) {
            cout << "Invalid input! Please enter a valid number.\n";
            cin.clear();
            cin.ignore(10000, '\n');
            continue;
        }

        // Perform selected operation
        switch (choice) {

            case 1:
                result = num1 + num2;
                cout << fixed << setprecision(2);
                cout << "Result = " << result << endl;
                break;

            case 2:
                result = num1 - num2;
                cout << fixed << setprecision(2);
                cout << "Result = " << result << endl;
                break;

            case 3:
                result = num1 * num2;
                cout << fixed << setprecision(2);
                cout << "Result = " << result << endl;
                break;

            case 4:
                if (num2 == 0) {
                    cout << "Error: Division by zero is not allowed!\n";
                } else {
                    result = num1 / num2;
                    cout << fixed << setprecision(2);
                    cout << "Result = " << result << endl;
                }
                break;

            case 5:
                // Modulus works with integers
                if (num2 == 0) {
                    cout << "Error: Modulus by zero is not allowed!\n";
                } else {
                    int a = static_cast<int>(num1);
                    int b = static_cast<int>(num2);

                    cout << "Result = " << a % b << endl;
                }
                break;
        }

    } while (true);

    return 0;
}