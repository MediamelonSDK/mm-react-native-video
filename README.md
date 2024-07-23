# MediaMelon React Native Video SDK

## Overview
The MediaMelon SDK provides comprehensive video engagement and Quality of Experience (QoE) monitoring for React Native applications using `reactnative-video`.

## Documentation
Visit our [documentation](https://docs.mediamelon.com/mediamelon/smartsight-player-sdk-integration/react-native/react-native-video-v5.2.0-with-mediamelon-sdk) to get started.

## Requirements
- A functioning React Native application that uses `reactnative-video`.
- React Native Video

## Installation
Install the SDK from our repository:

for react native video (5.0.2)
```sh
npm i mediamelon-reactnative-video@1.0.0
```
for react native video (6.4.2)
```sh
npm i mediamelon-reactnative-video@2.0.0
```

Usage
The MediaMelon SDK wraps your Video component in a higher-order component to provide additional monitoring and analytics capabilities.

```javascript
import mmReactNativeVideo from 'mediamelon-reactnative-video'; // Import the SDK

// Wrap the `Video` component with MediaMelon functionality
const MMPlayer = mmReactNativeVideo(Video);

// Use `MMVideoPlayer` component in your application
 <MMPlayer
    source={{ uri: 'https://demo.unified-streaming.com/k8s/features/stable/video/tears-of-steel/tears-of-steel.mp4/.m3u8' }}   // Can be a URL or a local file.
    style={styles.video}
    controls={true}  
    resizeMode="contain"
    onLoad = {() => setLoading(false)}
    mmOptions={{
    data: {
      application_name: 'APP_NAME',           
      application_version: 'APP_VERSION',
      player_name: 'PLAYER_NAME',
      customer_id: 'CUSTOMER_ID',             // (required)
      subscriber_id: 'SUBSCRIBER_ID',
      domain_name: 'DOMAIN_NAME',
      subscriber_type: 'SUBSCRIBER_TYPE',
      subscriber_tag:'SUBSCRIBER_TAG',
      player_brand:"PLAYER_BRAND",
      player_model:"PLAYER_MODEL",
      player_version:'PLAYER_VERSION',
      device_marketing_name:'DEVICE_MARKETING_NAME'
    },
    content_metadata: {
      asset_name:'ASSET_NAME',
      asset_id:"ASSET_ID",
      video_Id:"VIDEO_ID",
      content_type:'CONTENT_TYPE',
      genre:'GENRE',
      drm_protection:'DRM_PROTECTION',
      episode_number:'EPISODE_NUMBER',
      season:'SEASON',
      series_title:'SERIES_TITLE',
      video_type:'VIDEO_TYPE',
      is_live: false,
    },
    custom_tags:{
      "KEY1": "VALUE_STRING1",
      "KEY2": "VALUE_STRING2"
    },
    enable_log_trace:false,
 }}
 />
```
## Known Issues
### Android:
onPause, onPlay, onSeek, and onBuffer events do not work automatically. (in react native video 5.2.0 )
### iOS:
onSeek event does not work.
