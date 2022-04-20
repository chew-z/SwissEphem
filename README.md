# GoHoroscope

A bit of astrology in terminal with Go. Prints Ascendant, Houses, Zodiac signs, Aspects, Positions, Solar and Lunar eclipses, Retrograde movements.

## Installation

```
- git clone
- go build -o ./bin/horoscope .
```
This project is using Swiss Ephemeris with [swephgo](https://github.com/mshafiee/swephgo) as a wrapper. You will also need Swiss Ephemem library and ephemeris files. 

Download the Swiss Ephemeris Library [here](https://www.astro.com/ftp/swisseph/). After compiling the library, copy the libswe.so file to /usr/local/lib/

````
$ cp libswe.so /usr/local/lib/
````

Finally you will need some shell variables

```
export LATITUDE="51.5072"¬
export LONGITUDE="0.1276"¬
export CITY="Europe/London"
```

or put variables in `.env` file looking like `.env.example`

## Usage

```
horoscope --horoscope [date]

20 Apr 22 07:08 UTC - lat: 52.43, lon: 20.89
Ascendant: 121.96 MC: 7.01

+-------+----------+-------+-------------+
| House | Position | Cusp  | Sign        |
+-------+----------+-------+-------------+
| I     | 121.96   | 1.96  | Leo         |
| II    | 138.02   | 18.02 | Leo         |
| III   | 158.49   | 8.49  | Virgo       |
| IV    | 187.01   | 7.01  | Libra       |
| V     | 226.61   | 16.61 | Scorpio     |
| VI    | 269.36   | 29.36 | Sagittarius |
| VII   | 301.96   | 1.96  | Aquarius    |
| VIII  | 318.02   | 18.02 | Aquarius    |
| IX    | 338.49   | 8.49  | Pisces      |
| X     | 7.01     | 7.01  | Aries       |
| XI    | 46.61    | 16.61 | Taurus      |
| XII   | 89.36    | 29.36 | Gemini      |
+-------+----------+-------+-------------+


+---------+----------+-------+-------------+-------------------------------------------+
| Planet  | Position | House | Sign        | Aspects                                   |
+---------+----------+-------+-------------+-------------------------------------------+
| Sun     | 30.27    | X     | Taurus      |
|         |          |       |             |    Sextile - Mars - 333.97 in Pisces         |
|         |          |       |             |    Square - Pluto - 298.58 in Capricorn      |
| Moon    | 258.69   | V     | Sagittarius |
|         |          |       |             |    Quincunx - Mercury - 47.56 in Taurus      |
|         |          |       |             |    Square - Venus - 346.13 in Pisces         |
|         |          |       |             |    Square - Neptune - 354.24 in Pisces       |
| Mercury | 47.56    | XI    | Taurus      |
|         |          |       |             |    Sextile - Venus - 346.13 in Pisces        |
|         |          |       |             |    Conjunction - Uranus - 43.94 in Taurus    |
| Venus   | 346.13   | I     | Pisces      |
|         |          |       |             |    Conjunction - Jupiter - 355.71 in Pisces  |
|         |          |       |             |    Sextile - Uranus - 43.94 in Taurus        |
|         |          |       |             |    Conjunction - Neptune - 354.24 in Pisces  |
| Mars    | 333.97   | VIII  | Pisces      |
| Jupiter | 355.71   | I     | Pisces      |
|         |          |       |             |    Conjunction - Neptune - 354.24 in Pisces  |
|         |          |       |             |    Sextile - Pluto - 298.58 in Capricorn     |
| Saturn  | 323.61   | VIII  | Aquarius    |
|         |          |       |             |    Semi-sextile - Neptune - 354.24 in Pisces |
| Uranus  | 43.94    | X     | Taurus      |
| Neptune | 354.24   | I     | Pisces      |
| Pluto   | 298.58   | VI    | Capricorn   |
+---------+----------+-------+-------------+-------------------------------------------+

```
