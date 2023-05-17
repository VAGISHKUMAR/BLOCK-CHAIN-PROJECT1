pragma solidity ^0.8.0;
contract DepositWithdraw {
    mapping(address => uint256) public deposits;
    function deposit() public payable{deposits[msg.sender] += msg.value; }
    function withdraw(uint256 amount) public {
        require(deposits[msg.sender] >= amount);
        deposits[msg.sender] -= amount;
        msg.sender.transfer(amount);}}
