## Usage

Grab a [*GeoLite2 City* database][geolite2] from MaxMind:

```
$ curl -s http://geolite.maxmind.com/download/geoip/database/GeoLite2-City.mmdb.gz | \
  gunzip > GeoLite2-City.mmdb
```

Prep Cabal for building/running geode:

```
$ cabal sandbox init
$ cabal install -j --only-dependencies
```

Fire up geode:

```
$ cabal run
Running geode...
Setting phasers to stun... (port 3000) (ctrl-c to quit)
```

Try it out:

```
$ curl -s localhost:3000/8.8.8.8
{
  "regionName": "California",
  "latitude": 37.386,
  "postalCode": "94035",
  "city": "Mountain View",
  "countryName": "United States",
  "countryCode": "US",
  "region": "CA",
  "longitude": -122.0838,
  "continentCode": "NA",
  "continent": "North America"
}
```

[geolite2]: https://dev.maxmind.com/geoip/geoip2/geolite2/
