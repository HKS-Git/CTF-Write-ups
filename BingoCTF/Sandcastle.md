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

After knowing this, I thought of breaking the "walls" by dividing the large n with small primes

</div>
