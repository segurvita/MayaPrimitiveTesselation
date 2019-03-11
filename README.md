# MayaPrimitiveTesselation

トポロジーが綺麗なメッシュのポリゴンが必要だったので作成しました。



トポロジーが綺麗とは、

- メッシュが綺麗に整列している。

- メッシュの面積の大小の差が小さい。

という意味で使っています。



# fbx

| ファイル名                 | 形状     | 補足 |
| -------------------------- | -------- | ---- |
| pCone.fbx                  | 円錐     |      |
| pCube.fbx                  | 立方体   |      |
| pCylinder.fbx              | 円柱     |      |
| pPipe.fbx                  | 円管     |      |
| pSphere.fbx                | 球       |      |
| pSphereFromCatmullCube.fbx | 球       |      |
| pTorus.fbx                 | トーラス |      |



# pSphereFromCatmullCube.fbx  

`pSphere.fbx` と `pSphereFromCatmullCube.fbx` はどちらも球形状ですが、メッシュの配置が違います。

`pSphere.fbx` は 正距円筒図法をもとにメッシュを配置しています。世界地図のようなテクスチャを貼り付けるときは計算が楽です。しかし、北極と南極が特異点となっており、エッジが集中しています。特異点付近よりも、赤道付近のメッシュの方が面積が大きいです。

`pSphereFromCatmullCube.fbx` はCubeをCatmullClark Subdivisionで細分割したメッシュを、球状に再配置したものです。北極と赤道でメッシュの面積が同等になります。比較的トポロジーが綺麗です。



# PrimitiveTesselation.ma

上記のfbxを生成するために使用したMayaの編集ファイルです。