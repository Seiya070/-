# 課題10 画像のエッジ抽出 
次のプログラムを参考にして，エッジ抽出を体験せよ．


元の白黒画像  
ORG=imread('view.png'); % 原画像の入力  
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換  
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/10-1.png?raw=true)  
図1　白黒画像

プレウィット法  
IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/10-2.png?raw=true)  
図2　プレウィット法によるエッジ抽出

ソベル法  
IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/10-3.png?raw=true)  
図3　ソベル法によるエッジ抽出

キャニー法  
IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
![原画像](https://github.com/Seiya070/Image_Process/blob/master/image/10-4.png?raw=true)  
図4　キャニー法によるエッジ抽出

3つの方法によるエッジ抽出の結果を比較すると、
この原画像からでは、プレウィット法とソベル法の違いは特に目立たないが、
キャニー法は他2つの方法と比べて、細かく輪郭を抽出しているのが見てわかる。  
この原画像では、中央の像と左右の木の輪郭はどの方法でも判別可能だが、
キャニー法出なければ中央の像の台座の輪郭は確認できない。
