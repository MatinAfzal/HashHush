# HashHush

![images](osan.jpg)

**This program helps you keep your identity secure on the internet after you hacked the whole country’s digital infrastructure.** <br />

The old‑school proof is silent: a lit cigarette in the dark, no rush, no fear. Interception is temporary — smoke is permanent. <br />
I know there are PGP and many other tools, algorithms, and private‑key systems, but I decided to create my own. I think it is cooler — although also weaker.

## ☰ Menu

- [About](#hashhush)
- [How It Works](#how-it-works)
- [Identity Chain](#identity-chain-example)
- [Security Notes](#about-security)
- [Download & Build](#download--build)
- [Future Improvements](#future-improvements)

---

## How it works

This program takes some keywords from you called **Identification Keys** and mixes those keys into randomly generated strings called **(HUSH)**.  
It then converts each of them into **SHA-512 (HASH)**.

It repeats this process multiple times (as many as you want) and then gives you something like this:

```
********************HashHush V1.0.0**********************
The owner of these hashes is the person behind the mask.
*********************************************************
PAGE ID:
ef1ac24576ec5de394f9fa7db0e640efde6a4f4a5221b85456cc28c2a048adc612c13d8f457257fc7d9c03525d188080bf625471447005caf8c63237619c2c20
*********************************************************
e92d25862845511da0594fe8cdde3ef0fced8156e37e6243b1b3143dbf8f2ba9990b179f264599f87128b360c1aa1b55c99618dfc562a005ee46711dba13c8b7
407644962434b7638a4ab996b6744117905f94040ebcd524445836c9c788bed29ff7e00a6cc3e3110021b049dd968ce07eed78285919b856a7301e496793aca7
78046960f829449286720eb9448b4e6fa54df5f15632cd56aacede91b7e355a18fc5f7afb533079861c131c072743466e8e9ac9872d99aa688adea9e4b404246
9d028799ece68e619d68079078f3588c5538338cf3111a3292ef75e90946c0776374793cdc0f9ec6c3c0c95810e6e4b001482cdf1a881c7a49be701b0ce1c423
c85c6ab0524da544d2529b603606095d1044b50b49fe29c007d71e6c0316c9aa7916a5811c94b78e23a42bc0817ac3d6f9e0dc1eaab757af5d17b6d698ba03ef
*********************************************************
The owner of these hashes is the person behind the mask.
*********************************************************
```

These are the 5 hashes created from randomly generated HUSH strings mixed with your keys.  
You can share the message above anywhere on the internet, in any way you want.

As you can see, there is a **PAGE ID**, which is the SHA-512 hash of all 5 hashes combined. This helps others verify your identity more easily.

The program also gives you something like this:

```
********************HashHush V1.0.0**************************
The owner of these hushes is the creator of the linked page.
*************************************************************
PAGE :
ef1ac24576ec5de394f9fa7db0e640efde6a4f4a5221b85456cc28c2a048adc612c13d8f457257fc7d9c03525d188080bf625471447005caf8c63237619c2c20
Seed: 2626541424
Count: 5
Length: 30
Identification keys:
Matin
Afzal
Asr
********************HashHush V1.0.0**************************
The owner of these hushes is the creator of the linked page.
*************************************************************
```

This is your **private key** and proves your identity, so keep it secret.  
The PAGE number is included so you (or others, if you share it) know exactly which message this key belongs to.

You can also see **Seed, Count, Length, and Identification Keys** — these are like your passport.

- **Seed** = exact time when the HUSH strings were generated × program PID  
- This value is fed into `srand()` and reproduces the exact pseudo-random sequence  
- The program regenerates the same number (**Count**) of random strings with the same **Length**  
- Your Identification Keys are inserted randomly into those strings  
- All hashes are recomputed again to regenerate the same PAGE ID  

By inputting passport values, program will execute an identity check:
```
HASH: e92d25862845511da0594fe8cdde3ef0fced8156e37e6243b1b3143dbf8f2ba9990b179f264599f87128b360c1aa1b55c99618dfc562a005ee46711dba13c8b7 | HSUH: dAp#PgAfzalMatinrHHLEBLAsrfo:LwPq8/(HEJWqZ5
HASH: 407644962434b7638a4ab996b6744117905f94040ebcd524445836c9c788bed29ff7e00a6cc3e3110021b049dd968ce07eed78285919b856a7301e496793aca7 | HSUH: KkAsrUJbZAfzalTer7bS*#JQ(~aMatin2)kw3:jQuCm
HASH: 78046960f829449286720eb9448b4e6fa54df5f15632cd56aacede91b7e355a18fc5f7afb533079861c131c072743466e8e9ac9872d99aa688adea9e4b404246 | HSUH: l3oMiWh52tI+:_9Afzalzx,muMaAsrtin?RJ+5JKNif
HASH: 9d028799ece68e619d68079078f3588c5538338cf3111a3292ef75e90946c0776374793cdc0f9ec6c3c0c95810e6e4b001482cdf1a881c7a49be701b0ce1c423 | HSUH: /n]MatiAsrnN^lwC#Ml1!%GUYAfzalg[$bJ<Ck[;imY
HASH: c85c6ab0524da544d2529b603606095d1044b50b49fe29c007d71e6c0316c9aa7916a5811c94b78e23a42bc0817ac3d6f9e0dc1eaab757af5d17b6d698ba03ef | HSUH: X:EU:%f$]txlzRfjAfzal$Vum#_'n's0Il}MAsratin
If the regenerated PAGE matches the shared PAGE, the identity is verified.

*************************************************************
If the owners hashes are marked with page number
 PAGE: [ ef1ac24576ec5de394f9fa7db0e640efde6a4f4a5221b85456cc28c2a048adc612c13d8f457257fc7d9c03525d188080bf625471447005caf8c63237619c2c20 ]
 then the information is attributed to him.
*************************************************************
```

**If the regenerated PAGE matches the shared PAGE, the identity is verified.**

## Identity Chain Example

This allows you to create a chain of identity messages like this:

```
Hey again, I'm the dude who hacked the whole country and I'm keeping my identity using this system.

My Previous Message:
********************HashHush V1.0.0**************************
The owner of these hushes is the creator of the linked page.
*************************************************************
PAGE :
ef1ac24576ec5de394f9fa7db0e640efde6a4f4a5221b85456cc28c2a048adc612c13d8f457257fc7d9c03525d188080bf625471447005caf8c63237619c2c20
Seed: 2626541424
Count: 5
Length: 30
Identification keys:
Matin
Afzal
Asr
********************HashHush V1.0.0**************************
The owner of these hushes is the creator of the linked page.
*************************************************************

My Next Message:
********************HashHush V1.0.0**********************
The owner of these hashes is the person behind the mask.
*********************************************************
PAGE ID:
983d8059179957cdd7539adf95a70f5e2316101b41e663ffa4c455c1575da84ccb9b28782c872974451dc469d06e1ff2cbb742c7f274d407963def6c1f8658a8
*********************************************************
bc4053333106609887e1ceb6819d5a58c36ab31effe4d89dccdddd00e69dde2d103f1b4f407583c5ab3afb5a65bec9c5f0aab2357a8d9a786a326d30e2afe5eb
5a2c2272eadec12001ed2d99e9fdaaa2c3da9d405afbf0c61cdac907869f7a4e471c196b67a9159b2a71d1039dc2f622e1f7a131ce837d5bb8f7da3f09cb03c2
4b1305edbd501c07a994d666d30f4004ec360ee3ef1e7d9ea7210791d53f8287eb7672eb045b468807a5450c97fe7b784728a4f3df868c7f0d463a0879d50b8f
4727a1f69ae5fc2c3ee2817f56af1d8dbcba57dea393063fc7f141c47cf30f0049b5df6a52b6d2f81e3fe83d8bd100c4c60e33b7525e5e2194f7ec5fe7f02a17
48f9477befa8adb2fe8bdad5f64e4463ed057f52bbc5c183415a048353585eaef692b02806fc74f36e34e2555c5d32f4a803a6b7f6ad0305fdf069a6d4fb6f2a
*********************************************************
The owner of these hashes is the person behind the mask.
*********************************************************
```

In this way, you create a secure identity chain.

## About Security

Here are some notes for anyone trying to break **HashHush V1.0.0**:

Since the program uses `srand()` (which is usually 32-bit), multiplying time by PID does not significantly increase randomness. <br />
The total number of possible pseudo-random sequences is: **4,294,967,295**

Because the program generates random strings starting from `n0` of the sequence, then uses `n1 … n(keywords)` to randomly place the keywords — and repeats the same process for other HUSH strings — an attacker could theoretically try all **4,294,967,295** seeds. However, they would only reconstruct the **first hash** initially, then try to detect patterns to find the rest.

The attacker would also need an approximate number of Identification Keys (for example, 3-10). Knowing this makes the attack easier — but it is still difficult to fully intercept the identity.

## Download & Build

Clone the repository:

```bash
git clone https://github.com/MatinAfzal/HashHush
```

Compile:
```bash
g++ HashHush.cpp -o HashHush.exe
```

## Future Improvements

I plan to add more security features such as:

- Better seeding and randomness  
- Random `n(STEP)` sampling from the series  
- RNG warm-up  
- Salt support  
- And more
