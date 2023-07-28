# Linear-Regression
## إستخدام الإنحدار الخطي (Linear Regression) على بيانات رقمية في ملف CSV بإستخدام Python .



 سنستخدم بيانات توضح أحجام عدد من المناطق(area) وأسعار كل منطقة (price).


 ### البيانات (Excel)
 ```
    area	price
0	1000	316404.1096
1	1500	384297.9452
2	2300	492928.0822
3	3540	661304.7945
4	4120	740061.6438
5	4560	799808.2192
6	5490	926090.7534
7	3460	650441.7808
8	4750	825607.8767
9	2300	492928.0822
10	9000	1402705.479
11	8600	1348390.411
12	7100	1144708.904
```
![image](https://github.com/taline1429/Linear-Regression/assets/75810658/75288c3c-c036-400b-8256-a74a564c5c7a)

استدعاء المكتبات المطلوبة و قراءة ملف ال csv اللذي تم تسميته (price) وطباعة البيانات التي يحتويها ليسهل رؤيتها.
```python

import pandas as pd
import matplotlib.pyplot as plt
from sklearn import linear_model

df = pd.read_csv("price.csv") # the csv file
print(df)
```
وضع دالة الإنحدار الخطي في متغير (reg).
```python
reg = linear_model.LinearRegression()
reg.fit(df[['area']], df.price)
```

الآن سنحدد المحور الصادي "Y" وسيكون عبارة عن الأسعار (price), والمحور السيني "X" وسيكون عبارة عن المناطق (area), ونجعل حجم الخط 20.
```python
plt.xlabel("area", fontsize=20)
plt.ylabel("price", fontsize=20)
```

سنجعل النقاط التي تربط بين المناطق وأسعارها باللون الأحمر وعبارة عن شكل "+"
```python
plt.scatter(df.area, df.price, color="red", marker="+")

```
ثم نجعل لون الخط اللذي سيربط بين النقاط باللون الأزرق, ونظهر الرسم البياني بإستعمال دالة (show)
```python
plt.plot(df.area, reg.predict(df[["area"]]), color="blue")
plt.show()
```

## الآن يمكنك تشغيل الكود ورؤية الانحدار الخطي لبياناتك
## إنتهى.
