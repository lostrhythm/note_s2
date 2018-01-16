# big_data_gfs
Tuesday, 16-Jan-18 22:40:11 UTC  
gfs

    - Architecture
        master - namenode
        chunkserver - datanode
            datanode and client could be running on the same machine
        chunk - block
        chunkhandle - blockid
            globally unique
            64 bit
        heartbeat - heatbeat
            instruction
            stat
        
        chunkserver do not need to cache data
        as linux buffer cache
        already does that
            - caching data, put data in memory
            - so that it can be efficiently accessed
            



co
------
vnode
