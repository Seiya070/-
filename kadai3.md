# 課題３　閾値処理
閾値を4パターン設定し,閾値処理した画像を示せ．


ORG=imread('view.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/3-1.png?raw=true)  
図1 白黒画像

閾値を64にした場合  
IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換  
imagesc(IMG); colormap(gray); colorbar;  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/3-2.png?raw=true)  
図2 閾値64  

閾値を96にした場合  
IMG = ORG > 96;  
imagesc(IMG); colormap(gray); colorbar;  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/3-3.png?raw=true)  
図3 閾値96  

閾値を128にした場合  
IMG = ORG > 128;  
imagesc(IMG); colormap(gray); colorbar;  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/3-4.png?raw=true)  
図4 閾値128  

閾値を192にした場合  
IMG = ORG > 192;  
imagesc(IMG); colormap(gray); colorbar;  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/3-5.png?raw=true)  
図5 閾値192  

境界値以下の輝度は0となるため、輝度の境界値を上げていくと、
輝度0の画素が増え、徐々に画像全体が黒く変化していく。
