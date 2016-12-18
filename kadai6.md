# 課題６　画像の二値化
判別分析法を用いて画像二値化せよ．


元の白黒画像  
ORG=imread('view.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/6-1.png?raw=true)  
図1 白黒画像

輝度128を境に二値化  
IMG = ORG>128; % 128による二値化
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/6-2.png?raw=true)  
図2 128による二値化

ディザ法  
IMG = dither(ORG); % ディザ法による二値化
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/6-2.png?raw=true)  
図2 ディザ法による二値化

ディザ法による二値化は128を境にしたものに比べ、
物の輪郭は取れているように見えるが、
全体的にゴマ粒のようなものが乗っている。  
一方、128を境にした二値化では全体的に白っぽい。
