# Pixel Tools
## Preferences
![Preferences](https://github.com/Morphinometr/Pixel_Tools/blob/readme/images/preferences.png)

Укажите путь к проекту на вашем компьютере.

Для полноценной работы необходимо включить стандартный аддон Interface: Copy Attributes Menu. А также установить аддон Import-Export: Better FBX Importer & Exporter, Object: Texel Density Checker.

## Layout
![Layout](https://github.com/Morphinometr/Pixel_Tools/blob/readme/images/layout.png)

Раздел предназначен в основном для подготовки к презентациям. Но может также использоваться и для быстрого импорта аватаров/пушек.

* "Avatar Tag" и "Weapon Tag" - тег по которому ищется нужный fbx в проекте. Также эти поля используются при сборке рига для презентации.
  > *Нужно копировать содержимое ячейки таблицы, а не саму ячейку. Ячейка может содержать скрытые символы, которые Блендер не распознаёт*

* "Weapon Number" - номер оружия, используется при сборке рига для презентации для автоматического переименования костей.
  > *Например, для Weapon1550 вписать только номер 1550*

* "Import Avatar" - импортирует fbx аватара и ищет связанные с ним текстуры. Также по-умолчанию пикселизирует все его текстуры и настраивает материал чтобы при рендере выглядел плоским (убирает металичность, спекуляр и эмиссию).
  > *Если fbx ссылается на png текстуру, а в проекте только psd она найдена не будет*

* "Import Weapon" - то же что и для аватара, только для оружия.

* "Fix Imported Rig" - правит косяк когда Better Exporter импортирует риг как ротомка пустышки. Этот оператор убирает родителя, на его месте создает кость и убирает клю анимации с объекта арматуры.
  > *При импорте из Maya новая кость имеет неправильную ориентацию. Нужно перепроверять в проекте*

* "Combine Rigs" - для презентаций. Соединяет риг оружия (выделенный) и основной риг презентации (активный). Переименовывает кости, вращает FK контроллеры костей в положение рук оружия, привязывает руки оружия к рукам основного рига.


## Modeling
![Modeling](https://github.com/Morphinometr/Pixel_Tools/blob/readme/images/modeling.png)

* "Make pixelated" - Делает пиксельными все текстуры всех материалов всех выделенных и активного объектов.

* "Optimize" - Сшивает меш, удаляет внутренние вершины и ребра плоских граней активного объекта. Также сбрасывает нормали вершин. Используется для первичной оптимизации моделей из воксельных редакторов. 
  > *Этот оператор не заменяет ручной оптимизации. Использовать только как подготовительный этап*

* "Test Material" - Создаёт тестовый материал, если такового нет в сцене, назначет его на выделенные объекты. Тестовый материал защищен от удаления, имеет текстуру цвета и запекания, которые автоматичиски назначаются следующим оператором.

* "Set Texture" - Назначает текстуру для развёртки и запечки выбранного разрешения тестовому материалу.

* "Unwrap" - Делает все жёсткие рёбра швами и разворачмвает меш.
  > *Делает только первоначальную развёртку. Дальше ручками*

* "Set Texel Density" - Масштабирует выденный участок развёртки в соответствии с выбранным размером текстуры и плотностью пикселей. Не меняет саму развёртку.
  > *Для работы необходим аддон Object: Texel Density Checker*

* "Reload Textures" - Перезагружает все текстуры для выделенных и активного объектов.

## Rigging
![Rigging](https://github.com/Morphinometr/Pixel_Tools/blob/readme/images/rigging.png)

> *Раздел сырой*

* "Add Bone" - Создаёт кость в выбранной арматуре, которая учитывает масштаб юнитов сцены.

* "Create simple controls" - Создаёт контрольные кости для выделенных костей рига. 
  > *Есть возможность выбрать слой для костей и изменение их формы на куб*