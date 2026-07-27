# Native IAMF (Immersive Audio Model and Formats) MP4 Playback Explainer

Today, sites have two options to handle immersive audio: using propriatery formats (which could be costly to hardware manufacturers), or using complex WebAudio node graphs to simulate the immersiveness. By including a built-in IAMF sofware decoder in the browser, developers can save time and work, and hardware manufacturers could reduce their overall costs (reduction in royalty fees).

We propose integrating the open, royalty-free Immersive Audio Model and Formats (IAMF) specification to enable MP4 media files containing IAMF audio tracks (identified by the `iacb` sample entry descriptor box) to play natively through [Media Source Extensions (MSE)](https://developer.mozilla.org/en-US/docs/Web/API/Media_Source_Extensions_API).
  
From the web developer's point of view, there is no change in using MSE. The API is used in the same way, and the browser will still handle the decoding process. The main change is in the case of encoding media; Media provider services will need to use an IAMF encoder for such tasks (e.g., [`iamf-tools`](https://github.com/AOMediaCodec/iamf-tools)).

## References & Useful Links
* [AOMedia Immersive Audio Model and Formats (IAMF) Specification](https://aomediacodec.github.io/iamf/latest-approved.html)
* [IAMF Tools & Rendering Library (`iamf-tools`)](https://github.com/AOMediaCodec/iamf-tools)
* [IAMF Binaural Web Demo](https://aomediacodec.github.io/iamf-tools/web_demo/)