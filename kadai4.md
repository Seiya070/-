# 課題４　画像のヒストグラム
画素の濃度ヒストグラムを生成せよ．

ORG=imread('view.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/4-1.png?raw=true)  
図1 白黒画像

imhist(ORG); % ヒストグラムの表示  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/4-2.png?raw=true)  
図2 ヒストグラム

この画像のヒストグラムは元の画像に白い部分が多いため、
輝度が高い部分が特に飛びぬけている。  
また、課題3の結果と比較して、対象と背景を分ける場合、
ヒストグラムの谷である輝度200付近で閾値を定めると対象物がはっきりと分かる。
