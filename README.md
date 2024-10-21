# Diffie-Hellman-Key-Exchange-Algorithm
## Aim:
  To implement Diffie Hellman Key exchange algorithm.
## Algorithm:
1.Agree on Public Keys: Choose prime number P and primitive root G.

2.Generate Private Keys: Alice chooses a, Bob chooses b.

3.Calculate Public Keys: Alice computes x = Ga mod P, Bob computes y = Gb mod P.

4.Exchange Public Keys: Alice and Bob exchange x and y.

5.Compute Shared Secret: Alice computes ka = ya mod P, Bob computes kb = xb mod P.

## Program:
```
#include <math.h>
#include <stdio.h>
// Power function to return value of a ^ b mod P
long long int power(long long int a, long long int b,long long int P)
{
    if (b == 1)
    return a;
    else
    return (((long long int)pow(a, b)) % P);
}
// Driver program
int main()
{
    long long int P, G, x, a, y, b, ka, kb;
    // Both the persons will be agreed upon the
    // public keys G and P
    printf("\n                  ****Diffie-Hellman Key Exchange algorithm\n\n");
    printf("\n\nEnter the value of P: ");
    scanf("%lld",&P); // A prime number P is taken
    printf("The value of P: %lld\n", P);
    printf("Enter the value of G (Primitive root of P): ");
    scanf("%lld",&G); // A primitive root for P, G is taken
    printf("The value of G: %lld\n\n", G);
    // Alice will choose the private key a
    a = 4; // a is the chosen private key
    printf("The private key a for Alice : %lld\n", a);
    x = power(G, a, P); // gets the generated key
    // Bob will choose the private key b
    b = 3; // b is the chosen private key
    printf("The private key b for Bob : %lld\n\n", b);
    y = power(G, b, P); // gets the generated key
    // Generating the secret key after the exchange
    // of keys
    ka = power(y, a, P); // Secret key for Alice
    kb = power(x, b, P); // Secret key for Bob
    printf("Secret key for the Alice is : %lld\n", ka);
    printf("Secret Key for the Bob is : %lld\n", kb);
    return 0;
}
```
## Output:
![{B668F6A5-7275-4C5E-9FB3-E21E417C6BC1}](https://github.com/user-attachments/assets/c08895dd-cb3c-4d0b-bd13-c01e57bddbb1)
## Result:
 Thus the program for Diffie hellman key exchange is implemented successfully.
