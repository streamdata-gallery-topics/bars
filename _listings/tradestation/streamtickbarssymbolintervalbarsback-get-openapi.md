---
swagger: "2.0"
x-collection-name: TradeStation
x-complete: 0
info:
  title: TradeStation Stream Tick Bars
  description: Streams tick bars data from a number of bars back, each bar returned
    separated by interval number of ticks.
  termsOfService: http://elasticbeanstalk-us-east-1-525856068889.s3.amazonaws.com/wp-content/uploads/2014/03/Guidelines_For_Acceptance.pdf
  contact:
    name: TradeStation API Team
    url: https://developer.tradestation.com/webapi
    email: webapi@tradestation.com
  version: 1.0.0
host: api.tradestation.com
basePath: /v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /stream/barchart/{symbol}/{interval}/{unit}/{barsBack}/{lastDate}/...:
    get:
      summary: Stream BarChart - Bars Back
      description: Streams barchart data starting from a number of bars back from
        last date, each bar filling interval of unit.
      operationId: streamBarchartsBarsBack
      x-api-path-slug: streambarchartsymbolintervalunitbarsbacklastdate----get
      parameters:
      - in: query
        name: access_token
        description: A valid OAuth2 token used to authorize access to the resource
      - in: path
        name: barsBack
        description: The number of bars to stream, going back from time 00:00:00 of
          the day specified in lastDate
      - in: path
        name: interval
        description: Interval that each bar will consist of
      - in: path
        name: lastDate
        description: The date to use as the end point when getting bars back
      - in: query
        name: SessionTemplate
        description: United States (US) stock market session templates, that extend
          bars returned to include those outside of the regular trading session
      - in: path
        name: symbol
        description: A Symbol Name
      - in: path
        name: unit
        description: Unit of time for each bar interval
      responses:
        200:
          description: Successful response
      tags:
      - Stream
      - BarChart
      - '-'
      - Bars
      - Back
  /stream/tickbars/{symbol}/{interval}/{barsBack}:
    get:
      summary: Stream Tick Bars
      description: Streams tick bars data from a number of bars back, each bar returned
        separated by interval number of ticks.
      operationId: streamTickBars
      x-api-path-slug: streamtickbarssymbolintervalbarsback-get
      parameters:
      - in: query
        name: access_token
        description: A valid OAuth2 token used to authorize access to the resource
      - in: path
        name: barsBack
        description: The number of bars to stream, going back from current time
      - in: path
        name: interval
        description: Interval for each bar returned (in ticks)
      - in: path
        name: symbol
        description: A Symbol Name
      responses:
        200:
          description: Successful response
      tags:
      - Stream
      - Tick
      - Bars
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---