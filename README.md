# DAB Compliance Testing Suite #

This project contains tools and tests to validate Device Automation Bus 2.0 Partner implementations end-to-end.

## Prerequisite ##
```
pip3 install -r requirements.txt
```

## Available Test Suite ##

### 1. Spec conformance Test Suite ###

Spec Conformance test checks if all DAB topic is available and the latency of each requests is within expectation. 
This test doesn't check on functionality or endurance. This should be the first test suite to run if you are checking your baisc implementation against DAB.

The following is command to run Spec conformance Test Suite:
```
❯ python3 main.py -v -b <mqtt-broker-ip> -I <dab-device-id>
```


### 2. Send Text/Send Audio Voice Test Suite ###

Voice functionality tests focuses on voice assisstance intergration with the platform. It go through a playback lifecycle from search to playback controls. Make sure if your device support all of these voice actions. 

The following is command to run Send Text/Send Audio Voice Test Suite
```
❯ python3 voice_audio.py -v -b <mqtt-broker-ip> -I <dab-device-id>

❯ python3 voice_text.py -v -b <mqtt-broker-ip> -I <dab-device-id>
```

### 3. End to End YouTube Test Suite ###

This end to end intergration test focuses on a mix of key presses and voice controls.

The following is command to run End to End YouTube Test Suit

```
❯ python3 end_to_end_YouTube.py -v -b <mqtt-broker-ip> -I <dab-device-id>
```


## Commands ##

These are the main commands of the tool:

```
❯ python3 test_suite.py --help
usage: test_suite.py [-h] [-v] [-l] [-b BROKER] [-I ID] [-c CASE]

options:
  -h, --help            show this help message and exit
  -v, --verbose         increase output verbosity
  -l, --list            list the test cases
  -b BROKER, --broker BROKER
                        set the IP of the broker. Ex: -b 192.168.0.100
  -I ID, --ID ID        set the DAB Device ID. Ex: -I mydevice123
  -c CASE, --case CASE  test only the specified case.Ex: -c 3
</pre>

```

## Command Examples ##

To list the command options:

```
❯ python3 main.py --help
```

To list the available test cases, type:

```
❯ python3 main.py -l
```

To execute the first test only:

```
❯ python3 main.py -v -b <mqtt-broker-ip> -I <dab-device-id> -c 0
```

To execute the third test only:

```
❯ python3 main.py -v -b <mqtt-broker-ip> -I <dab-device-id> -c 2
```

To execute all the tests:

```
❯ python3 main.py -v -b <mqtt-broker-ip> -I <dab-device-id>
```