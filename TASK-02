#include <iostream>
using namespace std;

double celsiusToFahrenheit(double celsius) {
    return (celsius * 9 / 5) + 32;
}

double celsiusToKelvin(double celsius) {
    return celsius + 273.15;
}

double fahrenheitToCelsius(double fahrenheit) {
    return (fahrenheit - 32) * 5 / 9;
}

double fahrenheitToKelvin(double fahrenheit) {
    return fahrenheitToCelsius(fahrenheit) + 273.15;
}

double kelvinToCelsius(double kelvin) {
    return kelvin - 273.15;
}

double kelvinToFahrenheit(double kelvin) {
    return celsiusToFahrenheit(kelvinToCelsius(kelvin));
}

int main() {
    int inputScale, outputScale;
    double temperature;

    cout << "Temperature Conversion Program" << endl;
    cout << "Choose the input temperature scale:" << endl;
    cout << "1. Celsius\n2. Fahrenheit\n3. Kelvin\n";
    cin >> inputScale;

    cout << "Enter the temperature: ";
    cin >> temperature;

    cout << "Choose the output temperature scale:" << endl;
    cout << "1. Celsius\n2. Fahrenheit\n3. Kelvin\n";
    cin >> outputScale;

    double convertedTemp;

    if (inputScale == 1) {
        if (outputScale == 1) convertedTemp = temperature;
        else if (outputScale == 2) convertedTemp = celsiusToFahrenheit(temperature);
        else if (outputScale == 3) convertedTemp = celsiusToKelvin(temperature);
    } else if (inputScale == 2) {
        if (outputScale == 1) convertedTemp = fahrenheitToCelsius(temperature);
        else if (outputScale == 2) convertedTemp = temperature;
        else if (outputScale == 3) convertedTemp = fahrenheitToKelvin(temperature);
    } else if (inputScale == 3) {
        if (outputScale == 1) convertedTemp = kelvinToCelsius(temperature);
        else if (outputScale == 2) convertedTemp = kelvinToFahrenheit(temperature);
        else if (outputScale == 3) convertedTemp = temperature;
    } else {
        cout << "Invalid input scale!" << endl;
        return 1;
    }

    cout << "Converted temperature: " << convertedTemp << endl;

    return 0;
}
