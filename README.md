# docker-sms
This is a sample SMS app using MQTT ready for Docker.

## Installation Steps

1. install mosquitto from http://mosquitto.org/download/
2. open a terminal window and navigate to where your cloned this repository
3. `npm install`
4. open another terminal window
5. `/usr/local/sbin/mosquitto -c /usr/local/etc/mosquitto/mosquitto.conf`
6. go to first terminal window
7. `cd src/server`
8. `node server.js`

## Testing the MQTT services
Open a terminal window and proceed with either of the scenarios. Keep the terminal window where node is running the server to see the stdout messages.

### Sending a text
```
mosquitto_pub -t dc/sms -m "get sms ready"
mosquitto_pub -t dc/send-sms -m '{"to":"<ENTER PHONE NUMBER>","text":"hello mobile"}'
```

## Publishing a Mosquitto topic from Commandline

```
mosquitto_pub -t dc/matt -m "hello world"
```

You need to ensure that you either have a wild card or using a specific topic.

## Subscribing to a Mosquitto topic using a wild card from commandline

```
mosquitto_sub -t dc/#
```