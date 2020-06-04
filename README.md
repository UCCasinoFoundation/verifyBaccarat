# UC Casino Foundation

## Provably Fair ##

UC Casino Foundation's random number generator (RNG) facilitates SHA256 hash function and uuid4. First of all, for provable fairness, RNG generates the list of hashes. Each element in the list is the hash of the previous hash. The first hash is generated by uuid4. Then the list is reversed so that it provides the consecutively verifiable hash list, i.e. hashing the current hash outputs of the previous game’s hash. This reversed hash list is uncheatable and easily verifiable because no one can predict the next hash in the reversed hash list in the reasonable time and anyone can verify the current hash is valid by hashing the current hash. Each game uses a random number for its own use. For example, Baccarat uses a random number to shuffle the eight-deck shoe.


## verifyBaccarat

```
function verifyBaccarat(hash, salt): gameResult {
      const hashList = makeHashList(hash, salt);
      const eight-deck-shoe = makeShoe(hashList);
      const gameResult = simulateBaccarat(eight-deck-shoe);
      return gameResult;
}
```

When the makeHashList() function is called, given the hash and salt, it generates 52 * 8 hashes by hashing the previous hash. Then, makeShoe() function makes the shuffled eight-deck shoe with the hash list using the well-known Fisher–Yates shuffle algorithm. When the simulateBaccarat() function is called, it proceeds throughout the multiple steps until the shoe ends. For verification of a game result with your hash and salt, please refer to Verify Baccarat.

**UC Casino Foundation**
https://uccasino.org
*contact@uccasino.org*
