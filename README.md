# cricbuzzpy

A python library to extract Player info and stats from [Cricbuzz](https://www.cricbuzz.com/)

## Installation

```bash
pip install cricbuzz-stats
```

## Usage

```python
from cricbuzzpy.player import Player

# create Player obj
p = Player()

# get player
p.get('jason holder')

{'id': 8313,
 'title': 'Jason Holder',
 'imageName': 'Jason Holder',
 'intro': 'Jason Holder',
 'country': 'West Indies',
 'publishedTime': '1575901896000',
 'imageId': '244677'}

# get player info
p.get_info(8313)

{'age': '31',
 'height': None,
 'role': 'bowling allrounder',
 'batting_style': 'right handed bat',
 'bowling_style': 'right-arm fast-medium'}

# get player stats
p.get_stats()

(       m inn no runs  hs   avg   bf      sr 100 200 50  4s  6s
 t20i  49  34  9  385  38  15.4  319  120.69   0   0  0  23  21
 ipl   38  24  5  247  47  13.0  199  124.12   0   0  0  13  17,
        m inn     b  runs wkts   bbi   bbm  econ    avg     sr 5w 10w
 t20i  49  46  1006  1370   51  5/27  5/27  8.17  26.86  19.73  1   0
 ipl   38  38   824  1177   49  4/52  4/52  8.57  24.02  16.82  0   0)

# init player with stats
p = Player('jason holder')
print(p)

        Name: Jason Holder
        Country: West Indies
        Info: {'age': '31', 'height': None, 'role': 'bowling allrounder', 'batting_style': 'right handed bat', 'bowling_style': 'right-arm fast-medium'}
        Batting Stats:        m inn no runs  hs   avg   bf      sr 100 200 50  4s  6s
t20i  49  34  9  385  38  15.4  319  120.69   0   0  0  23  21
ipl   38  24  5  247  47  13.0  199  124.12   0   0  0  13  17
        Bowling Stats:        m inn     b  runs wkts   bbi   bbm  econ    avg     sr 5w 10w
t20i  49  46  1006  1370   51  5/27  5/27  8.17  26.86  19.73  1   0
ipl   38  38   824  1177   49  4/52  4/52  8.57  24.02  16.82  0   0

```

## Limitations

Only T20I and IPL stats for players are supported currently