# 課題7　ダイナミックレンジの拡大
画素のダイナミックレンジを０から２５５にせよ．


元の白黒画像  
ORG=imread('view.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/7-1.png?raw=true)  
図1 白黒画像

![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/7-2.png?raw=true)  
図2 原画像のヒストグラム

ORG = double(ORG);  
mn = min(ORG(:)); % 濃度値の最小値を算出
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;

![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/7-3.png?raw=true)  
図3 ダイナミックレンジ変更の結果

unit8についての考察
ORG = uint8(ORG);  
uint8は8bit符号なし整数への変換を行う関数である。  
8bitでは値が0～255までの範囲を取る。  

imhist(ORG); % 濃度ヒストグラムを生成、表示
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/7-4.png?raw=true)  
図4 変更後のヒストグラム


変更前と後の画像を見比べても違いは特に確認できない。  
しかし、ヒストグラムを比較した場合、
変更後では輝度が40、90、170、240辺りで出現頻度が0になっている。  