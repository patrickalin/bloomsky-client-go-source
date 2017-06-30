# BloomSky Client in Go

[![Build Status](https://travis-ci.org/patrickalin/bloomsky-client-go.svg?branch=master)](https://travis-ci.org/patrickalin/bloomsky-client-go)
![Build size](https://reposs.herokuapp.com/?path=patrickalin/bloomsky-client-go)
[![Go Report Card](https://goreportcard.com/badge/github.com/patrickalin/bloomsky-client-go)](https://goreportcard.com/report/github.com/patrickalin/bloomsky-client-go)
[![Coverage Status](https://coveralls.io/repos/github/patrickalin/bloomsky-client-go/badge.svg)](https://coveralls.io/github/patrickalin/bloomsky-client-go)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Join the chat at https://gitter.im/tockins/bloomsky-client-go](https://badges.gitter.im/tockins/bloomsky-client-go.svg)](https://gitter.im/bloomsky-client-go/)
[![https://img.shields.io/badge/bloomsky-api-go.svg](https://img.shields.io/badge/bloomsky-api-go.svg)](https://github.com/patrickalin/bloomsky-api-go)

A simple Go client for the BloomSky API.

* It's possible to show informations in the console or in a embedded web server.
* It's also possible to export datas to Time Series Database InfluxData.

## 1] Getting Started

### Prerequisites

* BloomSky API key (get it here: [Bloomsky api](https://dashboard.bloomsky.com/))

### Installation

* Download the [binary](https://github.com/patrickalin/bloomsky-client-go/releases) for your OS and the [config.yaml](https://github.com/patrickalin/bloomsky-client-go/blob/master/config.yaml) in the same folder.

### Configuration

* Don't forget !!!! : You have to change the API Key in the config.yaml.
* Or use flag "-token xxxxxx"

### Traduction

* This application supports en-us and fr
* Cette application supporte l'anglais et le français

### Usage with config.yaml

Execute the binary with the config file "config.yaml" in the same folder.

* Windows : goBloomsky-windows-amd64.exe
* Linux : ./goBloomsky-linux-amd64.bin
* Mac : ./goBloomsky-darwin-amd64.bin

### Usage with flag

* Windows : goBloomsky-windows-amd64.exe -token xxxxxxx
* Linux : ./goBloomsky-linux-amd64.bin -token xxxxxxx
* Mac : ./goBloomsky-darwin-amd64.bin -token xxxxxxx

There are some others flags : --help for doc

   Usage of ./bloomsky-client-go:
     -debug string
       	panic,fatal,error,warning,info,debug
     -devel string
       	true,false
     -mock string
       	true,false
     -token string
       	yourtoken

### Example : result in the webserver

By default : `http://localhost:1111/`

![Web server](https://raw.githubusercontent.com/patrickalin/bloomsky-client-go/master/img/webserver.png)

### Example : result in the standard console

    Bloomsky
    --------
    Timestamp :         2017-06-09 22:07:10 &#43;0200 CEST
    City :              Thuin
    Device Id :         442C05954A59
    Num Of Followers :  2
    Index UV :          1
    Night :             true
    Wind Direction :    SW
    Wind Gust :         4.16
    Sustained Wind Speed : 2.17
    Wind Gust :         6.6976
    Sustained Wind Speed 3.4937
    Rain :              false
    Daily :             0.44
    24h Rain :          0.44
    Rain Rate :         0
    Rain Daily :        0.44
    24h Rain :          11.18
    Rain Rate :         0
    Temperature F :     59.13 °F
    Temperature C :     15.07 °C
    Humidity :          65
    Pressure InHg :     29.38
    Pressure HPa :      994.92

### Example : result in a influxData

![InfluxData Image ](https://raw.githubusercontent.com/patrickalin/bloomsky-client-go/master/img/InfluxDB.png)

## 2] Modification code / Compilation

### Pre installation

* install git
* install go from `http://golang.org/`
* If you want install influxData

### Installation env development

    git clone https://github.com/patrickalin/GobloomskyThermostatAPIRest.git
    cd GobloomskyThermostatAPIRest
    export GOPATH=$PWD
    go get -v .
    go build

### Mock

In the config file, you can activate a mock. If you don't have a API key.

* mock: true

### Dev

In the config file, you can change the dev mode to use template, lang locally.

* dev: true

When the dev = false you use assembly files.
Execute "go generate" to refresh assembly files.

### Debug

In the config file, you can change the log level (panic,fatal,error,warn,info,debug)

* logLevel: "debug"

## 3] Thanks

<https://github.com/tixu> for testing and review

<http://mervine.net/json2struct> "transform JSON to Go struct library"

<http://github.com/spf13/viper> "read config library"

## 4] License

The code is licensed under the permissive Apache v2.0 licence. This means you can do what you like with the software, as long as you include the required notices. [Read this](https://tldrlegal.com/license/apache-license-2.0-(apache-2.0)) for a summary.

