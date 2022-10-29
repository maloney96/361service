# 361service
### Oregon State University 361 - 400 F2022

## What you need:
API Key for [Positionstack API Key](https://positionstack.com/)

API Key for [Openweathermap API Key](https://openweathermap.org/)

## How to run:
```
git pull git@github.com:penkar/361service.git
cd 361service
npm install
# Write API Keys to Secrets JS file
node index.js
# From your Browser Console try running: 
# await fetch(`http://localhost:3000/?addressString=${encodeURIComponent("Corvallis, OR 97331")}`).then(res => res.json())

```

## How to use:
1) Encode and address string as a URI component:
`let address = encodeURIComponent("Corvallis, OR 97331")`
2) Make your request to the provided port using the addressString url param
`fetch("http://localhost:3000/?addressString=${address}")`
3) OR Make your request using the lat & longitude url params
`fetch("http://localhost:3000/?lat=10&long=10")`
4) This will return a Promise with the weather forecaset data for your requested address over the next four days.

```
  {
    city:
    cnt:
    cod:
    list: 96x[
      {
        clouds:{
          all: INT
        },
        dt: DATE,
        dt_txt: DATESTRING,
        main: {
          feels_like: NUMBER,
          grnd_level: NUMBER,
          humidity: NUMBER,
          pressure: NUMBER,
          sea_level: NUMBER,
          temp: NUMBER,
          temp_kf: NUMBER,
          temp_max: NUMBER,
          temp_min: NUMBER,
        },
        pop: NUMBER,
        sys: {
          pod: STRING,
        },
        visibility: NUMBER,
        weather: {
          description: STRING,
          icon: STRING,
          id: NUMBER,
          main: STRING,
        }
        wind: {
          deg: NUMBER,
          gust: NUMBER,
          speed: NUMBER,
        }
      }
    ]
  }
```


