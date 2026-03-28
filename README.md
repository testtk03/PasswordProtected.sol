# PasswordProtected.sol
Base - Smart Contract Deployed by Remix PasswordProtected.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract PasswordProtected {
    bytes32 private passwordHash;

    constructor(string memory _password) {
        passwordHash = keccak256(abi.encodePacked(_password));
    }

    function checkPassword(string memory _password) public view returns (bool) {
        return keccak256(abi.encodePacked(_password)) == passwordHash;
    }
}
