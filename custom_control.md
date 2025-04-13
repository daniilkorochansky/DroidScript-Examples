# Как добавить сторонний элемент в наше Hybrid приложение?
Чтобы добавить сторонний элемент в наше приложение воспользуемся **ui.addHTMLElement** который входит в плагин UI

Добавим редактор кода Ace.

## Пример кода
```javascript
app.Script("Html/ace.js") //Скачайте библиотеку и распакуйте содержимое в заранее созданную вами в вашем проекте папку "Html"

class Main extends App
{
    onStart()
    {
        this.main = ui.addLayout("main", "Linear", "VCenter,FillXY")

        this.editorElement = ui.addHTMLElement(this.main, "div", "", 1, 1)
        
        var editor = ace.edit(this.editorElement.el)
        this.editor.setTheme("ace/theme/twilight")
       this.editor.session.setMode("ace/mode/python")
       this.editor.insert("print('Hello World')")
    }
}
```
