#include <iostream>
#include <math.h>
using namespace std;

enum CARS{ ВАЗ_2107 = 1, ГАЗ_13, ЗАЗ_965,ПАЗ_2125, ЗИЛ_111 = 0 };
CARS operator+(const CARS& m, const int& b)
{
CARS t = CARS (b + m);

return(t = CARS(t % 5));
}

CARS operator+(const int& b, const CARS& m)
{
return (m + b);
}
CARS operator++(CARS& m)
{
return (m = CARS(m + 1));
}
CARS operator++(CARS& m, int)
{
CARS t = m; m = CARS(m + 1);
return t;
}
void print(const CARS& d)
{
string CAR[5] =
{
"ВАЗ-2107","ГАЗ-13","ЗАЗ-965","ПАЗ-2125","ЗИЛ-111"
};
cout « CAR[d] « endl;
};

int main()
{
setlocale(LC_ALL, "Rus");

CARS m = ИЖ_2125;
print(m + 1);
print(2 + m);
print(operator+(m, 1));
print(operator+(2, m));
m++;
print(m);
print(++m);
print(operator++(m));
print(operator++(m, 0));
print(m);

system("pause");
}
