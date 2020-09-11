# set
- ads
- parent ads list

## about
    no duplicate values

## variations
### disjoint set
    - stores collection of disjoint (non-overlapping) sets
    - main implementation is the disjoint set forest
        - each tree repersents a set in the forest, set members are nodes in the tree
        - each tree has a root/which repersents it
        - node
            - node.pointer: points to parent, the root will point to itself, this creates a parent pointer tree
            - node.size:
            - cant implement node.pointer and node.size
    - use: find which items are connected directly or indirectly

#### operations
##### making a new set containing new element
```
    make_set(x)
        if x is not already in the forest then
            x.parent = x
            x.size = 1     // if nodes store size
            x.rank = 0     // if nodes store rank
        end if
    end function


```
##### finding the representative of the set containing a given element
```
    find_set(x):
        if x !== x.parent:
            x.parent = find_set(x.parent)
        return x.parent
```
##### merging two sets (union)
find parents and then compare their ranks/sizes
```
by rank
    union_set(x, y):
        //replace nodes with roots
        x, y = find_set(x), find_set(y)

        if x == y then
            return  // x and y are already in the same set
        end if

        //set with bigger rank should be parent, so that the disjoint set tree will be more flat.
        if x.rank > y.rank:
            y.parent = x
        else:
            x.parent = y
            if x.rank == y.rank:
                y.rank += 1

by size
    union_set(x, y) is
        x, y = find_set(x), find_set(y)

        if x == y then
            return  // x and y are already in the same set
        end if

        y.parent = x
        x.size = x.size + y.size
    end function
```
