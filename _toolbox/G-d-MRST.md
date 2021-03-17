---
title: G-δ - MRST
---

- How to build the EGG model with GAWPS by using `deckformat`:
{% highlight matlab %} 
mrstModule add deckformat

f = fullfile('..', 'GAWPS', 'Models', 'EGG', 'Egg_Model_ECL.DATA');

% Reading the input deck

deck = readEclipseDeck(f);      
deck = convertDeckUnits(deck);  % Convert to MRST units (SI)

% Reading grid structure

G = initEclipseGrid(deck); 
G = computeGeometry(G);

% Reading rock properties

rock = initEclipseRock(deck);
rock = compressRock(rock, G.cells.indexMap);
{% endhighlight %}

- How to detect cell boundaries in arbitrary grids:
{% highlight matlab %} 
bndyfac = any(G.faces.neighbors == 0, 2);
bndycells = find(accumarray(sum(G.faces.neighbors(bndyfac,:), 2), 1) > 0);
% check that you have selected all the boundary faces
figure, plotFaces(G,bndyfac);
{% endhighlight %}

Verification steps: 
{% highlight matlab %} 
% check if all the boundary cells were selected
figure
plotGrid(G,'Facecolor','none');
bndyfac = any(G.faces.neighbors == 0, 2);
bndycells = accumarray(sum(G.faces.neighbors(bndyfac,:), 2), 1) > 0;
plotGrid(G,~bndycells,'FaceColor','b');
{% endhighlight %}

- How to understand `accumarray` above:
	1. `G.faces.neighbors(bndyfac,:)` extracts an `n x 2` array containing the indices of cells on opposite sides of the faces given by `bndyfac`. Each row in this array will have two entries, but if `bndyfac` only contains boundary faces, one of the entries will always be zero. We can then extract the nonzero entry in each row by summing in the second dimension.
	2. The `sum(G.faces....)` operation has given us an array with indices of cells that lie next to the boundary. This array may contain repeated entries, since boundary cells may have more than one boundary face. The `accumarray()` counts the number of occurrences for each cell index (from 1 to the maximum returned by `sum()`). We can then use `find(accumarray(..) > 0)` to extract the cell indices that appear at least once in the list.



