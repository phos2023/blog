---
title: QML 创建自定义的类
date: 2025-02-10 18:49:08
tags:
    - Qt
    - QML
    - Python
    - PySide
---

转载自 [Qt-PySide2-Primer](https://github.com/hubenchang0515/Qt-PySide2-Primer/blob/master/note/qml/08.custom_class.md)，年代久远，PySide2 无法在新版本的 Python 中运行，建议替换为 PySide6，原文的代码仍可使用。

# 创建自定义的类
在相同目录下创建单独的qml文件，即可将该文件的文件名作为类名来创建对象，不需要使用`import`导入。  

例如，将[使用Canvas绘图](./note/qml/07.canvas.md)中设计的数码管风格数字显示器的代码放在单独的文件中。将文件命名为`Tube.qml`，即可用`Tube`作为类名创建对象。  

下面代码使用`Tube`显示了多个数字 :  

```QML
import QtQuick 2.13
import QtQuick.Window 2.13

Window {
    id: mainWindow
    visible: true
    width: 640
    height: 400
    title: qsTr("PySide2 QML")

    Row {
        spacing: 20 // Row中元素之间的间隔

        Tube {
            color: "red"
            number: 2
        }

        Tube {
            color: "orange"
            number: 0
        }

        Tube {
            color: "yellow"
            number: 1
        }

        Tube {
            color: "green"
            number: 9
        }
    }
}
```

![2019](https://github.com/hubenchang0515/Qt-PySide2-Primer/raw/master//image/qml/08.custom_class/2019.png)