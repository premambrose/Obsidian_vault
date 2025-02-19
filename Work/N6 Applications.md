- Ran and tested all the AI application examples for N6.
- Made a PowerShell script to run some image examples easily.
- working on learning the ISP package and middleware  and camera middleware understanding.

## ISP middleware architecture
![[Pasted image 20250207115838.png]]


## ISP Middleware Control Services

| Function            | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `ISP_Init()`        | Initialize the ISP middleware. The IQ tuning parameters structure and a list of helpers providing non-ISP controls (e.g., sensor configuration) are provided as input parameters. |
| `ISP_DeInit()`      | Deinitialize the ISP middleware.                                            |
| `ISP_Start()`       | Start the ISP processing. Configures the ISP and sensor according to the IQ tuning parameters and starts the IQ algorithms. |
| `ISP_BackgroundProcess()` | Run background tasks such as algorithm control and STM32 ISP IQTune message exchange (if in engineering mode). Should be called regularly (at least once per VSYNC for optimal performance). |

## ISP Middleware Applicative Services

| Function                    | Description                                                                             |
| --------------------------- | --------------------------------------------------------------------------------------- |
| `ISP_SetExposureTarget()`   | Adjust the exposure target setting.                                                     |
| `ISP_GetExposureTarget()`   | Read the exposure target setting.                                                       |
| `ISP_ListWBRefModes()`      | Return the list of predefined white balance modes.                                      |
| `ISP_SetWBRefMode()`        | Apply predefined ISP gains and color conversion settings based on a white balance mode. |
| `ISP_GetWBRefMode()`        | Read the current white balance mode.                                                    |
| `ISP_SetAECState()`         | Enable or disable the Auto Exposure Control algorithm.                                  |
| `ISP_GetAECState()`         | Read the state of the Auto Exposure Control algorithm.                                  |
| `ISP_GetDecimationFactor()` | Read the ISP decimation factor.                                                         |
| `ISP_SetStatArea()`         | Define the statistic window area.                                                       |
| `ISP_GetStatArea()`         | Read the statistic window area.                                                         |

---

- VENC support by the N6 under study. 

## Encoder API function prototypes

|                            |                                                                                             |
| -------------------------- | ------------------------------------------------------------------------------------------- |
| `H264EncGetApiVersion`     | Retrieves the version information of the H.264 encoder API.                                 |
| `H264EncGetBuild`          | Retrieves the build information of the H.264 encoder.                                       |
| `H264EncGetBitsPerPixel`   | Helper function to get the bit-depths for input formats.                                    |
| `H264EncInit`              | Initializes the H.264 encoder with the provided configuration.                              |
| `H264EncRelease`           | Releases the H.264 encoder instance.                                                        |
| `H264EncSetCodingCtrl`     | Sets the coding control parameters before stream generation.                                |
| `H264EncGetCodingCtrl`     | Gets the current coding control parameters.                                                 |
| `H264EncSetRateCtrl`       | Sets the rate control parameters before and during stream generation.                       |
| `H264EncGetRateCtrl`       | Gets the current rate control parameters.                                                   |
| `H264EncSetPreProcessing`  | Sets the preprocessing configuration before and during stream generation.                   |
| `H264EncGetPreProcessing`  | Gets the current preprocessing configuration.                                               |
| `H264EncSetRoiMap`         | Sets the Region of Interest (ROI) map.                                                      |
| `H264EncSetSeiUserData`    | Inserts user data during stream generation.                                                 |
| `H264EncStrmStart`         | Starts the stream generation by generating the SPS and PPS.                                 |
| `H264EncStrmEncode`        | Encodes one video frame and handles SEI messages and MVC mode.                              |
| `H264EncStrmEnd`           | Ends the stream with an End of Stream (EOS) code.                                           |
| `H264EncSetTestId`         | Sets the internal encoder test ID.                                                          |
| `H264EncSetInputMbLines`   | Sets the valid input macroblock lines for the encoder to work.                              |
| `H264EncGetEncodedMbLines` | Gets the information about encoded macroblock lines from the encoder.                       |
| `H264EncGetMbInfo`         | Sets the motionVectors field of the H264EncOut structure to point to a specific macroblock. |
| `H264AccessUnitDelimiter`  | Adds an Access Unit Delimiter (AUD).                                                        |
| `H264EncTrace`             | Callback function for API tracing.                                                          |
