```Python
# initialize index counters
set modelIndex to 0
set chainIndex to 0
set groupIndex to 0
set atomIndex to 0

# traverse models
for modelChainCount in chainsPerModel
    print modelIndex
    # traverse chains
    for 1 to modelChainCount
        print chainIndex
        set offset to chainIndex * 4
        set chainGroupCount to groupsPerChain[ chainIndex ]
        # traverse groups
        for 1 to chainGroupCount
            print groupIndex
            set group to groupList[ groupTypeList[ groupIndex ] ]
            set atomOffset to atomIndex
            set groupBondCount to group.bondAtomList.length / 2
            for i in 1 to groupBondCount
                print group.bondOrderList[ i ]
            set groupAtomCount to group.atomNameList.length
            # traverse atoms
            for i in 1 to groupAtomCount
                print atomIndex
                increment atomIndex by 1
            increment groupIndex by 1
        increment chainIndex by 1
    increment modelIndex by 1

# traverse inter-group bonds
for i in 1 to bondAtomList.length / 2
    print bondOrderList[ i ]
```
