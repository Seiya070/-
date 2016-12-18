# 課題２　階調数と疑似輪郭
２階調，４階調，８階調の画像を生成せよ．

画像から白黒画像を生成する。

clear; % 変数のオールクリア  
ORG=imread('view.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;  
imagesc(ORG); axis image; % 画像の表示  

![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/2-1.png?raw=true)  
図1 白黒画像

2階調128bitの範囲で白黒を分ける。
% ２階調画像の生成  
IMG = ORG>128;  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/2-2.png?raw=true)  
図2 2階調

4階調64bitの範囲で濃淡を区別。
% ４階調画像の生成  
IMG0 = ORG>64;  
IMG1 = ORG>128;  
IMG2 = ORG>192;  
IMG = IMG0 + IMG1 + IMG2;  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/2-3.png?raw=true)  
図3 4階調

8階調32bitの範囲で濃淡を分ける。
% ８階調画像の生成  
IMG0 = ORG>32;  
IMG1 = ORG>64;  
IMG2 = ORG>96;  
IMG3 = ORG>128;  
IMG4 = ORG>160;  
IMG5 = ORG>192;  
IMG6 = ORG>224;  
IMG = IMG0 + IMG1 + IMG2 + IMG3 + OMG4 + IMG5 + IMG6;  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/2-4.png?raw=true)  
図4 8階調

以上のようにグレースケールの濃淡の表現を細かくすることで、
2階調、4階調、8階調の順に画像が鮮明になる。

