# note_s2
consistent hashing algorithm
        - Tuesday, 16-Jan-18 22:14:11 UTC in RFC 2822
        - https://en.wikipedia.org/wiki/Consistent_hashing

                The main idea behind the
                consistent hashing algorithm

                is to
                associate each cache
                with
                one or more hash value intervals (bin)
                where
                the interval boundaries
                are determined by
                calculating the hash of each cache identifier.
                The hash function used to
                define the intervals
                does not have to be
                the same function used to
                hash the cached values.
                Only the range of the two functions
                need match.

                If the cache is removed
                its interval is taken over by a cache
                with an adjacent interval.

                All the remaining caches are unchanged.

        - technique
                Consistent hashing
                is based on
                mapping each object to a point on the edge of a
                circle
                mapping each object to a real angle

                system maps each available machine
                many pseudo-randomly distributed points
                on the edge of the same circle.

                To find where an object should be placed,
                the system finds the
                location of that object's key on the edge of the circle;
                then walks around the circle
                until falling into the first bucket it encounters
                        - clock wise bucket?

                If a bucket becomes unavailable (for example because the computer it resides on is not reachable),
                then the points it maps to will be removed.
                Requests for resources that would have mapped to each of those points now
                map to the next highest points.
                        - once a barrier is down, the balls roll to the next room
                                - in real situation, it may not be the simple "rolling" to the next room
                                - cause the hash function may not be linear
                                - if a wall is broken, the elements in the room is re- hashed and walked clocl-wise on the circle?
                                        - if it is like this, once a wall is built, every points will be re calculated ???

                Both consistent hashing and
                rendezvous hashing have the
                essential property that
                removal or addition of one node changes only
                the set of keys
                owned by the nodes with
                adjacent IDs
                        - 'next' room
                        - https://en.wikipedia.org/wiki/Distributed_hash_table







     
