# MyUnit.py

This is a thin wrapper of `SymPy` for peeps like me that deal with the natural units on a daily basis. Common usage is outlined in `demo.ipynb`. Even though there are fancy packages that can do much better, I find it more than enough for my usual order-of-magnitude estimates. 

Even though it is aimed for personal light uses, a few close friends asked me if I could share. So here it is. Feel free to open issues and even contribute if you find it handy. 


Cheers,
Chen


# Quick Examples: 

The use case I have in mind is to run from within a `Jupyter` notebook. 

A few examples on natural units:

```
test = NaturalUnit('c*year')
test()
```

```
# 4.79444331506342⋅1022 eV
```


```
NaturalUnit('year*eV')()
```

```
# 4.79444331506342⋅1022
```


```
new_quantity = NaturalUnit('year')*NaturalUnit('eV')
new_quantity()
```

```
# 4.79444331506342⋅1022
```

```
new_quantity.__dict__
```

```
# {'symb': 4.79444331506342e+22,
 'str': '4.79444331506342e+22',
 'val': 4.79444331506342e+22}
```


```
NaturalUnit('60*s').Mpl()
```
```
# 1.11293326256637⋅10^{45} Mpl
```

A few examples on SI Units:
```
test2 = SIUnit(test)
test3 = NaturalUnit(test2)
print(test3())
print(SIUnit(test3.length())())
print(SIUnit(test3.mass())())
print(SIUnit(test3.T())())
print(SIUnit(test3.mom())())
print(SIUnit(test3.time())())
print(NaturalUnit(SIUnit(test3.power())()))
print(SIUnit(test3.power()))
print(test3.GeV())
print(test3.Mpc())
print(test3.Mpl())
```

```
# 4.79444331506341e+22/eV
# 9.46073047258078e+15*m
# 2.68948557400311e+58/kg
# 4.13153032678779e+18/K
# 8.9711582204083e+49*s/(kg*m)
# 31557599.9999999*s
# 4.79444331506341e+22*eV**(-0.5)*(1/eV)**0.5
# 3.07302356212126e+24*kg**(-0.5)*m**(-1.0)*s**1.5
# 4.79444331506341e+31/GeV
# 3.06599166237184e-7*Mpc**1.0
# 5.85358378779407e+50/Mpl
```

# MyUnit.nb
This is an early version with `Mathematica` written in 2017. Although I rarely use `Mathematica` these days, some of you may use it more often than `python`. I'm putting it here as well. 

# License
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

    MyUnit  A light weight wrapper to convert untis between natural and SI units.
	Copyright (C) 2017-2022  Chen Sun

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.
	
