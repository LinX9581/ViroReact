
# QUICK
[官方入門文件](https://docs.viromedia.com/docs/quick-start-windows)  
[Set up Android Studio with ViroReact](https://docs.viromedia.com/docs/installing-viro-android)  

## Windows 環境安裝
Mac 有Cli , Windows通通要手動Q  
```
react-native init ProjectAR --version=0.59.3
cd ProjectAR
npm install -S -E react-viro
```
把下面路徑 javascript裡面檔案 全丟到專案裡面並取代
ProjectAR\node_modules\react-viro\bin\files\javascript
更改 index.android.js 第四行
AppRegistry.registerComponent('ProjectAR', () => App);
更改 App.js API Key
396D77A3-A4F0-4E99-9466-D8778E94FCAD

## 限 Mac Linux 的 AndroidStudio 環境才能用
手動執行 setup-ide.sh 檔案在下面目錄  
\ProjectAR\node_modules\react-viro\bin  
需要移檔案到根目錄ProjectAR    
終端機 執行 setup-ide.sh android  

## 限 Windows AndroidStudio 環境
手動執行 android-setup.sh 檔案在下面目錄  
\ProjectAR\node_modules\react-viro\bin  
需要移檔案到根目錄ProjectAR  
終端機 執行 android-setup.sh 然後會失敗...  
官方回應 Our android-setup.sh script hasn't been tested with windows  

文件只有給 [Windows Setup Diff](https://gist.github.com/manbod/5a7f7d0511ff4b4c7f78086ee4706932)
只能手動慢慢改  
最下面的 android/settings.gradle 要先改  
不然會一直error..  

## 手機支援 ARCore 
如果最後還是跑不出畫面  
那可能是手機沒支援ARCore.....  
[支援列表](https://developers.google.com/ar/discover/supported-devices)  
官方的 [IsARSupportedOnDevice](https://docs.viromedia.com/docs/isarsupportedondevice) 藏在最下面  


## 測試
AndroidStudio 要能build成功  
把專案build到手機 (要插線)  
cd android && ./gradlew.bat installGvrDebug  
npm start  
再用ngrok http 8080 把網址丟到[Viromedia](https://play.google.com/store/apps/details?id=com.viromedia.viromedia&hl=zh_TW)  

## 實用issue
https://github.com/viromedia/viro/issues/593
https://github.com/viromedia/viro/issues/177
https://github.com/viromedia/viro/issues/563

## 版本坑
如果用的是 [官方舊版 SampleCode](https://github.com/viromedia/ViroARSampleApp)  
但套件裝的是新版的 Viro React2.14  
會一直叫你更新SDK Build Tools version 到 28.0.3 舊版的是23.0.1  

可以試試[新版範例](https://github.com/viromedia/viro)  






