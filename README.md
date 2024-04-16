# social-vis

```mathematica
gr = Flatten[
   Table[Table[
     UndirectedEdge[dataset[j, 7, "likes", All, "userName"][i], 
      dataset[j, 3, "authorName"]], {i, 1, 
      Length[dataset[j, 7, "likes"]]}], {j, 1, 7418}]];
```
 
```mathematica
style = {VertexStyle -> Black, VertexShapeFunction -> "Point", EdgeStyle -> Directive[Opacity[0.05], Black, Thickness -> 0.0005], Background -> White, EdgeShapeFunction -> (Line[#1] &), ImageSize -> 600};
g = Graph[Flatten[{gr, grr}], style, GraphLayout -> {"PackingLayout" -> "ClosestPacking"}]
```

```mathematica
style = {EdgeStyle -> 
    Directive[Opacity[.05], Black, Thickness -> 0.00001], 
   Background -> White, EdgeShapeFunction -> (Line[#1] &), 
   ImageSize -> 30000};
CommunityGraphPlot[gr, style]
```


```mathematica
style = {EdgeStyle -> 
    Directive[Opacity[.05], Black, Thickness -> 0.0001], 
   ImageSize -> 3000};
graph = CommunityGraphPlot[gr, CommunityBoundaryStyle -> None, style, 
  VertexLabels -> "Name", 
  VertexLabelStyle -> Directive[Black, Opacity[1], 2]]
```
