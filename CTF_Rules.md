# CTF Rules

## Challenge 1
1. You can't mint more NFTs as the admin to any Staker
2. Inflate the staking weight of Staker1 to 10

- Use the next function to test your answer for the CTF. Add it to the [Exploit.t.sol file of the Challenge 1](https://github.com/0xStalin-eth/CTF/blob/main/test/Challenge1/Exploit.t.sol).
```solidity
    function test_ctf_answer() public {
        //@audit-info => Code the exploit here

        // post checks //
        vm.expectRevert();
        // validate no new mints
            // must revert because there should be only 2 LicenseNFTs
        licenseContract.ownerOf(3);

        //@audit-info => Staker1 must have inflated its weight to 10
        assertEq(stakingManager.stakersWeight(staker1), 10);
    }
```