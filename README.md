# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

STEP-1: Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

STEP-2: Initialization
Agree on a large prime number (p) and a primitive root (g) modulo (p), both of which are public values.

STEP-3: Key Exchange Process
Each party selects a private key and calculates their public key using the formula g^private key mod p. Then each party shares their public key with the other party.

STEP-4: Secret Key Computation
Each party computes the shared secret key using the received public key and their own private key.

STEP-5: Security
The security is based on the difficulty of solving the discrete logarithm problem, which makes it hard to derive the private key from public information.

## Program:

```
#include <stdio.h>

long long power(long long a, long long b, long long mod)
{
    long long result = 1;
    while(b > 0)
    {
        if(b % 2 == 1)
        {
            result = (result * a) % mod;
        }
        a = (a * a) % mod;
        b = b / 2;
    }
    return result;
}

int main()
{
    int p = 23;
    int g = 5;
    int a = 6;
    int b = 15;
    printf("DIFFIE HELLMAN KEY EXCHANGE\n");
    long long A = power(g, a, p);
    long long B = power(g, b, p);
    long long key1 = power(B, a, p);
    long long key2 = power(A, b, p);
    printf("\nPublic Value p = %d", p);
    printf("\nPublic Value g = %d", g);
    printf("\n\nPrivate Key User 1 = %d", a);
    printf("\nPrivate Key User 2 = %d", b);
    printf("\n\nPublic Key User 1 = %lld", A);
    printf("\nPublic Key User 2 = %lld", B);
    printf("\n\nShared Secret Key User 1 = %lld", key1);
    printf("\nShared Secret Key User 2 = %lld", key2);
    if(key1 == key2)
    {
        printf("\n\nKey Exchange Successful");
    }
    else
    {
        printf("\n\nKey Exchange Failed");
    }
    return 0;
}
```

## Output:

<img width="1915" height="901" alt="ex10op" src="https://github.com/user-attachments/assets/44506b39-6488-41c6-ad95-96767ca5d10c" />

## Result:
Thus, the implementation of Diffie Hellman Key Exchange Algorithm had been executed successfully.
