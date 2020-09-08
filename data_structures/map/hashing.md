# hashing

## about
    transformation of a string of character into a usually shorter fixed-length value or key that represents the original string
    EG use: index and retrieve database items, hash passwords, within encryption algorithms
    universal hashing
        perfect hash func: if any inp (key) -> unique num (val)
            easier to find it if you know the data in advance
        very low chance to 0 chance of collisions

## hash func
    - characteristics
        - hash fully dependant on input data and uses all of it 
        - similar data has very different hashes
### examples
    division method
        h(k) = k mod m
    multiplication method
        multiply the key k by a constant A in the range 0 < A < 1 and extract the fractional part of kA. Then, we increase this value by m and take the floor of the result
        h(k) = floor(m(kAmod1))

    mid square method
        h(k) = rmv(k^2)
            where rmv() removes digits from both sides of the square
        h(k) = 4207**2 -> 17698849 -> 98
    folding method
        h(k) = k1+ k2+.....+kn
        split into parts and add
        h(2798) = 27 + 98 = 125

## hash table
    - implements map
    - hold hashed keys mapped to data
    - universe of keys: all possible hashed keys from hash func, generally U
    - collision:  a hash calculated for a val already exists in the hash table
    - probling: check a location in a hash table

    - adv:
        - allow constant excution time for larger data sets
            - as its easier to find the smaller/ consistent length hashed key than original val
            - fits random access
        - avoid key wastage
    - use
        - db system
        - compiler symbol tables
        - data dictionaries 
        - general maps
### rehashing
    if any stage the hash table becomes nearly full, the running time for the operations of will start taking too much time 
    create hash table with 2*size
    insert old vals into new table
    free mem of old table

### implement
#### chaining / bucket chaining / separte chaining
    elem (each value) (size n) in elements S stored in hash table T of size m
    hash func h which represents U mapped to {0...m-1}
    T [h (k)], key k is hashed into slot h(k)
    each contains a pointer to a linked list (chain) or null
        keys hashed into the same slot (collisions) are associated with the same linked list
    n/m - get average load factor, repersent number of average keys per slot
        we want <1 generally

    could use list head cells
        store the first record of each chain in the slot array, decreases pointer traversals by one and hence allows better caching for access

#### open addressing
    elems stored directly in the hash table
    each slot is a dynamic set or null
    since no pointers more slots for same mem
        less collisions, faster retrieval
    on insert probe for unoccupied slot (by adjusting index/key in some way)

    linear probing
        mv collided elem to first slot after collided slot (h+i)
        h (k, i) = (h'(k) + i) mod m, (rehash the previous hash + i)
        if collision at T [h'(k)] -> T [h'(k)+1] -> T[m-1] -> T[0] -> T[h'(k)-1]
        suffers from primary clustering
            clusters of adjacent enteries: more collisions, more average search time

    quadratic probing
        mv collided elem to relative to a squared count (h+i^2)
        h(k,i) = (h'(k) + c_1i + c_2i^2) mod m 
            (c_1 and c_2 are auxiliary constants)
    double hashing
        permutations produced have many of the characteristics of randomly chosen permutations
        h(k,i) = (h_1(k) + i h_2 (k)) mod m
            (h_1 and h_2 are auxiliary hash funcs)
