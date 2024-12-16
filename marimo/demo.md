---
title: Demo
marimo-version: 0.10.2
---

# cvxbson

```{.python.marimo}
import numpy as np

from cvx.bson import read_bson, write_bson
from cvx.json import read_json, write_json
```

## Create a dictionary of numpy arrays

```{.python.marimo}
data = {"A": np.random.rand(50, 50), "B": np.random.rand(50)}
```

## json

```{.python.marimo}
write_json("test.json", data)
_recovered = dict(read_json("test.json"))
assert np.allclose(data["A"], _recovered["A"])
assert np.allclose(data["B"], _recovered["B"])
```

## bson

```{.python.marimo}
write_bson("test.bson", data)
_recovered = dict(read_bson("test.bson"))
assert np.allclose(data["A"], _recovered["A"])
assert np.allclose(data["B"], _recovered["B"])
```

```{.python.marimo}
import marimo as mo
```