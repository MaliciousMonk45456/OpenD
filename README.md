# OpenD

## web3 decentralised application run on different canisters using motoko language backend and react frontend which can be deployed to the Internet computer which is a blockchain enabling developers to build deploy canisters on.
## Here I made a clone of OpenSea website that controls minting, buying, viewing, selling of NFTS and transfers the amount from a hardcoded party wallet to another user who owns the NFT's wallet This transfer of amount is implemented by another motoko code written that is  token which handles the balances and gives out the custom crypto-coins to first time user (this can be implemented by using login usinginternet identity also) 

1. First install all required dependencies
```
npm i
```
2. Here we also require the token application available on my repo so we will have to delete the .dfx folder from both of these folders if either of them was run before.

3. start local dfx

```
dfx start --clean
```

4. Run NPM server

```
npm start
```

5. Deploy canisters

```
dfx deploy opend
```

6. Now for testing the functionality we can create a demo NFT by some other user which we can buy.
```
dfx canister call opend mint '(vec {137; 80; 78; 71; 13; 10; 26; 10; 0; 0; 0; 13; 73; 72; 68; 82; 0; 0; 0; 10; 0; 0; 0; 10; 8; 6; 0; 0; 0; 141; 50; 207; 189; 0; 0; 0; 1; 115; 82; 71; 66; 0; 174; 206; 28; 233; 0; 0; 0; 68; 101; 88; 73; 102; 77; 77; 0; 42; 0; 0; 0; 8; 0; 1; 135; 105; 0; 4; 0; 0; 0; 1; 0; 0; 0; 26; 0; 0; 0; 0; 0; 3; 160; 1; 0; 3; 0; 0; 0; 1; 0; 1; 0; 0; 160; 2; 0; 4; 0; 0; 0; 1; 0; 0; 0; 10; 160; 3; 0; 4; 0; 0; 0; 1; 0; 0; 0; 10; 0; 0; 0; 0; 59; 120; 184; 245; 0; 0; 0; 113; 73; 68; 65; 84; 24; 25; 133; 143; 203; 13; 128; 48; 12; 67; 147; 94; 97; 30; 24; 0; 198; 134; 1; 96; 30; 56; 151; 56; 212; 85; 68; 17; 88; 106; 243; 241; 235; 39; 42; 183; 114; 137; 12; 106; 73; 236; 105; 98; 227; 152; 6; 193; 42; 114; 40; 214; 126; 50; 52; 8; 74; 183; 108; 158; 159; 243; 40; 253; 186; 75; 122; 131; 64; 0; 160; 192; 168; 109; 241; 47; 244; 154; 152; 112; 237; 159; 252; 105; 64; 95; 48; 61; 12; 3; 61; 167; 244; 38; 33; 43; 148; 96; 3; 71; 8; 102; 4; 43; 140; 164; 168; 250; 23; 219; 242; 38; 84; 91; 18; 112; 63; 0; 0; 0; 0; 73; 69; 78; 68; 174; 66; 96; 130;}, "CryptoDunks #1123")'
```

7. List the item into mapOfListings: replace the principal with whatever you get in previous step

```
dfx canister call opend listItem '(principal "rdmx6-jaaaa-aaaaa-aaadq-cai", 2)'
```

8. Get OpenD canister ID:

```
dfx canister id opend
```

9. Transfer NFT to OpenD: (in principal "enter dfx canister id opend" and in call "enter pricipal we get in first step")

```
dfx canister call rdmx6-jaaaa-aaaaa-aaadq-cai transferOwnership '(principal "rrkah-fqaaa-aaaaa-aaaaq-cai", true)'
```

10. Now we can go over to the folder where token is stored.

11. Deploy token canister

```
dfx deploy
```

12. Start frontend

```
npm start
```

13. Run in token folder
```
dfx canister id token
```

14. Set the token canister id into the <REPLACE WITH TOKEN CANISTER ID> in handlebuy

```
const dangPrincipal = Principal.fromText("<REPLACE WITH TOKEN CANISTER ID>");
```

15. Now follow the steps in README of token repo to transfer half a billion tokens to the canister from where we can collect the DAMN tokens

16. We can visit https://localhost:8080 and https://localhost:8081 to visit both our websites.
    
