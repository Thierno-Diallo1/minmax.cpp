/*

Author: thierno diallo
Course: CSCI-136
Assignment:Lab 3a

Write a program  ask for a date and writes the water storage
*/


#include <cstdlib>
#include <fstream>
#include <iostream>
using namespace std;

int main() {
	ifstream fin("Current_Reservoir_Levels.tsv");
	if (fin.fail()) {
		cerr << "File cannot be opened for reading." << endl;
		exit(1); // exit if failed to open the file
	}
	string junk;        // new string variable
	getline (fin, junk); // read one line from the file 

	string date;
	double eastSt,eastEl,westSt,westEl;
	int starting;
	int ending;

	cout << "starting date is" << endl;
	cin >> starting;

	cout <<"ending date is" << endl;
	cin >> ending;


	while (fin >> date >> eastSt >> eastEl >> westSt >> westEl) { 
		if (eastEl < westEl) {
			cout << date << "west"<< endl;
		}
		else if (eastEl > westEl) {
			cout << date << "east"<< endl;
		}
		else{
			cout << date << "equal"<< endl;
		}
}

	fin.close();
}
