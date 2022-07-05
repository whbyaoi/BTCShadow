## ShadowTransaction

|  Name   | Type  | Description|
|  ----  | ----  | ---- |
| blockHeight  | int | height of the block where transaction is in  |
| blockHash  | str | hash value of the block where transaction is in |
| blockTime | int | time of the block where transaction is in. It's timestamp |
|fee|float| fee of transaction|
|hash|str|hash value of transaction|
|inputsCount|int||
|inputsValue|float||
|outputsCount|int||
|outputsValue|float||
|isCoinbase|bool|whether transaction is the first in one block|
|allInputsAddress|list(str)||
|allOutputsAddress|list(str)||
|allInputsAccount|list(ShadowAccount)||
|allOutputsAccount|list(ShadowAccount)||
|outputs|list(ShadowOutput)||
|inputs|list(ShadowInput)||
|allAddress|function(set(str))|return all address in transaction|

## ShadowInput

|  Name   | Type  | Description|
|  ----  | ----  | ---- |
| address  | str | address in input which is "" if it's in a coinbase transaction |
| prevHash  | str | the source of input which is "" if it's in a coinbase transaction |
| value | float |  |
| transaction | ShadowTransaction | The transaction containing it |

## ShadowOutput

|  Name   | Type  | Description|
|  ----  | ----  | ---- |
| address  | str | address in output |
| spentByTx  | str | the transaction of output to go, which is "" if it's not spent |
| value | float |  |
| transaction | ShadowTransaction | The transaction containing it |

## ShadowAccount

|  Name   | Type  | Description|
|  ----  | ----  | ---- |
| address  | str | address of the ShadowAccount |
| transactions  | dict(str:ShadowTransaction) | the dict containing transactions related to the ShadowAccount |
| inDegree | int | the in-degree of point related to the ShadowAccount in graph |
|outDegree|int| the out-degree of point related to the ShadowAccount in graph|
|loopDegree|int|the loop-degree of point related to the ShadowAccount in graph|
|transactionAsInput|function(list(ShadowTransaction)||
|transactionAsOutput|function(list(ShadowTransaction)||
|transactionOnlyAsInput|function(list(ShadowTransaction)||
|transactionOnlyAsOutput|function(list(ShadowTransaction)||


## AccountPoint

|  Name   | Type  | Description|
|  ----  | ----  | ---- |
| centerX  | float | x of position (x, y) |
| centerY  | float | y of position (x, y) |
| label | str | label of point |
| edges | list(MyEdge) | list containing edges |
| Account | ShadowAccount | Corresponding account |

## TxPoint

|  Name   | Type  | Description|
|  ----  | ----  | ---- |
| centerX  | float | x of position (x, y) |
| centerY  | float | y of position (x, y) |
| label | str | label of point |
| edges | list | list containing edges |
| transaction | ShadowTransaction | Corresponding transaction |

## MyEdge

|  Name   | Type  | Description|
|  ----  | ----  | ---- |
| point1  | AccountPoint or TxPoint | one of two point |
| point2  | AccountPoint or TxPoint | one of two point |
| transactions | list(ShadowTransaction) | a edge can contain more than one transactions in isomorphic graph |

## BitcoinDataset

|  Name   | Type  | Description|
|  ----  | ----  | ---- |
|  transactions  | dict(str:ShadowTransaction)  | ---- |
| accounts  | dict(str:ShadowAccount) | ---- |

