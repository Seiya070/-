# 課題8　ラベリング
二値化された画像の連結成分にラベルをつけよ．


元の白黒画像  
ORG=imread('view.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/8-1.png?raw=true)  
図1 白黒画像

二値化後の画像  
IMG = ORG > 128; % 閾値128で二値化  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/8-2.png?raw=true)  
図2 二値化後

ラベリング  
IMG = bwlabeln(IMG);
imagesc(IMG); colormap(jet); colorbar; % 画像の表示  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/8-3.png?raw=true)  
図2 ラベリング結果

二値化後の画像は白部分が非常に多く、広範囲で連結しているため、
ラベリング後の結果を見ると、中央の像は輪郭すら確認できない。
一方、像の左右にある木は輪郭が何となく分かるものとなっている。
