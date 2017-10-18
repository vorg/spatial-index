# spatial-index

Spatial index using KD-tree for finding neighbor search.

## API

#### index = spatialIndex(points, metric, dimensions, accuracy)

`points` - array of points
`metric` - distance function between two points
`dimensions` - list of props representing each direction e.g.: 
Array like point [0.3, 0.5] -> [0, 1]
Object like point { x: 0.3, y: 0.5 } -> ['x', 'y']
`accuracy` - precision below which points are considered equal

```javascript

const spatialIndex = require('spatial-index')
const Vec2 = require('pex-math/Vec2')

const points = [[0, 0], [1, 0], [2, 1], [1, 0], [0, 0], [0, 2]]

const index = spatialIndex(points, Vec2.distance, [0, 1], 0)
```


#### index.getUniquePoints()

```javascript
let uniquePoints = index.getUniquePoints()
//[[0, 0], [1, 0], [2, 1], [0, 2]]
```

#### index.nearestPoint(p)

```javascript
let nearest = index.nearestPoint([0.5, 0.7])
//[0, 1]
```

#### index.includePoint(p)

```javascript
index.includePoint([3, 1])
```

#### index.indexOf(p)

```javascript
let index = index.indexOf([0, 2])
//3

let index = index.indexOf([2, 0])
//-1
````
