# LARGEPRIME-S
Shows prime numbers in between a billion and a trillion
#include "stdafx.h"
#include <iostream>
#include <fstream>
#include <chrono>

using namespace std;
using namespace std::chrono;

bool is_prime(long long int n)//Function to show if number is prime or not
{
	if (n <= 1)
		return false;

	if (n <= 3)
		return true;

	if (n % 2 == 0 || n % 3 == 0)
		return false;

	for (int i = 5; i * i <= n; i = i + 6)
	{
		if (n % i == 0 || n % (i + 2) == 0)
		{
			return false;
		}
		return true;
	}
	
}



int main()
{
	
	long long int num;
	//do {


		//cout << "Please enter in an number or 0 to exit." << endl;
		//cin >> num;
	auto start = high_resolution_clock::now(); //Start Clock

		for (long long int n=1000000000000000; n< 1000000000001000; n++)	//Loop to check all numbers between quadrillion and quadrillion and a thousand.
		{
			
			//is_prime(n) ? cout << "Prime\t "<< n<<endl : cout << "Not Prime\n";
			
			if (is_prime(n))
			{
				cout << n << endl;
				//cout << n <<"\t\t";
			}

		}
	//} while (num != 0);
		auto stop = high_resolution_clock::now();	//End clock
		auto duration = duration_cast<milliseconds>(stop - start); // Type casting conversion to milliseconds

		cout << "Time taken by function: "
			<< duration.count() << " milliseconds" << endl;

    return 0;
}
