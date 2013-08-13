howler.js plugin for ImpactJS
======================
A plugins is tested with Impact 1.22.

##Quick Setup:

1. Copy `howler.js` to `lib/plugins/`
2. Require the plugin in main.js: `'plugins.howler'`

##Usage:

#####Most basic, play an MP3/OGG:
``` JavaScript
var sound = new Howl({
  urls: ['sound.mp3', 'sound.ogg']
}).play();
```
#####More playback options: 
``` JavaScript
var sound = new Howl({
  urls: ['sound.mp3', 'sound.ogg', 'sound.wav'],
  autoplay: true,
  loop: true,
  volume: 0.5,
  onend: function() {
    alert('Finished!');
  }
});
```
#####Define and play a sound sprite:
``` JavaScript
var sound = new Howl({
  urls: ['sounds.mp3', 'sounds.ogg'],
  sprite: {
    blast: [0, 2000],
    laser: [3000, 700],
    winner: [5000, 9000]
  }
});

// shoot the laser!
sound.play('laser');
```


