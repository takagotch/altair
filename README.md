### altair
---
https://github.com/altair-viz/altair

```py
import altair as alt
from vega_datasets import data
cars = data.cars()
alt.Chart(cars).mark_point().encode(
  x='Horsepower',
  y='Miles_per_Gallon',
  color='Origin',
)

import altair as alt
from vega_datasets import data

source = data.cars()

brush = alt.selection(type='interval')

points = alt.Chart(source).mark_point().encode(
  x='Horsepower',
  y='Miles_per_Gallon',
  color=alt.condition(brush, 'Origin', alt.value('lightgray'))
).add_selection(
  brush
)

bars = alt.Chart(source).mark_bar().encode(
  y='Origin',
  color='Origin',
  x='count(Origin)'
).transform_filter(
  brush
)

points & bars


@article{Altair2018,
  doi = {10.21105/joss.01057},
  url = {https://doi.org/10.21105/joss.01057},
  year = {2018},
  month = {dec},
  publisher = {The Open Journal},
  author = {Jacob VanderPlas and Brian Granger and Jeffrey Heer and Domink Moritz and Kanit Wongsuphasawat and Arvind Satyanarayan and Eitan Lees and Ilia Timofeev and Ben Wlsh and Scott Sievert},
  title = {Altair: Interactive Statistical Visualizations for Python},
  journal = {Journal of Open Source Software}
}

```

```sh
pip install git+http://github.com/altair-viz/altair
py.test --pyargs altair
```

```
```


