## Alberto Savi
- #### Voice Activity detection system  (VAD)
	- Multi Layer Perceptron - 1, 2 or 3 hidden dense layers(fully connected + Softmax)
		- 1 = 91.82%
		- 2 = 96.58%
		- 3 = 97.74%
			- with pyramidal structure(128 layer1, 64 layer2, 16 layer3) 96.93% with less parameters
	- Accuracy
		- 96.87 without quantization(~39Kbyte weights) and ~800 byte activations
		- 96.72 with quantization(~9Kbyte weights) and ~1000 byte activations
	- 
	- Feature extraction with old model called  "tonga model" for speaker ID
	- Tonga for feature embedding
	- MUSAN [Dataset](https://openslr.org/) music, speech and noise recordings
	- Noise doesn't include voice (unvoiced)
	- Music (unvoiced, only instrumental)

## Simone
- ### Face recognition & optimization
	- MTCNN Face detection and 5-key point extraction - Open source, 
	- Face recognition, QKeras model, Binary
	- mobilenetv2 on 850KB
		- difficult to binarize
		- 8bit and 1bit models
	- Multimodal
		- face images and voice audio
		- Audio Feature: Log-Mel spectrogram
		- MFCC- another audio feature but old and log-mel better
		- 64FFT windows, 64 MEL Filters = 64x64 audio features as image (Log-Mel spectrogram)
		- Cosine similarity classification 
		- Data fusion of audio and video happen at the last dense layer
		- Both audio and video use MNV2 version models
	- GAN
		- For creating new images with the existing images to get a diverse dataset and to avoid privacy
		- StyleGAN3
		
	

## Roberto Biraghi
- #### Contribution to [Vespucci](https://vespucci.st.com/) - cross-team project 
	- web app, nmo need to download any application and just design from the web app
	- web and firware parts
		- Collect raw data logs
		- Create or import database
		- Model dev and traininig
		- Generate Binary
		- Deploy	
	
	- eLooM is the embedded framework 
	- Introdcution of preprocessing in vespucci 
	- since earlier version of eLooM doesn't support the preprocessing of raw data
	- eLooM to support some additional sensors









## Others
- Investigate Pixies, aton and N6 sensor computation
- Thanos  - 3D scanner, more than VGA resolution, RAW data to be processed by a software pipeline
- Convert from RGB to Monochrome and use it for 3d face identification/recognition




