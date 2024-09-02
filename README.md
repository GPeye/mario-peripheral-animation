# Urchin Peripheral Animation

![mario](./mario.gif)

![mario](./maionboard.gif)

## Usage

To use my urchin animation module as-is, first add it to your config/west.yml by adding a new entry to remotes and projects:

**If you are using your own forked/cloned module, just replace the url-base: with your forked or cloned url base**

```yml
manifest:
  remotes:
      # zmk official
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: gpeye                         #new entry
      url-base: https://github.com/GPeye  #new entry
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: mario-peripheral-animation   #new entry
      remote: gpeye                       #new entry
      revision: main                      #new entry
  self:
    path: config
```

Now simply swap out the default nice_view shield for the custom one in your build.yaml file.

```yml
---
include:
  - board: nice_nano_v2
    shield: urchin_left nice_view_adapter nice_view
  - board: nice_nano_v2
    shield: urchin_right nice_view_adapter nice_view_custom #custom shield
```