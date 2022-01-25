---
id: V9cBZj2ub2x17iuSktWfL
title: Investpy
desc: ''
updated: 1643023038603
created: 1643022799097
---
# investpy package

[Documentation](https://investpy.readthedocs.io/)

Query historical data for multiple stocks in a single website request  
ref: [issue 488](https://github.com/alvarobartt/investpy/issues/488)
```python
import time
stocks = ["A", "B"]
for stock in stocks:
    data = investpy.get_stock_historical_data(stock=stocks, 
                                            country='XXX',
                                            from_date='01/01/2020',
                                            to_date='01/01/2021')
   time.sleep(5)
```

