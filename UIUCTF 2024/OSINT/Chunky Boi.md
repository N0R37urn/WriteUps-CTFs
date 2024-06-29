# Chunky Boi

Now that's a BIG plane! I wonder where it is. Flag format: uiuctf{plane type, coordinates of the aircraft} Example: uiuctf{Airbus A380-800, 40.036, -88.264}

For coordinates, just omit the digits, do not round up. Precision is the same as the one in the example. The aircraft name is the same as Wikipedia page title. You can extract enough information from this image to answer this. You DO NOT need to register any accounts, all the information is public.

Flag format clarification: The last digit of the first coordinate is even, and the last digit of the second coordinate is odd.

# Solution

By performing a reverse image search on the picture of the airplane, I identified the type of aircraft on [AirHistory](https://www.airhistory.net/photo/166643/07-7187/77187). To determine the location or airport, I cross-referenced information on potential locations using Wikipedia [Alaska Airlines](https://es.wikipedia.org/wiki/Alaska_Airlines), which led to the identification of the `Seattle-Tacoma International Airport.`


