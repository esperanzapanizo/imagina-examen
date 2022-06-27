# imagina-examen
### Hola
## Hola
# Hola

*hola* **hola** ***hola***

La url que usaremos es: https://api.covid19api.com/countries

Primero vamos a importar las librerías.


```python
!pip install pandas
```

    Requirement already satisfied: pandas in /usr/local/lib/python3.8/dist-packages (1.3.1)
    Requirement already satisfied: numpy>=1.17.3 in /usr/local/lib/python3.8/dist-packages (from pandas) (1.21.1)
    Requirement already satisfied: python-dateutil>=2.7.3 in /usr/local/lib/python3.8/dist-packages (from pandas) (2.8.1)
    Requirement already satisfied: pytz>=2017.3 in /usr/local/lib/python3.8/dist-packages (from pandas) (2020.4)
    Requirement already satisfied: six>=1.5 in /usr/lib/python3/dist-packages (from python-dateutil>=2.7.3->pandas) (1.14.0)


Perdón, lo de antes era instalar las librerías. Ahora sí, vamos a importarlas. 


```python
import pd as pandas
```


    ---------------------------------------------------------------------------

    ModuleNotFoundError                       Traceback (most recent call last)

    <ipython-input-4-d001e6b1a3c9> in <module>
    ----> 1 import pd as pandas
    

    ModuleNotFoundError: No module named 'pd'



```python
import pandas as pd
```

Ahora definimos la url que vamos a usar como variable.


```python
url = 'https://api.covid19api.com/countries'
```

Comprobamos que se ha fijado...


```python
url
```




    'https://api.covid19api.com/countries'



Bien. Ahora ya podemos crear el dataframe. 

En este caso, a diferencia del de las farolas, se trata de un archivo json.


```python
df = pd.read_json(url)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Malaysia</td>
      <td>malaysia</td>
      <td>MY</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Maldives</td>
      <td>maldives</td>
      <td>MV</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Mozambique</td>
      <td>mozambique</td>
      <td>MZ</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Turks and Caicos Islands</td>
      <td>turks-and-caicos-islands</td>
      <td>TC</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Viet Nam</td>
      <td>vietnam</td>
      <td>VN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>243</th>
      <td>Oman</td>
      <td>oman</td>
      <td>OM</td>
    </tr>
    <tr>
      <th>244</th>
      <td>Zimbabwe</td>
      <td>zimbabwe</td>
      <td>ZW</td>
    </tr>
    <tr>
      <th>245</th>
      <td>Gibraltar</td>
      <td>gibraltar</td>
      <td>GI</td>
    </tr>
    <tr>
      <th>246</th>
      <td>Germany</td>
      <td>germany</td>
      <td>DE</td>
    </tr>
    <tr>
      <th>247</th>
      <td>Marshall Islands</td>
      <td>marshall-islands</td>
      <td>MH</td>
    </tr>
  </tbody>
</table>
<p>248 rows × 3 columns</p>
</div>



Juguemos un poco con la tabla acotándola. ¿Qué columnas tiene?


```python
df.columns
```




    Index(['Country', 'Slug', 'ISO2'], dtype='object')




```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Malaysia</td>
      <td>malaysia</td>
      <td>MY</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Maldives</td>
      <td>maldives</td>
      <td>MV</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Mozambique</td>
      <td>mozambique</td>
      <td>MZ</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Turks and Caicos Islands</td>
      <td>turks-and-caicos-islands</td>
      <td>TC</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Viet Nam</td>
      <td>vietnam</td>
      <td>VN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>243</th>
      <td>Oman</td>
      <td>oman</td>
      <td>OM</td>
    </tr>
    <tr>
      <th>244</th>
      <td>Zimbabwe</td>
      <td>zimbabwe</td>
      <td>ZW</td>
    </tr>
    <tr>
      <th>245</th>
      <td>Gibraltar</td>
      <td>gibraltar</td>
      <td>GI</td>
    </tr>
    <tr>
      <th>246</th>
      <td>Germany</td>
      <td>germany</td>
      <td>DE</td>
    </tr>
    <tr>
      <th>247</th>
      <td>Marshall Islands</td>
      <td>marshall-islands</td>
      <td>MH</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.info
```




    <bound method DataFrame.info of                       Country                      Slug ISO2
    0                    Malaysia                  malaysia   MY
    1                    Maldives                  maldives   MV
    2                  Mozambique                mozambique   MZ
    3    Turks and Caicos Islands  turks-and-caicos-islands   TC
    4                    Viet Nam                   vietnam   VN
    ..                        ...                       ...  ...
    243                      Oman                      oman   OM
    244                  Zimbabwe                  zimbabwe   ZW
    245                 Gibraltar                 gibraltar   GI
    246                   Germany                   germany   DE
    247          Marshall Islands          marshall-islands   MH
    
    [248 rows x 3 columns]>



Vamos a centrarnos en uno de los países, españa. 


```python
url_es = 'https://api.covid19api.com/country/spain/status/confirmed/live'
```


```python
url_es
```




    'https://api.covid19api.com/country/spain/status/confirmed/live'




```python
df = pd.read_json(url_es)
```


```python
df = pd.read_json(url)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Malaysia</td>
      <td>malaysia</td>
      <td>MY</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Maldives</td>
      <td>maldives</td>
      <td>MV</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Mozambique</td>
      <td>mozambique</td>
      <td>MZ</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Turks and Caicos Islands</td>
      <td>turks-and-caicos-islands</td>
      <td>TC</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Viet Nam</td>
      <td>vietnam</td>
      <td>VN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>243</th>
      <td>Oman</td>
      <td>oman</td>
      <td>OM</td>
    </tr>
    <tr>
      <th>244</th>
      <td>Zimbabwe</td>
      <td>zimbabwe</td>
      <td>ZW</td>
    </tr>
    <tr>
      <th>245</th>
      <td>Gibraltar</td>
      <td>gibraltar</td>
      <td>GI</td>
    </tr>
    <tr>
      <th>246</th>
      <td>Germany</td>
      <td>germany</td>
      <td>DE</td>
    </tr>
    <tr>
      <th>247</th>
      <td>Marshall Islands</td>
      <td>marshall-islands</td>
      <td>MH</td>
    </tr>
  </tbody>
</table>
<p>248 rows × 3 columns</p>
</div>




```python
df_es = pd.read_json(url_es)
```


```python
df_es
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>882</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12613634</td>
      <td>confirmed</td>
      <td>2022-06-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>883</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12613634</td>
      <td>confirmed</td>
      <td>2022-06-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>884</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12681820</td>
      <td>confirmed</td>
      <td>2022-06-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>885</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12681820</td>
      <td>confirmed</td>
      <td>2022-06-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>886</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12681820</td>
      <td>confirmed</td>
      <td>2022-06-26 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>887 rows × 10 columns</p>
</div>




```python
url_it = 'https://api.covid19api.com/country/italy/status/confirmed/live'
```


```python
url_it
```




    'https://api.covid19api.com/country/italy/status/confirmed/live'




```python
df_it = pd.read_json(url_it)
```


```python
df_it
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>882</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>18014202</td>
      <td>confirmed</td>
      <td>2022-06-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>883</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>18071634</td>
      <td>confirmed</td>
      <td>2022-06-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>884</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>18128044</td>
      <td>confirmed</td>
      <td>2022-06-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>885</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>18184917</td>
      <td>confirmed</td>
      <td>2022-06-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>886</th>
      <td>Italy</td>
      <td>IT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>41.87</td>
      <td>12.57</td>
      <td>18234242</td>
      <td>confirmed</td>
      <td>2022-06-26 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>887 rows × 10 columns</p>
</div>




```python
url_gr = 'https://api.covid19api.com/country/greece/status/confirmed/live'
```


```python
url_gr
```




    'https://api.covid19api.com/country/greece/status/confirmed/live'




```python
df_gr = pd.read_json(url_gr)
```


```python
df_gr
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>883</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>3583526</td>
      <td>confirmed</td>
      <td>2022-06-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>884</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>3595498</td>
      <td>confirmed</td>
      <td>2022-06-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>885</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>3607580</td>
      <td>confirmed</td>
      <td>2022-06-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>886</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>3616874</td>
      <td>confirmed</td>
      <td>2022-06-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>887</th>
      <td>Greece</td>
      <td>GR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>39.07</td>
      <td>21.82</td>
      <td>3616874</td>
      <td>confirmed</td>
      <td>2022-06-27 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>888 rows × 10 columns</p>
</div>




```python
df_es.set_index('Date')
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-22 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
    </tr>
    <tr>
      <th>2020-01-23 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
    </tr>
    <tr>
      <th>2020-01-24 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
    </tr>
    <tr>
      <th>2020-01-25 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
    </tr>
    <tr>
      <th>2020-01-26 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2022-06-22 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12613634</td>
      <td>confirmed</td>
    </tr>
    <tr>
      <th>2022-06-23 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12613634</td>
      <td>confirmed</td>
    </tr>
    <tr>
      <th>2022-06-24 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12681820</td>
      <td>confirmed</td>
    </tr>
    <tr>
      <th>2022-06-25 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12681820</td>
      <td>confirmed</td>
    </tr>
    <tr>
      <th>2022-06-26 00:00:00+00:00</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12681820</td>
      <td>confirmed</td>
    </tr>
  </tbody>
</table>
<p>887 rows × 9 columns</p>
</div>




```python
df_es.set_index('Date')['Cases']
```




    Date
    2020-01-22 00:00:00+00:00           0
    2020-01-23 00:00:00+00:00           0
    2020-01-24 00:00:00+00:00           0
    2020-01-25 00:00:00+00:00           0
    2020-01-26 00:00:00+00:00           0
                                   ...   
    2022-06-22 00:00:00+00:00    12613634
    2022-06-23 00:00:00+00:00    12613634
    2022-06-24 00:00:00+00:00    12681820
    2022-06-25 00:00:00+00:00    12681820
    2022-06-26 00:00:00+00:00    12681820
    Name: Cases, Length: 887, dtype: int64




```python
df_it.set_index('Date')['Cases']
```




    Date
    2020-01-22 00:00:00+00:00           0
    2020-01-23 00:00:00+00:00           0
    2020-01-24 00:00:00+00:00           0
    2020-01-25 00:00:00+00:00           0
    2020-01-26 00:00:00+00:00           0
                                   ...   
    2022-06-22 00:00:00+00:00    18014202
    2022-06-23 00:00:00+00:00    18071634
    2022-06-24 00:00:00+00:00    18128044
    2022-06-25 00:00:00+00:00    18184917
    2022-06-26 00:00:00+00:00    18234242
    Name: Cases, Length: 887, dtype: int64




```python
df_gr.set_index('Date')['Cases']
```




    Date
    2020-01-22 00:00:00+00:00          0
    2020-01-23 00:00:00+00:00          0
    2020-01-24 00:00:00+00:00          0
    2020-01-25 00:00:00+00:00          0
    2020-01-26 00:00:00+00:00          0
                                  ...   
    2022-06-23 00:00:00+00:00    3583526
    2022-06-24 00:00:00+00:00    3595498
    2022-06-25 00:00:00+00:00    3607580
    2022-06-26 00:00:00+00:00    3616874
    2022-06-27 00:00:00+00:00    3616874
    Name: Cases, Length: 888, dtype: int64




```python
df_es.set_index('Date')['Cases'].plot(title='Casos de COVID-19 en España')
```




    <AxesSubplot:title={'center':'Casos de COVID-19 en España'}, xlabel='Date'>




![png](output_41_1.png)



```python
df_es.set_index('Cases')['Date'].plot(title='prueba de al revés')
```




    <AxesSubplot:title={'center':'prueba de al revés'}, xlabel='Cases'>




![png](output_42_1.png)



```python
b
```




    <AxesSubplot:title={'center':'Casos de COVID-19 en Italia'}, xlabel='Date'>




![png](output_43_1.png)



```python
df_gr.set_index('Date')['Cases'].plot(title='Casos de COVID-19 en Grecia')
```




    <AxesSubplot:title={'center':'Casos de COVID-19 en Grecia'}, xlabel='Date'>




![png](output_44_1.png)



```python
casos_es = df_es.set_index('Cases')['Date']
```


```python
casos_it = df_it.set_index('Cases')['Date']
```


```python
casos_gr = df_gr.set_index('Cases')['Date']
```


```python
casos_es = df_es.set_index('Date')['Cases']
```


```python
casos_es
```




    Date
    2020-01-22 00:00:00+00:00           0
    2020-01-23 00:00:00+00:00           0
    2020-01-24 00:00:00+00:00           0
    2020-01-25 00:00:00+00:00           0
    2020-01-26 00:00:00+00:00           0
                                   ...   
    2022-06-22 00:00:00+00:00    12613634
    2022-06-23 00:00:00+00:00    12613634
    2022-06-24 00:00:00+00:00    12681820
    2022-06-25 00:00:00+00:00    12681820
    2022-06-26 00:00:00+00:00    12681820
    Name: Cases, Length: 887, dtype: int64




```python
casos_it = df_it.set_index('Date')['Cases']
```


```python
casos_it
```




    Date
    2020-01-22 00:00:00+00:00           0
    2020-01-23 00:00:00+00:00           0
    2020-01-24 00:00:00+00:00           0
    2020-01-25 00:00:00+00:00           0
    2020-01-26 00:00:00+00:00           0
                                   ...   
    2022-06-22 00:00:00+00:00    18014202
    2022-06-23 00:00:00+00:00    18071634
    2022-06-24 00:00:00+00:00    18128044
    2022-06-25 00:00:00+00:00    18184917
    2022-06-26 00:00:00+00:00    18234242
    Name: Cases, Length: 887, dtype: int64




```python
casos_gr = df_gr.set_index('Date')['Cases']
```


```python
casos_gr
```




    Date
    2020-01-22 00:00:00+00:00          0
    2020-01-23 00:00:00+00:00          0
    2020-01-24 00:00:00+00:00          0
    2020-01-25 00:00:00+00:00          0
    2020-01-26 00:00:00+00:00          0
                                  ...   
    2022-06-23 00:00:00+00:00    3583526
    2022-06-24 00:00:00+00:00    3595498
    2022-06-25 00:00:00+00:00    3607580
    2022-06-26 00:00:00+00:00    3616874
    2022-06-27 00:00:00+00:00    3616874
    Name: Cases, Length: 888, dtype: int64




```python
vs = pd.concat([casos_es,casos_it];axis=1)
```


      File "<ipython-input-56-8995b982f51b>", line 1
        vs = pd.concat([casos_es,casos_it];axis=1)
                                          ^
    SyntaxError: invalid syntax




```python
pd.concat([casos_es,casos_it],axis=1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cases</th>
      <th>Cases</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-22 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-23 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-24 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-25 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-26 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2022-06-22 00:00:00+00:00</th>
      <td>12613634</td>
      <td>18014202</td>
    </tr>
    <tr>
      <th>2022-06-23 00:00:00+00:00</th>
      <td>12613634</td>
      <td>18071634</td>
    </tr>
    <tr>
      <th>2022-06-24 00:00:00+00:00</th>
      <td>12681820</td>
      <td>18128044</td>
    </tr>
    <tr>
      <th>2022-06-25 00:00:00+00:00</th>
      <td>12681820</td>
      <td>18184917</td>
    </tr>
    <tr>
      <th>2022-06-26 00:00:00+00:00</th>
      <td>12681820</td>
      <td>18234242</td>
    </tr>
  </tbody>
</table>
<p>887 rows × 2 columns</p>
</div>




```python
vs = pd.concat([casos_es,casos_it],axis=1)
```


```python
vs
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cases</th>
      <th>Cases</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-22 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-23 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-24 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-25 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-26 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2022-06-22 00:00:00+00:00</th>
      <td>12613634</td>
      <td>18014202</td>
    </tr>
    <tr>
      <th>2022-06-23 00:00:00+00:00</th>
      <td>12613634</td>
      <td>18071634</td>
    </tr>
    <tr>
      <th>2022-06-24 00:00:00+00:00</th>
      <td>12681820</td>
      <td>18128044</td>
    </tr>
    <tr>
      <th>2022-06-25 00:00:00+00:00</th>
      <td>12681820</td>
      <td>18184917</td>
    </tr>
    <tr>
      <th>2022-06-26 00:00:00+00:00</th>
      <td>12681820</td>
      <td>18234242</td>
    </tr>
  </tbody>
</table>
<p>887 rows × 2 columns</p>
</div>




```python
pd.concat([casos_es,casos_it,casos_gr],axis=1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cases</th>
      <th>Cases</th>
      <th>Cases</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-22 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-23 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-24 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-25 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-26 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2022-06-23 00:00:00+00:00</th>
      <td>12613634.0</td>
      <td>18071634.0</td>
      <td>3583526</td>
    </tr>
    <tr>
      <th>2022-06-24 00:00:00+00:00</th>
      <td>12681820.0</td>
      <td>18128044.0</td>
      <td>3595498</td>
    </tr>
    <tr>
      <th>2022-06-25 00:00:00+00:00</th>
      <td>12681820.0</td>
      <td>18184917.0</td>
      <td>3607580</td>
    </tr>
    <tr>
      <th>2022-06-26 00:00:00+00:00</th>
      <td>12681820.0</td>
      <td>18234242.0</td>
      <td>3616874</td>
    </tr>
    <tr>
      <th>2022-06-27 00:00:00+00:00</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>3616874</td>
    </tr>
  </tbody>
</table>
<p>888 rows × 3 columns</p>
</div>




```python
vs = pd.concat([casos_es,casos_it,casos_gr],axis=1)
```


```python
vs
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cases</th>
      <th>Cases</th>
      <th>Cases</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-22 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-23 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-24 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-25 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-26 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2022-06-23 00:00:00+00:00</th>
      <td>12613634.0</td>
      <td>18071634.0</td>
      <td>3583526</td>
    </tr>
    <tr>
      <th>2022-06-24 00:00:00+00:00</th>
      <td>12681820.0</td>
      <td>18128044.0</td>
      <td>3595498</td>
    </tr>
    <tr>
      <th>2022-06-25 00:00:00+00:00</th>
      <td>12681820.0</td>
      <td>18184917.0</td>
      <td>3607580</td>
    </tr>
    <tr>
      <th>2022-06-26 00:00:00+00:00</th>
      <td>12681820.0</td>
      <td>18234242.0</td>
      <td>3616874</td>
    </tr>
    <tr>
      <th>2022-06-27 00:00:00+00:00</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>3616874</td>
    </tr>
  </tbody>
</table>
<p>888 rows × 3 columns</p>
</div>




```python
vs.columns = ['España','Italia','Grecia']
```


```python
vs.columns
```




    Index(['España', 'Italia', 'Grecia'], dtype='object')




```python
vs.plot(title='Casos de COVID-19 en España, Italia y Grecia')
```




    <AxesSubplot:title={'center':'Casos de COVID-19 en España, Italia y Grecia'}, xlabel='Date'>




![png](output_63_1.png)


![valor-atributo-alt](https://www.phytoma.com/images/800px-2019-nCoV-CDC-23312.png)


```python

```
