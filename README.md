# hola

#include <iostream>
#include <sstream>
#include <string>
#include <cstdlib>
#include <cmath>

using namespace std;

// Headers
string toString (double);
int toInt (string);
double toDouble (string);
void primesinRange(int n);

int main() {
    // Te da los numero primos menores a lo que seleccionaste
    int n;
    
    cout << "Dame los numero primos mas pequeños que;" << endl;
    cin >> n;
    cout << "lista de todos lo nmeros primos mas pequeños que" << toString(n) << endl;
    primesinRange(n);
    return 0;
}

void primesinRange(int n) {
    double factores, k;
    
    factores = 1;
    for (k = 2; k <= n; k++) {
        factores = factores * (k - 1);
        if ((factores + 1) % k == 0) {
            cout << k << endl;
        }
    }
}

// The following implements type conversion functions.
string toString (double value) { //int also
    stringstream temp;
    temp << value;
    return temp.str();
}

int toInt (string text) {
    return atoi(text.c_str());
}

double toDouble (string text) {
    return atof(text.c_str());
}
