per folder
    data_structures
        */category
        abstract_ds
            README - about ads
            ds
                README
                ds.md
                ds.py
                ds.x
            future_category
                README
                ds
                    py
                    java
                    c
                    ...
                    ds.md
        queue
        stack
        graph
        trees
            search trees
            binary search trees
            self balancing
        map
        list

abstract_ds README.md
    # name
        - abstract ds
        - parent abstract ds
        - types
    ## about
        summary explanation, adv, disadv
    ## all posible generic operations
    ### generic operation pseudocode

    ## children abstract ds: list of children abstract ds
    ## list of ds implementations with their variations
        can add requirements
        if implementations from parent ds dont need to list. EG stack abstract ds parent is list, so can be implemented by array and linked-list
        but list if extra info
    ## types
        classes/groups implementing ds or child ds can be placed in
        eg binary search tree can be placed in the search tree type and binary types of a tree

    ## refs
parent ds README.md
    # name
        - ds
        - implemented abstract ds(s) or parent ds - normally parent folder, may have > 1, ?
        - types - eg for trees: search tree, unbalanced / self-balancing
    ## about
    ## operatons
        + - new operation not included in parent ds or implemented ads
        = - operation also included in parent
        if matching parent ds operations
    ## pseudocode/process
        or can include after each operation bp in a indented cb

individual ads/ds ads.md/ds.md
    # name
        - ads/ds
        - parent abstract ds / parent ds
        - implemented abstract ds
            dont have to include parents
            EG queues implement queue, dont need to implement list
    ### variation operations and pseudocode
    ## operations implemented from parent and additional operations
        note which operations are differ form parents version
    ### pseudocode if different or needs to be less generic
