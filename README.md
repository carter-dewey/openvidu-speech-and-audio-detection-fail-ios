# openvidu-speech-and-audio-detection-fail-ios
IOnic hello world to demonstrate that audio/speech events do not fire on iOS

This is the exact same as the OpenVidu Ionic Hello World documented here: https://openvidu.io/docs/tutorials/openvidu-ionic/

To demonstrating that soeech/audio detection on iOS does not fire I have added the following lines to app.component.ts.

Sppech detection lines 108-114
```javascript
  this.session.on('publisherStartSpeaking', (event : ConnectionEvent) => {
      console.log('Publisher ' + event.connection.connectionId + ' start speaking');
  });

  this.session.on('publisherStopSpeaking', (event: ConnectionEvent) => {
      console.log('Publisher ' + event.connection.connectionId + ' stop speaking');
  });
```

Audio detection lines 162-166

```javascript
  publisher.on('streamPlaying', (event : any) => {
      this.publisher.on('streamAudioVolumeChange', (event) => {
          console.log('Publisher audio volume change from ' + event.value.oldValue + ' to' + event.value.newValue);
      });
  });
```

The events never fire and the console statements never appear. The rest of the audio/video elements of the call work as expected.

