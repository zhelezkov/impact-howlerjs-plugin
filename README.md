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

##Properties 

`autoplay:` Boolean (true by default) Set to true to automatically start playback when sound is loaded.

`buffer:` Boolean (false by default) Set to true to force HTML5 Audio. This should be used for large audio files so that you don't have to wait for the full file to be downloaded and decoded before playing.

`format:` String (null by default) howler.js automatically detects your file format from the URL, but you may also specify a format in situations where URL extraction won't work.

`loop:` Boolean (false by default) Set to true to automatically loop the sound forever.

`sprite:` Object ({} by default) Define a sound sprite for the sound. The offset and duration are defined in milliseconds.
```
// Sound sprite definition format
{
  key: [offset, duration]
}
```

`volume:` Number (1.0 by default) The volume of the specific track, from 0.0 to 1.0.

`urls:` Array ([] by default) The source URLs to the track(s) to be loaded for the sound. These should be in order of preference, howler.js will automatically load the first one that is compatible with the current browser.

`onend:` Function (function(){} by default) Fire when the sound finishes playing (if it is looping, it'll fire at the end of each loop).

`onload:` Function (function(){} by default) Fires when the sound is loaded.

`onloaderror:` Function (function(){} by default) Fires when the sound fails to load.

`onpause:` Function (function(){} by default) Fires when the sound has been paused.

`onplay:` Function (function(){} by default) Fires when the sound begins playing.

##Methods 
`play:` Begins playback of sound. Will continue from previous point if sound has been previously paused.

`sprite:` String (optional) Plays from the defined sprite key.

`pause:` Pauses playback of sound, saving the pos of playback.

`id:` Number (optional) The play instance ID.

`stop:` Stops playback of sound, resetting pos to 0.

`id:` Number (optional) The play instance ID.

`mute:` Mutes the sound, but doesn't pause the playback.

`id:` Number (optional) The play instance ID.

`unmute:` Unmutes the sound.

`id:` Number (optional) The play instance ID.

`fadeIn:` Fade in the current sound.

`to:` Number Volume to fade to (0.0 to 1.0).

`duration:` Number Time in milliseconds to fade.

`callback:` Function (optional) Fires when fade is complete.

`fadeOut:` Fade out the current sound and pause when finished.

`to:` Number Volume to fade to (0.0 to 1.0).

`duration:` Number Time in milliseconds to fade.

`callback:` Function (optional) Fires when fade is complete.

`id:` Number (optional) The play instance ID.

`loop:` Get/set whether to loop the sound.

`loop:` Boolean (optional) To loop or not to loop, that is the question.

`pos:` Get/set the position of playback.

`position:` Number (optional) The position to move current playback to.

`id:` Number (optional) The play instance ID.

`sprite:` Get/set sound sprite definition.

`sprite:` Object (optional) See above for sound sprite definition.

`pos3d:` Get/set the 3D position of the audio source. The most common usage is to set the x position to affect the left/right ear panning. Setting the value higher than 1.0 will begin to decrease the volume of the sound as it moves further away. This only works with Web Audio API.

`x:` Number The x-position of the sound.

`y:` Number The y-position of the sound.

`z:` Number The z-position of the sound.

`id:` Number (optional) The play instance ID.

`volume:` Get/set volume of this sound.

`volume:` Number (optional) Volume from 0.0 to 1.0.

`id:` Number (optional) The play instance ID.

`urls:` Get/set the URLs to be pulled from to play in this source.

`urls:` Array (optional) Changes the source files for this Howl object.

`on:` Call/set custom events. Multiple events can be added by calling this multiple times.

`event:` String Name of event to fire/set.

`function:` Function (optional) Define function to fire on event.

`off:` Remove custom events that you've set.

`event:` String Name of event.

`function:` Function (optional) The listener to remove.

`unload:` Unload and destroy a Howl object. This will immediately stop all play instances attached to this sound and remove it from the cache.

##Global Methods 
The following methods are used to modify all sounds globally, and are called from the Howler object. 

`mute:` Mutes all sounds.

`unmute:` Unmutes all sounds and restores them to their previous volume.

`volume:` Get/set the global volume for all sounds.

`volume:` Number (optional) Volume from 0.0 to 1.0.


