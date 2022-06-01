# BTCShadow
BTC Shadow is a highly interactive tool for analyzing and exploring bitcoin data in graph form. Currently, the BTC Shadow is updating. But you can also utilize it.

## Loading data
BTC Shadow supports only one type of bitcoin data, which is obtained by crawling the [website] in JSON format. You can click File - Add and then choose a folder witch contains blocks folders. They look like these below.

![Folder containing blocks](Images/figure1.png)![Folder containing blocks](Images/figure2.png)

And after choosing the number of blocks loaded, the data will be stored in monitor.


## Monitor
The monitor will be created when loading the data or other operations that generating data. It's a list view that shows addresses and hash value of transactions.

![monitor](Images/monitor.png)

In this module, you can:
+ Delete addresses. If all addresses in one transaction are deleted, the transaction will also be deleted.
+ Copy the hash value of selected address.
+ Update bound graph page (<font color="#dd0000" size=2>Warning: The layout of graph must be generated manually. It can't generate automatically.</font>).
+ Create island. Generate the biggest connected graph of selected address.
+ Locate in. Find where the selected address is in any graph pages.
+ Add to monitor. Add the selected address to another monitor.

## Graph page
When call *Update bound page* function of monitor, it will create a corresponding graph page in center. Each monitor corresponds to each graph page.

![two graph types](Images/two graph types.png)
Graph page aims to show the graph of bitcoin data in isomorphic or heterogeneous form. 

In an isomorphic graph, white node represents account and cyan line represents flow of bitcoins. In a heterogeneous graph, white node represents account, 
yellow node represents transaction, green line represents the flow of bitcoins from transaction to account, red line represents the flow of bitcoins from account to transaction and purple line represents the bidirectional.

![graph](Images/graph.png)

In this module, you can:
+ Scroll the wheel of mouse to zoom view.
+ Click with left mouse key and drag mouse to drag the view
+ Click with left mouse key on node to select a node.
+ Locate selected node.
+ Delete selected node.
+ Add selected node to monitor. 
+ Create N-hop graph of selected node.
+ Create island(biggest connected graph) of selected node.


[website]: https://btc.com/api-doc