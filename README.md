1. this repo is modified base on [gmn](https://github.com/sbos/gmn)
2. I am planning to integrate GAN into this project, and leveraging mathcing networks to generate latent varibles or encode support images for few-shot image generation.
3. script:
python one_shot.py --test=1 --reconstructions=False --no_dummy=False --conditional=False --prior_entropy=True

python one_shot.py --generate=4 --reconstructions=False --no_dummy=False --conditional=False --prior_entropy=False

### experimental results


#### test-likelihood
calculating the total loss from the genrative model and recognition model \\
episode                   average predictive likelihood of 10 samples \\
testing 0 -211.22 -182.05 -161.47 -170.08 -141.03 -121.17 -133.89 -176.56 -162.87 -119.77
testing 1 -175.24 -165.74 -135.59 -136.54 -118.61 -116.54 -149.73 -152.94 -127.44 -124.37
testing 2 -132.97 -129.49 -112.44 -109.74 -97.30 -96.32 -120.75 -138.11 -105.69 -100.18
testing 3 -126.34 -139.09 -129.08 -121.82 -101.35 -95.40 -116.21 -152.05 -98.96 -108.97
testing 4 -116.77 -133.17 -111.58 -106.36 -88.70 -83.89 -107.47 -136.91 -94.75 -96.97 
testing 5 -108.45 -121.18 -106.37 -99.76 -82.52 -81.22 -100.34 -123.27 -87.28 -88.84
testing 6 -100.93 -110.23 -97.37 -111.54 -76.59 -87.09 -107.67 -113.06 -81.78 -83.06
testing 7 -99.06 -105.48 -97.22 -116.65 -76.38 -84.22 -106.61 -112.35 -81.87 -86.71
testing 8 -105.18 -108.89 -98.73 -121.50 -81.31 -85.71 -105.25 -119.93 -99.38 -92.86
testing 9 -101.14 -104.60 -94.85 -114.47 -79.35 -91.25 -103.17 -112.57 -95.26 -98.86

\\

episode                entropy of latent variables z for 10 training samples \\
entropy 0 2540.05 2592.36 2612.57 2611.59 2638.88 2630.10 2625.30 2622.07 2623.65 2621.29
entropy 1 2540.05 2555.04 2565.92 2559.50 2565.68 2548.38 2546.56 2541.19 2535.13 2532.97
entropy 2 2540.05 2523.61 2518.70 2516.92 2518.57 2501.61 2498.84 2493.59 2492.44 2490.82
entropy 3 2540.05 2526.16 2527.48 2526.81 2524.99 2513.59 2505.96 2500.21 2496.82 2492.82
entropy 4 2540.05 2529.75 2530.62 2517.74 2508.33 2495.24 2485.44 2480.88 2477.20 2474.25
entropy 5 2540.05 2517.55 2505.91 2495.20 2488.36 2475.00 2465.65 2460.77 2456.86 2452.97
entropy 6 2540.05 2518.91 2499.00 2488.43 2487.42 2471.04 2465.46 2463.07 2459.42 2452.50
entropy 7 2540.05 2523.11 2503.26 2486.32 2488.55 2474.32 2468.27 2466.13 2462.32 2456.05
entropy 8 2540.05 2525.60 2509.01 2493.94 2496.58 2482.80 2474.22 2469.67 2467.06 2462.29
entropy 9 2540.05 2523.77 2504.10 2487.71 2489.25 2476.37 2471.19 2467.00 2463.82 2458.69


#### reconstruction: during trianing
 
<div align="center">
<img src="/GMN/images/constructed/Figure_1.png" height="500px" alt="constructed_1" >
<img src="/GMN/images/constructed/Figure_1-1.png" height="500px" alt="constructed_2" >
<img src="/GMN/images/constructed/Figure_1-2.png" height="500px" alt="constructed_3" >
</div>
<center>reconstructing images based on trained samples (measuring intermediate generation results) </center>






#### generation: generative model

<div align="center">
<img src="/GMN/images/generated/Figure_1.png" height="500px" alt="generated_1" >
<img src="/GMN/images/generated/Figure_1-1.png" height="500px" alt="generated_2" >
<img src="/GMN/images/generated/Figure_1-2.png" height="500px" alt="generated_3" >
</div>
<center>fedding test set, generated new image without training</center>


* classification
accuracy: 0.850000

* likelihood-classification
accuracy: 0.650000