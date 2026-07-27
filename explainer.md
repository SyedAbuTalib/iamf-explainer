# Native IAMF (Immersive Audio Model and Formats) MP4 Playback Explainer

Today, sites have two main options for delivering immersive audio: licensing proprietary spatial formats (which can impose costly royalties on hardware manufacturers) or building complex Web Audio node graphs to simulate immersiveness in application JavaScript. By including a built-in IAMF software decoder in the browser, developers gain an open and royalty-free standard for spatial audio that dynamically renders to arbitrary headphone and surround speaker setups. This will save development effort while reducing royalty overhead across the ecosystem.
  
We propose integrating native software support for the Immersive Audio Model and Formats (IAMF) specification into the browser media pipeline. Because IAMF is delivered as an audio track within standard MP4 container files (identified by the standardized `iacb` sample entry descriptor box), enabling this software decoder allows browsers to seamlessly demux and play IAMF media natively through the existing [Media Source Extensions (MSE)](https://developer.mozilla.org/en-US/docs/Web/API/Media_Source_Extensions_API) API.

From the web developer's perspective, there are zero changes to existing MSE workflows. The API is utilized in the exact same way, and the browser will handle the decoding and spatial rendering. Media provider services simply need to package their media using an IAMF-enabled encoder (such as [`iamf-tools`](https://github.com/AOMediaCodec/iamf-tools)). While initial support focuses on royalty-free multichannel beds and surround audio, future iterations will extend this MP4 capability to natively support **object-based audio streams**, allowing audio elements to be repositioned and rendered dynamically in real-time 3D space.

## References & Useful Links
* [AOMedia Immersive Audio Model and Formats (IAMF) Specification](https://aomediacodec.github.io/iamf/latest-approved.html)
* [IAMF Tools & Rendering Library (`iamf-tools`)](https://github.com/AOMediaCodec/iamf-tools)
* [IAMF Binaural Web Demo](https://aomediacodec.github.io/iamf-tools/web_demo/)