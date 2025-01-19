# 準備方法
## FFMEG以外の準備は以下を参考に
[外部webサイト](https://studentwalker.com/spotdl){:target="_blank"}
## FFMEGのダウンロード
1. [ダウンロードサイト](https://github.com//BtbN/FFmpeg-Builds/releases/download/latest/ffmpeg-master-latest-win64-gpl-shared.zip){:target="_blank"}をクリック
2. Windowsボタン+R(同時に押す)で出てきたポップに**powershell**と入力しOKを押す
   ![画面1](/images/executeBox.png)
3. 以下をPowerShellで実行
   1.
   ```
   cd $env:USERPROFILE
   ``` 
   1. 
    ```
    Expand-Archive -Path $env:USERPROFILE\Downloads\ffmpeg-master-latest-win64-gpl-shared.zip -DestinationPath $env:USERPROFILE\Downloads\
    ```
    ![画面2](/images/expandArchive.png)
    2.
    ```
    new-item ProgramFiles -ItemType Directory
    ```
    2.
    ```
    Move-Item -Path $env:USERPROFILE\Downloads\ffmpeg-master-latest-win64-gpl-shared -Destination $env:USERPROFILE\ProgramFiles
    ```
    3.
    ```
    [System.Environment]::SetEnvironmentVariable("PATH", [System.Environment]::GetEnvironmentVariable("PATH","User") + ";$env:USERPROFILE\ProgramFiles\ffmpeg-master-latest-win64-gpl-shared\bin", "User")
    ```
    4.
    ```
    $env:PATH = [System.Environment]::GetEnvironmentVariable("PATH", "User")
    ```
## Music Center For PCのダウンロード
1. [ダウンロードリンク](https://info.update.sony.net/PP002/MusicCenterForPcSSL/contents/0014/musiccenter_setup_2.7.1.exe){:target="_blank"}をクリック
2.  以下をPowerShellで実行
```
invoke-item $env:USERPROFILE\Downloads\musiccenter_setup_2.7.1.exe
```
3. 画面に従ってインストール

## 準備完了後の使い方
1. 
```
cd $env:USERPROFILE\
```
2. 曲をダウンロード
```
spotdl [楽曲URL or  PlayListUrl] --output Music/spotdl
```
3.ダウンロードされた曲のフォルダーの開き方
```
invoke-item $env:USERPROFILE\Music\spotdl
```
4.  [曲の取り込み方](https://knowledge.support.sony.jp/electronics/support/articles/MC4PC020041){:target="_blank"}、[転送の仕方](https://knowledge.support.sony.jp/electronics/support/articles/MC4PC020056){:target="_blank"}を参考に