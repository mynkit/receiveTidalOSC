# receiveTidalOSC

Sample code to display OSC logs from TidalCycles in openFrameworks.

# preparation

After starting SuperDirt, execute the following code in SuperCollider.This will send TidalCycles OSC logs to port 2020 on localhost.


```supercollider:def.scd
(
var addr = NetAddr.new("127.0.0.1", 2020);
o = OSCFunc({
arg msg, time;
var latency = time - Main.elapsedTime;
addr.sendBundle(latency, msg)
},'dirt/play');
o.free;
o.fix;
)
```


