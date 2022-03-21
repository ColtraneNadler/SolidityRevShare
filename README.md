![alt text](https://i.imgur.com/NrH7kyC.jpg)

This revenue share contract follows the MasterChev approach to time based reward allocation, but with a non custodial ERC20 contract. This allows you to create vesting agreements with any ERC20 contract.

### web3.js example
```
	let erc20contract = new web3.eth.Contract(erc20abi, erc20address);
	try {
		await erc20contract.methods.transfer(revShareAddress, amount)
		.send({ from: userAccount });
	} catch(err) {
		return console.error(err);
	}

	let revShareContract = new web3.eth.Contract(revShareAbi, revShareAddress);
	revShareContract.methods.updateRewardPerSec()
	.send({ from: userAccount });
```

### Period
Update the period to change the rate at which the rewards are accrued.
```
    function updatePeriod(uint _period) public onlyOwner {
        period = _period;
    }
```

