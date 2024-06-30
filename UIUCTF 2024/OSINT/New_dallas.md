New Dallas

Super wide roads with trains... Is this the new Dallas? Flag format: uiuctf{coordinates of intersection between the rail and the road} Example: uiuctf{41.847, -87.626}

Flag format clarification: Use three decimal points of precision, truncate, and do not round. Use Google Maps location for reference. The last digit of the first cooordinate is odd, and the last digit of the second coordinate is even.

[Image]()

# Solution

1. I started by using reverse image search tools like Google, Yandex, and Bing but did not get any relevant results.

2. I then looked for vehicle plates and any visible text in the image. This led me to conclude that the location was in China, but I needed a specific city, town, or state to narrow down my searches.

3. After conducting numerous searches for metros in China, I found a metro line with colors very similar to the one I needed.

4. Through validation, I discovered it was the `Wuxi Metro` which has four lines. After spending considerable time, I identified the specific line I needed: `Line 2 of the Wuxi Metro.`

5. Using Baidu Maps, I utilized the street view feature to pinpoint the exact location: Location on Baidu Maps [Location](https://map.baidu.com/search/%E5%9C%B0%E9%93%812%E5%8F%B7%E7%BA%BF/@13402454.32,3686311.58,21z,87t,27.53h?querytype=s&da_src=shareurl&wd=%E5%9C%B0%E9%93%812%E5%8F%B7%E7%BA%BF&c=1&src=0&wd2=%E6%97%A0%E9%94%A1%E5%B8%82&pn=0&sug=1&l=5&b=(6347177.960000001,2093652.75;16832937.96,6885972.75)&from=webmap&biz_forward=%7B%22scaler%22:2,%22styles%22:%22pl%22%7D&sug_forward=b05cf10d623dcda38505bfe9&device_ratio=2#panoid=09000100011704181137551027O&panotype=street&heading=333.27&pitch=-5.66&l=21&tn=B_NORMAL_MAP&sc=0&newmap=1&shareurl=1&pid=09000100011704181137551027O).

6. With the information from Baidu Maps, I used Google Maps to find the intersection and extract the coordinates: Coordinates on Google Maps [coordeantes](https://www.google.com/maps/place/31%C2%B034'44.4%22N+120%C2%B023'16.8%22E/@31.5801847,120.3803256,1615m/data=!3m1!1e3!4m4!3m3!8m2!3d31.579!4d120.388?entry=ttu).

###  uiuctf{31.579, 120.388}
