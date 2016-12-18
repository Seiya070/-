# 課題９ メディアンフィルタと先鋭化
メディアンフィルターを適用し，ノイズ除去を体験せよ．


元の白黒画像  
ORG=imread('view.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/9-1.png?raw=true)  
図1 白黒画像

ノイズを付加  
ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/9-2.png?raw=true)  
図2 ノイズ添加後

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/9-3.png?raw=true)  
図3 平滑フィルタ適応後

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/9-4.png?raw=true)  
図4 メディアンフィルタ適応後

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/9-5.png?raw=true)  
図5 設計フィルタの適応

ノイズ添加後画像に対し、平滑化フィルタとメディアンフィルタの適応後の画像を見比べると、
平滑化フィルタではノイズを画像全体に分散させているように見えるのに対し、
メディアンフィルタではノイズそのものを除去しているように確認できる。  
この結果より、より画像の輪郭を鮮明にするならば、
平滑化フィルタよりもメディアンフィルタのほうが適しているように思われる。
