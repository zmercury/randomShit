## Answers

1. Write a C program to find cube of any number using function.

```c
#include <stdio.h>

int cube(int inputNumber);

int main() {
    int inputNumber, answer;

    printf("Enter the number to find the cube: ");
    scanf("%d", &inputNumber);

    answer = cube(inputNumber);

    printf("The cube of %d is %d\n", inputNumber, answer);

    return 0;
}

int cube(int inputNumber) {
    int result;
    result = (inputNumber * inputNumber * inputNumber);

    return result;
}
```

2. Write a C program to find diameter, circumference and area of circle using functions.

```c 
#include <stdio.h>

#define PI 3.14

int diameter(int mRadius);
int area(int mRadius);
int circumference(int mRadius);

int main() {
    int mRadius, mDiameter, mArea, mCircumference;

    printf("Enter the radius of the circle: ");
    scanf("%d", &mRadius);

    mDiameter = diameter(mRadius);
    mArea = area(mRadius);
    mCircumference = circumference(mRadius);

    printf("The diameter of the circle is %d cm\n", mDiameter);
    printf("The area of circle is %d cm2\n", mArea);
    printf("The circumference of circle is %d cm\n", mCircumference);

    return 0;
}

int diameter (int mRadius) {
    int ans;

    ans = mRadius * 2;

    return ans;
}

int area (int mRadius) {
    int ans;

    ans = PI * mRadius * mRadius;

    return ans;
}

int circumference (int mRadius) {
    int ans;

    ans = 2 * PI * mRadius;

    return ans;
}
```

3. Write a C program to find maximum and minimum between two numbers using functions.

```c
#include <stdio.h>
int maximini(int numberOne, int numberTwo);

int main() {
    int numberOne, numberTwo;

    printf("Enter any two numbers: ");
    scanf("%d %d", &numberOne, &numberTwo);

    if(maximini(numberOne, numberTwo)) {
        printf("%d is greater than %d\n", numberOne, numberTwo);
    } else {
        printf("%d is greater than %d\n", numberTwo, numberOne);
    }

    return 0;
}

int maximini(int numberOne, int numberTwo) {
    int result;

    if ( numberOne > numberTwo ) {
        return 1;
    } else {
        return 0;
    }
}
```

4. Write a C program to check whether a number is even or odd using functions.

``` c
#include <stdio.h>
int oddEven(int number);

int main() {
    int number;

    printf("Enter any number: ");
    scanf("%d", &number);

    if(oddEven(number)){
        printf("%d is even number!", number);
    } else {
        printf("%d is odd number!", number);
    }
}

int oddEven(int number) {
    if (number % 2 == 0) {
        return 1;
    } else {
        return 0;
    }
}
```

5. Write a C program to check whether a number is prime, Armstrong or perfect number using functions.

```c
#include <stdio.h>
#include <math.h>

int checkPrime(int num);
int checkArmstrong(int num);
int checkPerfect(int num);


int main()
{
    int num;
    
    printf("Enter any number: ");
    scanf("%d", &num);
    
    if(checkPrime(num))
    {
        printf("%d is Prime number.\n", num);
    }
    else
    {
        printf("%d is not Prime number.\n", num);
    }
    
    if(checkArmstrong(num))
    {
        printf("%d is Armstrong number.\n", num);
    }
    else
    {
        printf("%d is not Armstrong number.\n", num);
    }
    
    if(checkPerfect(num))
    {
        printf("%d is Perfect number.\n", num);
    }
    else
    {
        printf("%d is not Perfect number.\n", num);
    }
    
    return 0;
}

int checkPrime(int num) 
{
    int i;
    
    for(i=2; i<=num/2; i++)  
    {  
        if(num%i == 0)  
        {
            return 0;
        }  
    } 
    
    return 1; 
}

int checkArmstrong(int num) 
{
    int lastDigit, sum, originalNum, digits;
    sum = 0;
    
    originalNum = num;

    digits = (int) log10(num) + 1;

    while(num > 0)
    {
        lastDigit = num % 10;
        sum = sum + round(pow(lastDigit, digits));
        num = num / 10;
    }
    
    return (originalNum == sum);
}

int checkPerfect(int num) 
{
    int i, sum, n;
    sum = 0;
    n = num;
    
    for(i=1; i<n; i++)  
    {  
        if(n%i == 0)  
        {  
            sum += i;  
        }  
    }
    
    return (num == sum);
}
```

6. Write a C program to find all prime numbers between given interval using functions.

```c
#include <stdio.h>

int findPrime(int, int);

int main() {
    int intervalStart, intervalEnd;

    printf("Enter the start and end of the interval: ");
    scanf("%d %d", &intervalStart, &intervalEnd);

    findPrime(intervalStart, intervalEnd);

    return 0;
}

int findPrime(int intervalStart, int intervalEnd) {
    int primeNumbers, flag_var, i,j;

    for(i=intervalStart+1; i<intervalEnd; ++i)
    {
      flag_var=0;
      for(j=2; j<=i/2; ++j)
      {
         if(i%j==0)
         {
            flag_var=1;
            break;
         }
      }
      if(flag_var==0)
         printf("%d\t",i);
    }
    return 0;
}
```

7. Write a C program to print all strong numbers between given interval using functions

``` c
#include <stdio.h>

long long fact(int num);
int printStrongNumbers(int start, int end);


int main()
{
    int start, end;
    
    printf("Enter the lower limit to find strong number: ");
    scanf("%d", &start);
    printf("Enter the upper limit to find strong number: ");
    scanf("%d", &end);
    
    printf("All strong numbers between %d to %d are: \n", start, end);
    printStrongNumbers(start, end);
    
    return 0;
}

int printStrongNumbers(int start, int end)
{
    long long sum;
    int num;
    
    while(start != end) {
        sum = 0;
        num = start;
        
        while(num != 0) {
            sum += fact(num % 10);
            num /= 10; 
        }

        if(start == sum) {
            printf("%d, ", start);
        }
        
        start++;
    }
}

long long fact(int num)
{
    if(num == 0) {
        return 1;
    } else {
        return (num * fact(num-1));
    }
}
```

8. Write a C program to find power of any number using recursion.

```c
#include <stdio.h>

int power(int n1, int n2);

int main() {
    int base, a, result;
    printf("Enter base number: ");
    scanf("%d", &base);
    printf("Enter power number(positive integer): ");
    scanf("%d", &a);
    result = power(base, a);
    printf("%d^%d = %d", base, a, result);
    return 0;
}

int power(int base, int a) {
    if (a != 0)
        return (base * power(base, a - 1));
    else
        return 1;
}
```

9. Write a C program to find sum of digits of a given number using recursion.

``` c
#include <stdio.h>

int addNumbers(int n);

int main() {

  int num;
  printf("Enter a positive integer: ");
  scanf("%d", &num);
  printf("Sum = %d", addNumbers(num));
  return 0;
}

int addNumbers(int n) {
  if (n != 0)
    return n + addNumbers(n - 1);
  else
    return n;
}
```

10. Write a C program to generate nth Fibonacci term using recursion.

```c

```


11. Write a C program to find LCM of two numbers using recursion.

```c

```



