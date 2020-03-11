# cs389_hw3

I used the testing framework Catch2. I have 4 test cases: plain cache, cache integration, fifo, and lru.

Each "test" is a section, with test code found in `test_evictors.cc` and `test_cache.cc`. 

### Plain Cache
| test name     | description                                                          | status |
|---------------|----------------------------------------------------------------------|--------|
| insert + get  | can keys and values be inserted                                      | pass   |
| empty query   | uninserted items are not found                                       | pass   |
| basic delete  | delete removes items                                                 | pass   |
| reset         | reset removes all items                                              | pass   |
| duplicates    | duplicate entries overwrite eachtother                               | pass   |
| full cache    | a cache will fill up until it hits its capacity, then it wont accept | pass   |
| unsafe values | cache copies values passed to it                                     | pass   |

### Cache Integration
Note: I still consider these unit tests. They are not a test of the
evictor. Instead, they test whether the cache performs correctly when given a
evictor. 
| test name  | description                               | status |
|------------|-------------------------------------------|--------|
| basic      | cache can accept an evictor, and it works | pass   |
| duplicates | cache handles duplicate evictions         | pass   |
| robustness | robustness check on evictor integration   | pass   |
| scale      | scale check on evictor integration        | pass   |

### FIFO Evictor
| test name   | description                              | status |
|-------------|------------------------------------------|--------|
| basic       | evictor is stable, returns "" on empty   | pass   |
| duplicates  | evictor handles duplicate keys correctly | pass   |
| unsafe item | evictor handles temporary values         | pass   |

### LRU Evictor
| test name   | description                                 | status |
|-------------|---------------------------------------------|--------|
| basic       | evictor is stable, returns "" on empty      | pass   |
| juggle      | evictor will not reject recently given keys | pass   |
| unsafe item | evictor handles temporary values            | pass   |


Note: There are cache/evictor submissions after Monday. This is to reflect
updates made on the homework 2 repository, as that due date was extended to before
class on Wednesday.
