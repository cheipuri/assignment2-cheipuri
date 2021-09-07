# assignment2-cheipuri
# Sravan kumar cheipuri
###### My favourite place is goa, India.
 I like **goa** because it's a beautiful place, Most of the **international people** vist goa because of less cost of living.

---
## Maryville to Hollywood.
    1. Directions for Hollywood.
        1. start in Maryville (Missouri) drive for about 2.5 hours
        2. Lincoln (Nebraska).
        3. Lincoln to  North Platte.
        4. North Platte to Capitol Reef National Park.
        5. National Park to Las Vegas.
    2. Finally Hollywood.

 ### Products to be packed for enjoyment.
    - Comfortable Shoes.
    - Weather Appropriate, Layered Attire.
    - Light Jacket.
    - Purse/Backpack.
    - Camera.
    - Extra Batteries/Charger.
    - Refillable Water Bottle.
    - Extra Cash.
---

[About me](AboutMe.md)

---
# Food Table

This table shows location and Amount of Foods.

| *Food*                | *Location*      | *Amount*         |
| -----------------------  | ----------------- | ------------------ |
| Biryani                  | Hyderabad         | 230 INR            |
| rasgulla                 | Kolkata           | 10 INR             |
| Paranthas                | Delhi             | 80 INR             |
| samber idli              | Chennai           | 45 INR             |

---
# Quotes

>Our greatest glory is not in never falling, but in rising every time we fall.

>Magic is believing in yourself, if you can do that, you can make anything happen.

>All our dreams can come true, if we have the courage to pursue them. 

---

# Dynamic Programming, Linear Algebra, Numerical Methods

>Dynamic programming is both a mathematical optimization method and a computer programming method. The method was developed by Richard Bellman in the 1950s and has found applications in numerous fields, from aerospace engineering to economics.
[Dynamic programming](https://en.wikipedia.org/wiki/Dynamic_programming)

int n, m;  
vector < vector<long long> > dp;  


void calc (int x = 0, int y = 0, int mask = 0, int next_mask = 0)  
{  
  if (x == n)  
  return;  
  if (y >= m)  
  dp[x+1][next_mask] += dp[x][mask];  
  else  
  {  
        int my_mask = 1 << y;  
        if (mask & my_mask)  
        calc (x, y+1, mask, next_mask);  
        else  

  {
    calc (x, y+1, mask, next_mask | my_mask);  
    if (y+1 < m && ! (mask & my_mask) && ! (mask & (my_mask << 1)))  
    calc (x, y+2, mask, next_mask);  
  }
  }
  }


  int main()  
  {  
  cin >> n >> m;  

  dp.resize (n+1, vector<long long> (1<<m));  
  dp[0][0] = 1;  
  for (int x=0; x<n; ++x)  
  for (int mask=0; mask<(1<<m); ++mask)  
  calc (x, 0, mask, 0);  

  cout << dp[n][0];  
  }

  [Dynamic programming source code](https://cp-algorithms.com/dynamic_programming/profile-dynamics.html)



 