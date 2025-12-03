<div align="justify">

# BingoCTF - Sandcastle Write-up (Challenge Creator: @ransion) 

<div align="center">
<img src="./assets/Sandcastle/SandcastleQuestion.png" 
     alt="Question Description" 
     style="display: block; margin: 0 auto;" 
/>
</div>

> "I built this sandcastle to protect the flag. But the walls are just sand." 

**Flag Format:** `BINGOCTF{flag}`

---

This challenge is a crytography challenge related to RSA. 

Given a text file containing the vlaues of e, n, and c.

>e = 65537
>
>n = 642357873091603463764734869345408116782823370659539361740349721231972127853142360071989379920603126962...
>
>c = 298418186969057703435185628502383880046593036913842405146545631349909408382695212702150885976806096263...

[sandcastle.txt](https://github.com/user-attachments/files/23873405/sandcastle.txt)

What makes this challenging is because of the large vlaue of n (157826 digits), A normal RSA modulus, n is usually around 2048 bits, around 600 digits.

Given the susiciously large RSA modulus, n, I start by trying to use online factoring tools to try and get n to a smaller number, but no online tool can handle the large number.

The reason for this is likely because these online tools assumes RSA is formed by **2 large primes**.

Going back to the Challenge description "the walls are just sand" hints that the "walls", n, is just "sand", lots of smaller primes.

After knowing this, try breaking the "walls" by dividing the large n with small primes (3, 5, 7, 11, ...).

---
<h2>Step 1: Start by test using division with small primes using python. </h2>

```
def factor_small_primes(n, limit=300):
    factors = {}
    tmp = n

    # Try all primes between 2 and 300
    for p in primerange(2, limit + 1):

        # If p divides the current value of n
        if tmp % p == 0:
            count = 0

            # Keep dividing until p no longer fits
            while tmp % p == 0:
                tmp //= p
                count += 1

            # Store p^count
            factors[p] = count
            print(f"[+] Found factor: {p}^{count}")

    # Return the factorization and any leftover remainder
    return factors, tmp
```
The function returns: 
- A dictionary of all discovered prime factors (p<sup>k</sup>)
- Any remainder left after dividing (should be 1 if fully factored)

Once n is factored, we can compute **Euler’s Totient, 𝜙(n)**:

$$
𝜙(𝑝^𝑘) = 𝑝^{𝑘−1}(𝑝−1)
$$

p = a small prime factor of n

k = how many times p divides n

---
<h2>Step 2: Computing Euler's Totient ϕ(n)</h2>

```
def compute_phi(factors):
    phi = 1
    for p, k in factors.items():
        phi *= (p ** (k - 1)) * (p - 1)
    return phi
```

Since n is made of many prime powers:

$$
n = p_1^{k_1} \cdot p_2^{k_2} \cdots
$$

$\phi(n)$ is the product of each individual totient:

* Compute the totient for each $p^k$
* Multiply everything together

---
<h2>Step 3: </h2>

```
def crt(mod_res_pairs):
    # Compute the full modulus (product of all moduli)
    M = 1
    for m, _ in mod_res_pairs:
        M *= m

    result = 0

    for m, r in mod_res_pairs:
        Mi = M // m               # Partial modulus
        inv = pow(Mi, -1, m)      # Modular inverse
        result = (result + r * Mi * inv) % M

    return result
```


</div>
