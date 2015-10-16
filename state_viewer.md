# State Viewer

This panel is located below the block chain panel, in the scenario view.
Once the blockchain has been run, this panel shows the state of the blockchain.

By state we mean all accounts balance (including contract and normal account), and the storage (global variable of all deployed contract).
The content of this panel is not static, it depends on the selected transaction on the blockchain panel.
The state shown here is the state resulting of the execution of the selected transaction.

![](state_mix.png)

In that case, 2 contracts are deployed, the selected transaction (deployment of testCtr) is the last one. so the state view shows the storage of both TestCtr and BasicContract.

###Display calls

A contract call is a function invokation. This is not a transaction as a contract call cannot change the state.
A contract call is not part of the blockchain but for practical and ux design reason, it is convenient to display calls at the same functional level as a transaction. The JS icon warn you that this is not a transaction but a call.
To show/hide call, click on the menu Scenario -> Display calls.

###Transaction detail

on each transaction click on the arrow on the right corner will expand it and display further information related to the transacations.
 - Input parameters
 - Output parameters
 - Event

It is also possible to edit the transaction (to change parameters for example) or to debug the transactions.
