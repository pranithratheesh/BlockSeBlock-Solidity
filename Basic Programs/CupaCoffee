// SPDX-License-Identifier: MIT
pragma solidity ^0.8.31;

//buy me a cup of coffee

contract Coffee {
       address public Owner;
       uint256 public Coffee_Price = 0.0001 ether;
       mapping (address => uint256) public Coffees_bought;

//Dep event
event Deposited (address indexed buyer, uint256 Qty , uint256 Amount);
//withdrawal event
event withdrawn(address indexed Owner, uint256 Amount);

constructor(){
    Owner = msg.sender ;
}
  
modifier onlyOwner(){
      require(msg.sender == Owner , "Only owner can call the function");
      _;
}
    //Function to buy Coffee

function BuyCoffee(uint256 Qty) external payable{

  require(Qty>0 ,"Qty should be greater than 0");
  uint256 totalcost = Coffee_Price * Qty ; 
  require(msg.value >= totalcost ,"Insufficient amount");
  Coffees_bought[msg.sender ] += Qty ;
  emit Deposited(msg.sender,Qty,totalcost);

} 

function withdraw() external onlyOwner{
    uint256 balance = address(this).balance;  
    require(balance>0,"No balance to withdraw");
    (bool success, ) = Owner.call{value : balance}("");
    require(success ,"Withdrawal failed");
    emit withdrawn(Owner,balance);

}

function getbalance()external view returns(uint256){
       return address(this).balance;
}
}
