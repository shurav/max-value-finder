# max-value-finder
This program asks the user to enter a list of integer values stored in an array and determines the maximum value

#include <iostream>

using namespace std;

int main()
{
    int max;
    int maxValue;
    cout << "Enter the maximum number of values in an integral data set: ";
    cin >> max;
    while(cin.fail())
    {
        cin.clear();
        cin.ignore(100, '\n');
        cout << "Enter a proper value: ";
        cin >> max;
    }
    int array[max];
    for (int i = 0; i < max; i++)
    {
        cout << "Enter value " << i+1 << ": ";
        cin >> array[i];
        while(cin.fail())
        {
            cin.clear();
            cin.ignore(100, '\n');
            cout << "Enter a proper value: ";
            cin >> array[i];
        }
    }
    int arrayMax = array[0];
    int *arrayMaxPtr = &arrayMax;
    for (int i = 0; i < max-1; i++)
    {
        if (arrayMax < array[i+1])
        {
            arrayMax = array[i+1];
        }
    }
    cout << "The largest integer value in the data set is " << *arrayMaxPtr << " located in address: " << arrayMaxPtr << endl;
    return 0;
}
