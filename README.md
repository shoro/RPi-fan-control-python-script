# RPi CPU Temperature Monitor

### Create file

```
sudo nano cpumon.py
```

### Copy code below

```
import os
import time

while True:
    temperature = float(os.popen('vcgencmd measure_temp').readline().replace("temp=","").replace("'C",""))
    voltage = float(os.popen('vcgencmd measure_volts core').readline().replace("volt=","").replace("V",""))
    print(temperature, "°C", "|", voltage, "V")
    time.sleep(1)
```

### Save and Exit

CTRL+X -> Y -> ENTER

### Run the script

```
sudo python cpumon.py
```

### Stop the script

CTRL+C
