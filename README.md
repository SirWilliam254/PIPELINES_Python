# PIPELINES_Python

Data pipelines allow one to transform data from one representation to another by a series of steps. 
They are a key component of data engineering
Below is a simple pipeline which does the following:
      imputing the missing values in numeric data, 
      scaling them, 
      and fitting an XGBRegressor to X, y:
``` python
from sklearn.pipeline import make_pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.impute import SimpleImputer
import xgboost as xgb

xgb_pipe = make_pipeline(
                SimpleImputer(strategy='mean'),
                StandardScaler(),
                xgb.XGBRegressor()
            )

___ = xgb_pipe.fit(X, y)
```

This enables us to collapse all preprocessing and modelling steps into a single estimator and reduce overall errors 
in our code.
