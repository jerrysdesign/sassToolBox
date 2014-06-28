#sassToolBox

sassToolBox參考了[compass](http://compass-style.org/)與[bourbon](http://bourbon.io/) 兩大sass Library，根據項目實務，歸納總結而成，並持續更新中...

sassToolBox提供了一些基礎和常用的東西，基於它你可以擴展出很多組件等，如果你對這個有興趣，可以參考下基於sassToolBox的[Jerry](http://www.sasstoolbox.com)建構中。

##如何使用？

sassToolBox分核心文件和擴展文件兩種。其中核心文件提供一些基礎的樣式和`@mixin`，`%`等方便調用；而擴展文件則提供一些模塊的樣式，如`form`，`table`等。

詳細使用文檔請移步：[sassToolBox](http://sasstoolbox/index.html)

###核心文件調用
第一種除提供基礎功能外，會產生一份reset樣式：

@import "/sass/_toolbox/base";

第二種不產生任何樣式，只提供功能的調用：

@import "/sass/_toolbox/function";

###擴展文件調用

根據需要調用，以table為例：

@import "d:/sassToolBox/ext/table";

注：因為sass不能導入線上sass文件，而sassToolBox也沒有提供安裝版的使用，所以預設統一放在/sass/_toolbox進行調用。

##五大特點：

* sassToolBox涵蓋範圍廣。核心文件有setting，css3，media-queries，mixin，grid，reset；擴展文件有animate，font-face，btn，message，form，table，helps，typography；除此之外還有兩個集合文件function和base。
* sassToolBox對瀏覽器相容性採用了開關控制機制。如對於是否支援ie6/7可以通過設置為true或false以生成對應的原始碼。
* sassToolBox嚴格控製樣式多餘累贅。使用開關變數做到需要什麼樣式就加載什麼樣式，按需開啟，避免樣式多餘累贅。
* sassToolBox設計了兩種調用方式，一種是只調用功能，不產生任何多餘的css原始碼；另一種是包含了些重置樣式。為團隊的合作開發提供了良好的解決方案。
* sassToolBox借鑒優秀的作品，根據經驗創造新的方法，緊跟前沿，每一個文件都是經過深思熟慮，幾易其稿，在實用和卓越上狠下功夫。

##文件簡述

sassToolBox包括兩個集合文件（base，function）和兩個文件夾（core，ext）。其中core文件夾中為核心基礎文件，包括setting，css3，media-queries，mixin，grid，reset；而ext文件夾中是一些擴展文件，包括animate，font-face，btn，message，form，table， typography，helper。

兩個集合文件（base，function）導入的都是core中的文件，區別在於base除了提供基本功能之外還會生成一份reset樣式，而function則只提供基本功能。至於ext中的文件則屬於額外的一些模塊擴展，可根據需​​求導入。

###core文件

####setting
負責基礎變數的文件，如常用的顏色，字體等變數。

####css3
負責css3屬性前綴的文件。參考了[bourbon](http://bourbon.io/)，然後進行一系列的擴展及優化，以使解析出來的原始碼更加合理。

####media-queries
負責響應式寬度判斷的文件。主要是對響應式佈局的一些寬度判斷，來自paranoida的[sass-mediaqueries](https://github.com/paranoida/sass-mediaqueries)。

####mixin
負責功能方面的文件。這裡我們大概分成三個部分，一個是混合部分即mixin，一個是placeholder選擇器部分即%，最後就是我們的function函式部分。我們常用的include及extend當然就是來自於這裡了。

####grid
負責網格系統的文件。預設為固定寬度佈局（1000px），可以通過設置$gridPercentSwitch為true來切換為流體佈局，也可以通過設置$gridSpanSwitch為true或false來控制是否輸出各個網格的class。

###reset
在[normalize](http://necolas.github.io/normalize.css/)的基礎上，根據目前多數使用習慣進行了一些歸零行動，及設置文字字體顏色，是否輸出打印樣式。

###ext文件

####animate
將[animate.css](http://daneden.github.io/animate.css/)轉成scss版本，預設不輸出任何樣式，需要什麼動畫先導入對應的動畫文件，然後include調用即可。

####font-face
來自[Font Awesome](http://fontawesome.io/)的字體圖示，可以根據自己的需求使用其他字體圖示，預設不輸出任何class，可根據實際需求輸出其中的某些icon。

####btn
為按鈕設計的文件，裡面定義了一系列mixin，可用於自定義按鈕，預設生成兩種按鈕

####message
互動提示信息，包括警告，錯誤，成功，提示四種狀態的樣式

####form
提供表單元素樣式及幾種常見的表單組合樣式，可通過變數控制輸出

####table
提供幾種常用的表格樣式，可通過變數來控制輸出

####helper
常用的幾個class樣式，可以根據自己的喜好定義。

####typography
負責文字排版的文件。這裡主要考慮到文章詳細頁和其他頁面的一些不同情況而給詳細頁加入了article這個class，裡面的一些元素如ul，li，p給予一定的樣式，而不是歸零。