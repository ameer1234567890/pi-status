## Status Dashboard on a Raspberry Pi

This shows a web based status dashboard on a Raspberry Pi.

#### Installation
- Add `* * * * * curl "https://api.thingspeak.com/update?api_key={YOUR_THINGSPEAK_API_KEY_HERE}&field1=$(awk '/MemFree/ {print $2}' /proc/meminfo)&field2=$(vcgencmd measure_temp | cut -d = -f 2 | cut -d \' -f 1)"` to crontab and change API_KEY.
- Install a web server. Really any web server that can erve static content is fine.
- Copy this repository to the web root.
- Change ThingSpeak channel ID in `index.html`, `cputemp/index.html` and `freemem/index.html` as required.

#### Usage
- Open Raspberry Pi's IP address in a web browser (Chrome recommended).
