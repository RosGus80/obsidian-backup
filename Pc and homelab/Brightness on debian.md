
Brightness setting is set in /sys/class/backlight/amdgpu10/brightness with values  from 0 to 255 (amdgpu10 may be replaced with another gpu name)
to change the value we can 
`echo <value> | tee /sys/class/backlight/amdgpu10/brightness`
