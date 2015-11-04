#Gephi

#



# Install
Go to Terminal.

Type "java -version".

If you have Java 6, great!

If you have Java 7 or higher, we need Java 6 to run Gephi 0.8.2. In December, a new version of [Gephi 0.9](https://gephi.wordpress.com/2015/11/02/announcing-gephi-0-9-release-date/) will be available that works with Java 8. Until then, we need to do a work around. We need to delete/ disable your current version of Java. 

If you have OSX before El Capitan, follow [these instructions](https://www.java.com/en/download/help/mac_uninstall_java.xml0).

If you have OX El Capitan, go to the terminal and type:

```
cd /Library/Java/JavaVirtualMachines/
ls
```
You need to delete every version of Java in here!

Note: Make sure to change where it says "version" to the version's of java on your machine.

```
cd /Library/Java/JavaVirtualMachines/
sudo rm -rf /Library/Java/JavaVirtualMachines/jdk<version>.jdk
```

For example:
```
sudo rm -rf /Library/Java/JavaVirtualMachines/jdk1.8.0_60.jdk
```

```
sudo rm -rf /Library/Java/JavaVirtualMachines/jdk1.8.0_51.jdk/
```

```
sudo rm -rf /Library/Java/JavaVirtualMachines/jdk1.8.0_05.jdk/
```

Download [Java 6](https://support.apple.com/kb/DL1572?locale=en_US).



Download [Gephi](http://gephi.github.io/). 

Open the .dmg file. Drag Gephi into Applications. Launch Gephi.


If it doesn't open: Right click and select "Show Package Contents". Go to Contents -> Resources -> gephi -> etc -> gephi.conf

Open gephi.conf with a text editor.

Edit the #jdkhome line so that it points to Java6.  Most likely:

jdkhome="/SystFem/Library/Frameworks/JavaVM.framework/Versions/1.6.0/Home/"



(Special thank you to [Evan Van Ness](http://www.evanvanness.com/post/71491924768/how-to-run-gephi-in-mac-os-x) for this work around.)



#Loading Data
Download 20050.zip. Download Supreme Court Zip Files.

[Code Book](http://scdb.wustl.edu/documentation.php?s=2c)

File -> Open -> 20050.csv

Here you must choose whether your graph is directed or undirected. The decision depends on your data.

Note: If the proper screen doesn't seem to be appearing, you can always to go Window in the menu bar. For example, I often find myself having to go to Window-> Graph to get my network to appear. (As you'll see, Gephi is fickle!)

Another Note: To move the graph, select Command and then move your graph. You can zoom in and out with your mouse.

Overview of Gephi by Clement Levallois.



#Data
To see the data, select Data Laboratory. (If the tables don't appear, go to Window -> Data Table)

It separates you data into a node list and edge list.  You can adjust the data within Gephi. If you do so, make sure to export it!



#Layout
You can choose your layout. The following are the two we covered in class:



Layout -> Fruchterman Reingold -> Run -> Stop

Based on graph drawing. The idea is that the edges want to stay together but the nodes want to move apart.



Layout -> Forced Atlas2 -> Run -> Stop

Designed for Gephi and popular for visualizations.



The first time you select a layout, options will appear. Some adjustments you might consider are  Prevent Overlap and Gravity. To return to this screen, go to Data Laboratory -> Layout. Select the layout you want to adjust and the options screen will appear.



#Labels
In the graph view, select the T in the bottom menu. The labels will appear. Their are several options next to the T that allow you to adjust text font and size. Play around!



#Statistics
Statistics -> Modularity -> Run

Modularity is an algorithm designed to help identify groups or communities in a network (i.e. community detection). It measures the nodes, so to visualize it, we want to look at how this calculation impacts the nodes. Go toward the top left of your screen  and select Partition -> Refresh (icon with two arrows) -> Nodes ->  Choose a partition parameter  -> Modularity Class

Now we have groups of cases. Let's say I want to know which cases are the most important. So, let's count the number of edges using Degree.

Statistics -> Average Degree -> Run

Ranking (next to Partition) -> Select the Diamond -> Degree -> Min/Max -> Apply

Now you can adjust the Min / Max. The nodes with the least amount of edges are adjusted through Min size: and the nodes with the most amount of edges are adjusted by Max size:.  After you hit apply, the nodes sizes should adjust accordingly.

The other options are excellent as well and worth exploring!

For example, betweenness and and closeness centrality are popular because they both measure which nodes are central to the network. You can access these calculations by selecting Avg. Path Length.  In our case, it isn't a surprise that 347 US 483 Brown v Board of Education is central to cases on school desegregation.



#Outliers(?)
So, let's say there are some outliers that I am not interested in. (This is particularly important if you have a lot of data.) We might consider removing certain nodes. For example, let's say one case has only been cited by one other case. We might decide this case isn't important to our network for we want to know which cases are the most influential.

Window -> Filters -> Topology -> Degree Range

A slider will appear. Adjust accordingly.  Select Filter to apply.

 
#Final
Select Preview. There are many options. Play around and make sure to hit refresh in order to see them. To Export, go to File -> Export





#Assignment
The goal of the assignment is to visualize a theme from the Supreme Court Data. You can pick any theme you'd like.  In the response, explain the theme you chose, the decisions you made in Gephi and any conclusions we can draw from the network. Make sure to include the network in your blog post.

1. Use the  [Code Book](http://scdb.wustl.edu/documentation.php?s=2c) to pick a topic. (Ex. 20050  - Desegregation)

2. Download the ussc (3).  Once you have downloaded, unzip and select your topic.

3. Load your data into Gephi.  Adjust as you deem fit!


#Related Readings

Cordell, Ryan, “Uncovering Reprinting Networks in Nineteenth-Century American Periodicals.” Am Lit Hist (Fall 2015) 27 (3): 417–445.

Edward Arriaga, Fernando Caparini and Juan Luis Suarez, [“Modeling Afro-Latin American Artistic Representations in Topic Maps: Cuba’s Prominence in Latin American Discourse.”](http://www.digitalhumanities.org/dhq/vol/7/1/000145/000145.html).

Moretti, Franco. [Network Theory, Plot Analysis.](https://litlab.stanford.edu/LiteraryLabPamphlet2.pdf)

Weingart, Scott. [“Topic Modeling and Network Analysis.”](http://www.scottbot.net/HIAL/?p=221) The scottbot irregular.

Weingart, Scott. [“Contextualizing networks with maps.”](http://www.scottbot.net/HIAL/?p=1942) The scottbot irregular.
