# Linux misc problems

### Background noise in discord

```bash
sudo nvim /etc/pulse/default.pa
```

then add,

```bash
load-module module-echo-cancel source_name=noechosource sink_name=noechosink
set-default-source noechosource
set-default-sink noechosink
```

save, exit and run `pulseaudio -k`

