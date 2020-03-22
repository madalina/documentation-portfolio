## 1. Describing a song with few attributes

#### XML song Example
```
<?xml version="1.0" encoding="UTF-8" ?>
<song language="en">
   <title>Hey Jude</title>
   <artist>The Beatles</artist>
   <musicians>
       <musician>John Lennon</musician>
       <musician>Paul McCartney</musician>
       <musician>George Harrison</musician>
       <musician>Ringo Starr</musician>
   </musicians>
</song>
```

#### Documentation example

<table>
   <thead>
        <tr>
            <th colspan=3>Element</th>
            <th>Description</th>
            <th>Type</th>
            <th>Required</th>
            <th>Notes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan=3>song</td>
            <td>Top level</td>
            <td>song data type</td>
            <td>Required</td>
            <td > Attributes:
                <ul>
                    <li> language: two letter language code </li>
                </ul>
            </td>
        </tr>
        <tr>
            <td />
            <td colspan = 2>title</td>
            <td>Song title</td>
            <td>string</td>
            <td>Required</td>
            <td />
        </tr>
        <tr>
            <td />
            <td colspan = 2>artist</td>
            <td>Artist name</td>
            <td>string</td>
            <td>Required</td>
            <td />
        </tr>
        <tr>
            <td />
            <td colspan = 2>musicians</td>
            <td>A list of musicians playing the song</td>
            <td>array of musician elements</td>
            <td>Required</td>
            <td />
        </tr>
        <tr>
            <td /> 
            <td /> 
            <td>musician</td>
            <td>Name of musician playing the song</td>
            <td>string</td>
            <td>Required</td>
            <td />
        </tr>
    </tbody>
</table>

## 2. Temperature and humidity API example

#### XML song Example
```
<dailyData>
    <date>2015-06-01</date>
    <hourlyData>
        <time>10:00</time>
        <device>
            <id>34</id>
            <temperature>70</temperature>
            <humidity>11</humidity>
        </device>
        <device>
            <id>35</id>
            <temperature>72</temperature>
            <humidity>12</humidity>
        </device>
    </hourlyData>
    <hourlyData>
        <time>11:00</time>
        <device>
            <id>34</id>
            <temperature>71</temperature>
            <humidity>10</humidity>
        </device>
    </hourlyData>
</dailyData>
```
*Notes:*
- *time is local time.*
- *temperature is degrees F*
- *humidity is percentage*

#### Documentation example


#### Top Level
| Element   | Description                               | Type              |
| --------- | ----------------------------------------- | ----------------- |
| dailyData | Temperature and humidity data for one day | dailyData element |

#### dailyData element: Represents temperature and humidity data for one day
| Element    | Description                                 | Type               | Notes             |
| ---------- | ------------------------------------------- | ------------------ | ----------------- |
| date       | The date when the temperature data was taken| string             | Format: YYYY-MM-DD|
| hourlyData | Temperature and humidity data for one hour  | hourlyData element |                   |

#### hourlyData element: Represents temperature and humidity data for one hour
| Element| Description                                           | Type           | Notes         |
| ------ | ----------------------------------------------------- | -------------- | ------------- |
| time   | The local time that the temperature was taken         | string         | Format: HH:MM |
| device | One or more device objects with data from each device | device element |               |

#### device element: Temperature and himidity data from a device
| Element     | Description                                      | Type   |
| -------     | ------------------------------------------------ | -----  |
| id          | The device's id                                  | number |
| temperature | The measured temperature in degrees Fahrenheit.  | number |
| humidity    | The measured humidity in percentage.             | number |
