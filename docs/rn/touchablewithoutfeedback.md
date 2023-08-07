---
description: Обертка, позволяющая заставить представления правильно реагировать на прикосновения. При нажатии отсутствует визуальная обратная связь
---

# TouchableWithoutFeedback

!!!note ""

    Если вы ищете более широкий и перспективный способ обработки сенсорного ввода, обратите внимание на API [Pressable](pressable.md).

Не используйте его, если у вас нет очень веских причин. Все элементы, реагирующие на нажатие, должны иметь визуальную обратную связь при касании.

`TouchableWithoutFeedback` поддерживает только один дочерний элемент. Если вы хотите иметь несколько дочерних компонентов, оберните их в `View`. Важно отметить, что `TouchableWithoutFeedback` работает путем клонирования своего дочернего компонента и применения к нему пропса `responder`. Поэтому необходимо, чтобы любые промежуточные компоненты передавали эти пропсы базовому компоненту React Native.

## Шаблон использования

```ts
function MyComponent(props: MyComponentProps) {
    return (
        <View
            {...props}
            style={{ flex: 1, backgroundColor: '#fff' }}
        >
            <Text>My Component</Text>
        </View>
    );
}

<TouchableWithoutFeedback onPress={() => alert('Pressed!')}>
    <MyComponent />
</TouchableWithoutFeedback>;
```

## Пример

<div data-snack-id="@bndby/touchablewithoutfeedback-example" data-snack-platform="web" data-snack-preview="true" data-snack-theme="light" style="overflow:hidden;background:#F9F9F9;border:1px solid var(--color-border);border-radius:4px;height:505px;width:100%"></div>

## Свойства

### accessibilityIgnoresInvertColors

| Тип    |
| ------ |
| Булево |

### accessible

Когда `true`, указывает, что представление является доступным элементом. По умолчанию все осязаемые элементы являются доступными.

| Type   |
| ------ |
| `bool` |

### accessibilityLabel

Переопределяет текст, который считывается программой чтения с экрана, когда пользователь взаимодействует с элементом. По умолчанию метка строится путем обхода всех дочерних элементов и накопления всех узлов `Text`, разделенных пробелом.

| Тип    |
| ------ |
| строка |

### accessibilityLanguage :simple-ios:

Значение, указывающее, какой язык должен использоваться программой чтения с экрана, когда пользователь взаимодействует с элементом. Оно должно соответствовать спецификации [BCP 47](https://www.rfc-editor.org/info/bcp47).

Дополнительную информацию см. в документе [iOS `accessibilityLanguage` doc](https://developer.apple.com/documentation/objectivec/nsobject/1615192-accessibilitylanguage).

| Тип    |
| ------ |
| строка |

### accessibilityHint

Подсказка доступности помогает пользователям понять, что произойдет, когда они выполнят действие над элементом доступности, если результат не ясен из надписи доступности.

| Тип    |
| ------ |
| строка |

### accessibilityRole

`accessibilityRole` передает назначение компонента пользователю вспомогательной технологии.

`accessibilityRole` может быть одним из следующих:

-   `'none'` - Используется, когда элемент не имеет роли.
-   `'button'` - Используется, когда элемент должен рассматриваться как кнопка.
-   `'link'` - Используется, когда элемент должен рассматриваться как ссылка.
-   `'search'` - Используется, когда элемент текстового поля должен также рассматриваться как поле поиска.
-   `'image'` - Используется, когда элемент должен рассматриваться как изображение. Может сочетаться, например, с кнопкой или ссылкой.
-   `'keyboardkey'` - Используется, когда элемент действует как клавиша клавиатуры.
-   `'text'` - Используется, когда элемент должен рассматриваться как статичный текст, который не может изменяться.
-   `'adjustable'` - Используется, когда элемент может быть "отрегулирован" (например, ползунок).
-   `'imagebutton'` - Используется, когда элемент должен рассматриваться как кнопка, а также является изображением.
-   `'header'` - Используется, когда элемент действует как заголовок для раздела содержимого (например, заголовок навигационной панели).
-   `'summary'` - Используется, когда элемент может быть использован для предоставления краткой информации о текущих условиях в приложении при первом запуске.
-   `'alert'` - Используется, когда элемент содержит важный текст, который должен быть представлен пользователю.
-   `'checkbox'` - Используется, когда элемент представляет флажок, который может быть отмечен, снят или иметь смешанное состояние.
-   `'combobox'` - Используется, когда элемент представляет собой комбинированное окно, которое позволяет пользователю выбирать из нескольких вариантов.
-   `'menu'` - Используется, когда компонент представляет собой меню выбора.
-   `'menubar'` - Используется, когда компонент представляет собой контейнер нескольких меню.
-   `'menuitem'` - Используется для представления пункта в меню.
-   `'progressbar'` - Используется для представления компонента, который показывает прогресс выполнения задачи.
-   `'radio'` - Используется для представления радиокнопки.
-   `'radiogroup'` - Используется для представления группы радиокнопок.
-   `'scrollbar'` - Используется для представления полосы прокрутки.
-   `'spinbutton'` - Используется для представления кнопки, которая открывает список вариантов.
-   `'switch'` - Используется для представления переключателя, который можно включать и выключать.
-   `'tab'` - Используется для представления вкладки.
-   `'tablist'` - Используется для представления списка вкладок.
-   `'timer'` - Используется для представления таймера.
-   `'toolbar'` - Используется для представления панели инструментов (контейнер кнопок действий или компонентов).

| Тип    |
| ------ |
| строка |

### accessibilityState

Описывает текущее состояние компонента для пользователя вспомогательной технологии.

См. руководство [Accessibility guide](accessibility.md#accessibilitystate-ios-android) для получения дополнительной информации.

| Тип                                                                                             |
| ----------------------------------------------------------------------------------------------- |
| объект: {disabled: bool, selected: bool, checked: bool или 'mixed', busy: bool, expanded: bool} |

### accessibilityActions

Действия доступности позволяют ассистивной технологии программно вызывать действия компонента. Свойство `accessibilityActions` должно содержать список объектов действий. Каждый объект действия должен содержать имя поля и метку.

Дополнительную информацию см. в [Руководстве по доступности](accessibility.md#accessibility-actions).

| Тип    |
| ------ |
| Массив |

### aria-busy

Указывает на то, что элемент изменяется и что вспомогательные технологии могут захотеть подождать, пока изменения не будут завершены, прежде чем информировать пользователя об обновлении.

| Тип    | По умолчанию |
| ------ | ------------ |
| булево | `false`      |

### aria-checked

Указывает на состояние элемента с флажком. Это поле может принимать либо булево значение, либо строку "mixed" для представления смешанных флажков.

| Тип             | По умолчанию |
| --------------- | ------------ |
| булево, "mixed" | `false`      |

### aria-disabled

Указывает, что элемент воспринимается, но отключен, поэтому его нельзя редактировать или использовать другим способом.

| Тип    | По умолчанию |
| ------ | ------------ |
| булево | `false`      |

### aria-expanded

Указывает, является ли расширяемый элемент в данный момент развернутым или свернутым.

| Тип       | По умолчанию |
| --------- | ------------ |
| `boolean` | `false`      |

### aria-hidden

Указывает, являются ли элементы доступности, содержащиеся в этом элементе доступности, скрытыми.

Например, в окне, содержащем родственные представления `A` и `B`, установка `aria-hidden` в `true` для представления `B` заставляет VoiceOver игнорировать элементы в представлении `B`.

| Тип    | По умолчанию |
| ------ | ------------ |
| булево | `false`      |

### aria-label

Определяет строковое значение, которое маркирует интерактивный элемент.

| Тип    |
| ------ |
| строка |

### aria-live :simple-android:

Указывает, что элемент будет обновляться, и описывает типы обновлений, которые агенты пользователя, вспомогательные технологии и пользователь могут ожидать от живого региона.

-   **off** Службы доступности не должны объявлять об изменениях в этом представлении.
-   **polite** Службы доступности должны объявлять об изменениях в этом представлении.
-   **assertive** Службы доступа должны прерывать текущую речь, чтобы немедленно объявить об изменениях в этом представлении.

| Тип                                  | По умолчанию |
| ------------------------------------ | ------------ |
| `enum('assertive', 'off', 'polite')` | `'off'`      |

### aria-modal :simple-ios:

Булево значение, указывающее, должен ли VoiceOver игнорировать элементы в представлениях, которые являются родными братьями и сестрами приемника. Имеет приоритет над [`accessibilityViewIsModal`](#accessibilityviewismodal-ios) prop.

| Тип       | По умолчанию |
| --------- | ------------ |
| `boolean` | `false`      |

### aria-selected

Указывает, выбран ли в данный момент элемент с возможностью выбора или нет.

| Тип       |
| --------- |
| `boolean` |

### onAccessibilityAction

Вызывается, когда пользователь выполняет действия по обеспечению доступности. Единственным аргументом этой функции является событие, содержащее имя выполняемого действия.

Дополнительную информацию см. в [Руководстве по доступности](accessibility.md#accessibility-actions).

| Тип     |
| ------- |
| функция |

### accessibilityValue

Представляет текущее значение компонента. Это может быть текстовое описание значения компонента, или для компонентов, основанных на диапазоне, таких как ползунки и прогресс-бары, оно содержит информацию о диапазоне (минимальное, текущее и максимальное).

Дополнительную информацию см. в [Руководстве по доступности](accessibility.md#accessibilityvalue-ios-android).

| Тип                                                        |
| ---------------------------------------------------------- |
| object: {min: число, max: число, now: число, text: строка} |

### aria-valuemax

Представляет максимальное значение для компонентов, основанных на диапазоне, таких как ползунки и прогресс-бары. Имеет приоритет над значением `max` в пропсе `accessibilityValue`.

| Тип   |
| ----- |
| число |

### aria-valuemin

Представляет минимальное значение для компонентов, основанных на диапазоне, таких как ползунки и прогресс-бары. Имеет приоритет над значением `min` в пропсе `accessibilityValue`.

| Тип   |
| ----- |
| число |

### aria-valuenow

Представляет текущее значение для компонентов, основанных на диапазоне, таких как ползунки и прогресс-бары. Имеет приоритет над значением `now` в пропсе `accessibilityValue`.

| Тип   |
| ----- |
| число |

### aria-valuetuetext

Представляет текстовое описание компонента. Имеет приоритет над значением `text` в пропсе `accessibilityValue`.

| Type   |
| ------ |
| строка |

### delayLongPress

Продолжительность (в миллисекундах) от `onPressIn` до вызова `onLongPress`.

| Тип   |
| ----- |
| число |

### delayPressIn

Продолжительность (в миллисекундах) от начала прикосновения до вызова `onPressIn`.

| Тип   |
| ----- |
| число |

### delayPressOut

Продолжительность (в миллисекундах) с момента отпускания прикосновения до вызова `onPressOut`.

| Тип   |
| ----- |
| число |

### disabled

Если `true`, отключите все взаимодействия для этого компонента.

| Type |
| ---- |
| bool |

### hitSlop

Определяет, насколько далеко ваше прикосновение может отходить от кнопки. Это значение добавляется к `pressRetentionOffset` при отходе от кнопки.

Область касания никогда не выходит за границы родительского представления, и Z-индекс родственных представлений всегда имеет приоритет, если касание попадает на два пересекающихся представления.

| Тип                       |
| ------------------------- |
| [Rect](rect.md) или число |

### id

Используется для определения местоположения данного представления в родном коде. Имеет приоритет над `nativeID`.

| Type   |
| ------ |
| строка |

### onBlur

Вызывается, когда элемент теряет фокус.

| Тип     |
| ------- |
| функция |

### onFocus

Вызывается, когда элемент получает фокус.

| Тип     |
| ------- |
| функция |

### onLayout

Вызывается при монтировании и при изменении макета.

| Type                                                   |
| ------------------------------------------------------ |
| ({nativeEvent: [LayoutEvent](layoutevent.md)}) => void |

### onLongPress

Вызывается, если время после `onPressIn` длится более 370 миллисекунд. Этот период времени можно настроить с помощью параметра [`delayLongPress`](#delaylongpress).

| Тип     |
| ------- |
| функция |

### onPress

Вызывается при отпускании касания, но не при отмене (например, при прокрутке, которая крадет блокировку ответчика). Первый аргумент функции - событие в форме [PressEvent](pressevent.md).

| Тип     |
| ------- |
| функция |

### onPressIn

Вызывается сразу после нажатия на сенсорный элемент и вызывается даже до `onPress`. Это может быть полезно при выполнении сетевых запросов. Первым аргументом функции является событие в форме [PressEvent](pressevent.md).

| Тип     |
| ------- |
| функция |

### onPressOut

Вызывается, как только прикосновение отпускается, еще до `onPress`. Первым аргументом функции является событие в форме [PressEvent](pressevent.md).

| Тип     |
| ------- |
| функция |

### pressRetentionOffset

Когда вид прокрутки отключен, этот параметр определяет, насколько далеко ваше прикосновение может отойти от кнопки, прежде чем кнопка будет деактивирована. После деактивации попробуйте переместить ее обратно, и вы увидите, что кнопка снова активирована! Переместите ее вперед-назад несколько раз, пока вид прокрутки отключен. Убедитесь, что вы передали константу, чтобы уменьшить выделение памяти.

| Тип                       |
| ------------------------- |
| [Rect](rect.md) или число |

### nativeID

| Тип    |
| ------ |
| строка |

### testID

Используется для определения местоположения данного представления в сквозных тестах.

| Тип    |
| ------ |
| строка |

### touchSoundDisabled :simple-android:

Если `true`, не воспроизводит системный звук при касании.

| Type   |
| ------ |
| Булево |