
#include <iostream>
#include <string>

using namespace std;

class StringTool {
public:
    void string_length() {
        int;
        string str;
        string* ptr = &str;
        cout << "Enter a string: ";
        getline(cin, *ptr);
        cout << "Length of the string is: " << ptr->length() << "\n";
        for (size_t i = 0; i < str.length(); ++i) {
            cout << "Character: " << str[i] << " Address: " << static_cast<void*>(&str[i]) << endl;
        }
    }

    void string_compare() {
        string str1, str2;
        string* p1 = &str1, * p2 = &str2;

        cout << "Enter the first string: ";
        getline(cin, *p1);
        cout << "Enter the second string: ";
        getline(cin, *p2);

        if (*p1 < *p2)
            cout << "The first string is smaller.\n";
        else if (*p1 > *p2)
            cout << "The first string is greater.\n";
        else
            cout << "Both strings are equal.\n";
        for (size_t i = 0; i < str1.length(); ++i) {
            cout << "Character: " << str1[i] << " Address: " << static_cast<void*>(&str1[i]) << std::endl;
        }
        for (size_t i = 0; i < str1.length(); ++i) {
            cout << "Character: " << str1[i] << " Address: " << static_cast<void*>(&str1[i]) << std::endl;
        }
    }

    void string_concatenate() {
        string str1, str2;
        string* p1 = &str1, * p2 = &str2;

        cout << "Enter the first string: ";
        getline(cin, *p1);
        cout << "Enter the second string: ";
        getline(cin, *p2);

        cout << "Concatenated string: " << *p1 + *p2 << "\n";
        cout << " Memory Address of first string is " << &str1 << " and second string is " << &str2;
    }
};

int main() {
    StringTool tool;
    string choice;

    do {
        int option;
        cout << "What do you want to do?\n";
        cout << "1. Find the string length\n";
        cout << "2. Compare two strings\n";
        cout << "3. Concatenate twos strings\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> option;
        cin.ignore();

        switch (option) {
        case 1:
            tool.string_length();
            break;
        case 2:
            tool.string_compare();
            break;
        case 3:
            tool.string_concatenate();
            break;
        case 4:
            return 0;
        default:
            cout << "Invalid choice.\n";
        }

        cout << "\nTry again?[Y/N] ";
        cin >> choice;
        cin.ignore();

    } while (choice == "Y" || choice == "y");

    return 0;
}
