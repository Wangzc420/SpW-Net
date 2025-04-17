# SpW-Net

Electrical Impedance Tomography (EIT) reconstruction is a typical inverse problem with the characteristic of ill-posedness and nonlinearity. The reconstructed image based on sensitivity prior suffers from significant shape distortions due to the 'soft-field' nature and the limited measurements. Moreover, the existing learning-based methods still have drawbacks in expressing the complicated boundary and the multiphase distributions because of the insufficient features representation by spatial convolution. In this paper, we proposed a novel dual-domain architecture, called Spatial plus Wavelet Dual-domain Empowering (SpW-Net), to achieve high-quality EIT reconstruction, which learns the shape features and conductivity distributions in both the spatial and wavelet domains. First, the residual fast Fourier convolution is proposed to construct the spatial latent features globally. Second, a (shifted) window-based wavelet vision Transformer is introduced to not only capture multiscale and multifrequency information but also reduces the complexity efficiently. Finally, a dual-domain feature fusion block is proposed to fuse the latent representations in the spatial and wavelet domain adaptively with the attention-wise manner. Extensive experiments on both simulated and real-world data illustrate that SpW-Net performs better regarding visual results and quantitative evaluations (the Root Mean Squared Error (RMSE) is 3.972±1.931 and the Structural Similarity Index (SSIM) is 0.982±0.010). Further, the reconstructions of our method are more consistent with the ground truth compared with state-of-the-art methods on the public benchmark Kuopio Tomography Challenge 2023 (KTC2023). The SpW-Net could obtain better EIT reconstruction results, especially in complicated shapes and multiphase distributions.

The performances of our SpW-Net and other comparisons are listed as follows:

<div align="center">
  <img src="https://github.com/Wangzc420/SpW-Net/blob/main/Image/Overall%20Performance.png">
</div>

The performance of visualizations and quantitative evaluations. Left: the representative results (visualized reconstructions and quantitative metrics) of KTC-2023 test data, including multiphase inclusion distributions and complicated shapes. The compared methods include the proposed SpW-Net and CNN/Transformer-based architectures. The best results are marked as 'red.' Right: The SSIM v.s. Computational complexity (GFLOPs). The up-left area indicates better performance with higher SSIM and fewer GFLOPs. Overall, we can observe that SpW-Net offers improving visualizations and metrics and less GPU consumption with faster imaging speed.

The overall Framework of SpW-Net is:
<div align="center">
  <img src="https://github.com/Wangzc420/SpW-Net/blob/main/Image/SpW-Net%20Framework.png">
</div>

Overview of our SpW-Net framework with hierarchical dual-branch Encoder and Decoder structure. The measured voltages from the sensors are reshaped to VFM (16×16) and expanded to the HR-VFM (256×256) in a spatial-domain branch. Four layers of up-sampling obtain the initial imaging results in the spatial domain, and the ConvNeXt layer (shown in the green dot box) and the wavelet domain are obtained by the ISTA solver. The focuses of our design are residual fast Fourier convolution (RFFC), shifted/window-based wavelet vision Transformer (W2Former), and dual-domain feature fusion block (DFFB), where the details of these three core designs are illustrated in Section III-B, Section III-C, and Section III-D in the main paper. Finally, the output image is obtained by the initial reconstruction in the spatial domain and the results of the Decoder.

The Supplementary Materials are uploaded, which include the Noise robust analysis, Resolution analysis, and more visualization results.  

The code will be released once this paper is accepted. 


