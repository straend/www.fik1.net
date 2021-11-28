---
title: "ESPHome"
date: 2021-11-27T18:56:03+02:00

---


Code snippet that reads the log from ESPHome [Remote Receiver](https://esphome.io/components/remote_receiver.html) with name of key added at end of line.

`[00:37:53][D][remote.samsung:060]: Received Samsung: data=0xE0E0B44B, nbits=32 INFO`

Will create an entry like
```yaml
  - name: Samsung INFO
    platform: remote_receiver
    samsung:
      data: 3772822603
```
Full config for a remote at https://github.com/straend/HASS-ESPHome/blob/main/remote.yaml


```python
import re
import yaml

input_file = "samsung_remote.txt"
output_file = "samsung.yaml"

x = re.compile(r"(?P<code>0x[A-Z0-9]+).+ (?P<name>.+)")

inputs = []
for l in open(input_file).readlines():
    m = x.search(l)
    inputs.append({
        'platform': 'remote_receiver',
        'name': "Samsung {}".format(m.group('name')),
        'samsung': {
            'data': int(m.group('code'), 16)
        }
    })

with open(output_file, 'w') as f:
    yaml.dump({'binary_sensor': inputs}, f)
```