
// ConsoleApplication3.cpp : Defines the entry point for the console application.
//

#include "stdafx.h"
#include <windows.h>
int rekursiq(int n)
{
	if (n <= 1) return 1;
	return rekursiq(n - 1) + rekursiq(n - 2);
}

int iteraciq(int n)
{
	int i, f1 = 1, f2 = 1, f;
	for (i = 2; i <= n; i++)
	{
		f = f1 + f2; f2 = f1; f1 = f;
	}
	return f;
}
int _tmain(int argc, _TCHAR* argv[])
{
	int t1 = 0;
	int t2= 0;
	int vreme_rekursiq = 0;
	t1 = GetTickCount();
	rekursiq(40);
	t2 = GetTickCount();
	vreme_rekursiq=t2 - t1;
	printf("rekursiq---> %d", vreme_rekursiq);
	printf("\n");
	int t3 = 0;
	int t4 = 0;
	
	int vreme_iteraciq = 0;
	t3 = GetTickCount();
	iteraciq(40);
	t3 = GetTickCount();
	vreme_rekursiq = t4 - t3;
	printf("iteraciq---> %d", vreme_iteraciq);
	printf("\n");
	return 0;
}

