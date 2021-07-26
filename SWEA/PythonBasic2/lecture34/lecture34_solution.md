```python
beer = {'하이트': 2000, '카스': 2100, '칭따오': 2500, '하이네켄': 4000, '버드와이저': 500}

print(beer)

beer_inc = dict({key : float('{:.1f}'.format(val * 1.05)) for key, val in beer.items()})

print(beer_inc)
```



