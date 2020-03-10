# cs389_hw3

I used the testing framework Catch2. I have 4 test cases: plain cache, cache integration, fifo, and lru.

Each "test" is a section, with test code found in `test_evictors.cc` and `test_cache.cc`. 

### Plain Cache
| test name       | description                            | status |
|-----------------|----------------------------------------|--------|
| basic insertion | can keys and values be inserted        | pass   |
| empty query     | uninserted items are not found         | pass   |
| basic delete    | delete removes items                   | pass   |
| reset           | reset removes all items                | pass   |
| duplicates      | duplicate entries overwrite eachtother | pass   |

### Cache Integration
| test name       | description                                       | status |
|-----------------|---------------------------------------------------|--------|
| fifo basic      | cache can accept an evictor, and it works         | pass   |
| fifo duplicates | cache handles duplicate evictions                 | pass   |
| fifo unsafe     | cache handles can pass temporary names to evictor | pass   |
| lru basic       | robustness check on evictor integration           | pass   |
| lru juggle      | scale check on evictor integration                | pass   |

### FIFO Evictor
| test name   | description                              | status |
|-------------|------------------------------------------|--------|
| basic       | evictor is stable, returns "" on empty   | pass   |
| duplicates  | evictor handles duplicate keys correctly | pass   |
| unsafe keys | evictor handles temporary keys           | pass   |

### LRU Evictor
| test name | description                                 | status |
|-----------|---------------------------------------------|--------|
| basic     | evictor is stable, returns "" on empty      | pass   |
| juggle    | evictor will not reject recently given keys | pass   |


Note: There are cache/evictor submissions after Monday. This is to reflect
updates made on the homework 2 repository, as that due date was extended to before
class on Wednesday.
