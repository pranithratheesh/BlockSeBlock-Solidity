// SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.2;

contract Donation {
    mapping(address => uint256) public donations;
    address public owner;

    event Donated(address indexed donater, uint256 amount);
    event Withdraw(address indexed owner, uint256 amount);

    modifier onlyOwner() {
        require(msg.sender == owner, "Only owner can call");
        _;
    }

    constructor() {
        owner = msg.sender;
    }

    function donate() external payable {
        require(msg.value > 0, "Value should be greater than 0");
        donations[msg.sender] += msg.value;
        emit Donated(msg.sender, msg.value);
    }

    function withdraw(uint256 amount) external onlyOwner {
        uint256 balance = address(this).balance;
        require(amount <= balance, "Insufficient Balance");

        (bool success, ) = payable(owner).call{value: amount}("");
        require(success, "Transfer failed");

        emit Withdraw(owner, amount);
    }

    function getBalance()external view returns (uint256){
         return address(this).balance;
    }
}
