# ✍️Portion Watermarking
## HELPS YOU IN DETECTING & RETRIEVING CHANGES, IN ANY IMAGE (IF ANY DURING IT'S TRANSMISSION).

![Portion-Watermarking](https://socialify.git.ci/suva007/Portion-Watermarking/image?description=1&descriptionEditable=Security%20Enhancement%20Using%20Combined%20DCT-DWT%20Digital%20Image%20Watermarking%20Technique&font=Bitter&language=1&name=1&owner=1&pattern=Floating%20Cogs&theme=Dark)

- <a href="https://github.com/suva007/Portion-Watermarking/blob/main/portion_watermark-2.ipynb" title="Link to notebook" style="background-color:#FFFFFF;color:#000000;text-decoration:none">📚 Link to notebook </a>

## Summary
- Intro:
>The snowballing of digitisation due to rapid growth in internet and computer technologies , image authentication and image restoration in case of any attack is one of the major factors in today’s environment. Digital watermarking is one such saviour that has been developed to protect digital images from illegal manipulations.

>A combined approach of DCT-DWT based image watermarking is put forward in this paper that effectively enhances the image restoration and authentication capability.
- Methodology Used:
>In this scheme the cover image is sliced into 9 * 9 non - overlapping blocks and each block is then fed into fragile watermarking module based on combination of DCT - DWT and the watermarked image is further made over before transmission over the network in order to enhance security capabilities and making it impalpable for the attacker.
- Findings:
>The restoration is achievable with high PSNR of 67.2% for each non-overlapping block and 100% in case of full watermarked image.
Evaluating the results of this approach tells the two transforms with this new approach of self-embedding enhances the performance and security with great extent.

## Methodology used
- ![image](https://user-images.githubusercontent.com/38084433/148693719-83d8adf3-a759-4381-9728-23c7e3345ba0.png)

## DWT Based Image breakDown
- ![image](https://user-images.githubusercontent.com/38084433/148693820-f2bb7978-8014-4055-b30b-26b6271c56fb.png)
- ![image](https://user-images.githubusercontent.com/38084433/148693823-3717181b-4b7b-4f60-bb6e-4240a155fcf4.png)

## Combined DCT-DWT Algorithm [EMBEDDING]
- Step 1: Apply DWT onto each portion of cover image to give non-overlapping bands LL1,HL1,LH1and HH1.

- Step 2: Apply DWT now on the either of sub-band amongst HH1 or HL1 as depicted in above figure for LL1.

- Step 3: now divide sub-band HH2 or HL2  into 4 * 4 blocks. 

- Step 4: Apply DCT to each of these blocks now . 

- Step 5: Embedding of watermark will be done in the mid sub-band coefficients fetched out of DCT and a scale factor we need to define in order to decide the perceptibility of watermark post embedding.
	> mid_coeff’=mid_coeff (+/-) ALPHA * watermark

- Step 6: Apply inverse operation of DCT [IDCT] to after embedding the mid sub-band coefficients based on above formula . 

- Step 7: Apply IDWT on this transformed image, include modified sub-bands , to produce the watermarked host image. 
         
- Step 8: Convert the watermarked Image now into complete image portion by portion .

## EXTRACTION [Blind water marking - therefore host image not needed for this].
- Step 1: Combine and convert back portions using inverse spiral of matrix in each portion.
- Step 2: Apply DWT to this watermarked Image which may be altered or unaltered.
- Step 3: Apply DWT in (HL1 to form four frequency sub-bands)
- Step 4: Divide sub-bands like step 3 in embedding into 4*4 blocks.
- Step 5: DCT will be applied now to chosen sub-band and take out the mid-band coefficients for each DCT transformed 4*4 block. 
- Step 6: Regenerate watermark pattern , this will help in comparing the original watermark with the current coefficients and will help in tamper localisation.
- Step 7: For each block in the sub-band (HL2 or HH2), calculate the correlation between the mid-band coefficients and generated pattern from previous step. Based on correlation mark each of this watermarking bits [this will be based on whether the watermarking image is RGB or GRAY ], after remaking the watermark time to compare both original and extracted for tamper localisation and authenticity.
- Step 8: Reconstruct the watermark using the extracted watermark bits, and compute the dis-similarity between the original and extracted watermarks. 

## Result Evaluation
- DCT: 
> PSNR = 41.4
MSE = 0.67

> While transmission can be easily altered and attacked can get to know the type of information being transmitted.

> Perceptibility * fragility  =  medium.

> Not suitable for image contains almost same intensities or pixel values.

> Robustness and image quality after embedding = medium.

- DWT:

> PSNR=27.46
MSE=17.45

> While transmission can be easily altered and attacked can get to know the type of information being transmitted.

> Perceptibility * fragility  =  medium.

>   Robustness and Image quality = low.

- PROPOSED ALGORITHM:

> PSNR = 100

> Perceptibility * fragility  =  high.

>  Solves Drawbacks of both

>   Image quality after embedding = high , 
But not as good as original.

> Robustness = High
