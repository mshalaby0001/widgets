# widgets

## Text Widget 

Here’s a summary of the [Flutter `Text` class documentation](https://api.flutter.dev/flutter/widgets/Text-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Text` Widget**
The `Text` widget is used to display a string of text with a single style in a Flutter application. It is one of the most commonly used widgets for rendering text.

---

### **1. Basic Usage**
The simplest way to use the `Text` widget is to provide a string of text.

#### Example:
```dart
Text('Hello, Flutter!');
```

---

### **2. Styling Text**
You can style the text using the `style` parameter, which accepts a `TextStyle` object.

#### Example:
```dart
Text(
  'Hello, Flutter!',
  style: TextStyle(
    fontSize: 24,
    fontWeight: FontWeight.bold,
    color: Colors.blue,
  ),
);
```

---

### **3. Text Alignment**
You can align text within its container using the `textAlign` property.

#### Example:
```dart
Text(
  'Hello, Flutter!',
  textAlign: TextAlign.center,
);
```

---

### **4. Text Overflow**
You can handle text overflow (when the text exceeds the available space) using the `overflow` property.

#### Example:
```dart
Text(
  'This is a very long text that might overflow.',
  overflow: TextOverflow.ellipsis,
);
```

---

### **5. Max Lines**
You can limit the number of lines of text using the `maxLines` property.

#### Example:
```dart
Text(
  'This is a very long text that will be limited to two lines.',
  maxLines: 2,
  overflow: TextOverflow.ellipsis,
);
```

---

### **6. Rich Text**
You can display text with multiple styles using the `Text.rich` constructor and the `TextSpan` widget.

#### Example:
```dart
Text.rich(
  TextSpan(
    text: 'Hello, ',
    style: TextStyle(fontSize: 20),
    children: <TextSpan>[
      TextSpan(
        text: 'Flutter',
        style: TextStyle(fontWeight: FontWeight.bold, color: Colors.red),
      TextSpan(
        text: '!',
      ),
    ],
  ),
);
```

---

### **7. Text Direction**
You can specify the text direction (e.g., left-to-right or right-to-left) using the `textDirection` property.

#### Example:
```dart
Text(
  'Hello, Flutter!',
  textDirection: TextDirection.rtl, // Right-to-left
);
```

---

### **8. Locale**
You can specify the locale for the text using the `locale` property.

#### Example:
```dart
Text(
  'Hello, Flutter!',
  locale: Locale('es', 'ES'), // Spanish locale
);
```

---

### **9. Strut Style**
You can control the vertical layout of text using the `strutStyle` property.

#### Example:
```dart
Text(
  'Hello, Flutter!',
  strutStyle: StrutStyle(
    fontSize: 24,
    height: 1.5,
  ),
);
```

---

### **10. Text Scaling**
You can control how text scales with the system font size using the `textScaleFactor` property.

#### Example:
```dart
Text(
  'Hello, Flutter!',
  textScaleFactor: 1.5, // Increases text size by 50%
);
```

---

### **11. Selection and Interaction**
You can make text selectable using the `SelectableText` widget (not part of the `Text` class but related).

#### Example:
```dart
SelectableText(
  'Hello, Flutter!',
  style: TextStyle(fontSize: 20),
);
```

---

### **Summary of `Text` Widget Properties**
| Property          | Description                              | Example                                   |
|-------------------|------------------------------------------|-------------------------------------------|
| `data`            | The text to display                      | `Text('Hello, Flutter!')`                |
| `style`           | Text styling (`TextStyle`)               | `style: TextStyle(fontSize: 24)`         |
| `textAlign`       | Text alignment                           | `textAlign: TextAlign.center`            |
| `overflow`        | Text overflow handling                   | `overflow: TextOverflow.ellipsis`        |
| `maxLines`        | Maximum number of lines                  | `maxLines: 2`                            |
| `textDirection`   | Text direction (e.g., LTR or RTL)        | `textDirection: TextDirection.rtl`       |
| `locale`          | Locale for the text                      | `locale: Locale('es', 'ES')`             |
| `strutStyle`      | Vertical layout control                  | `strutStyle: StrutStyle(fontSize: 24)`   |
| `textScaleFactor` | Scaling factor for text size             | `textScaleFactor: 1.5`                   |
| `Text.rich`       | Rich text with multiple styles           | `Text.rich(TextSpan(...))`               |

---

### **Example: Full Usage**
Here’s an example combining multiple properties:
```dart
Text(
  'Hello, Flutter!',
  style: TextStyle(
    fontSize: 24,
    fontWeight: FontWeight.bold,
    color: Colors.blue,
  ),
  textAlign: TextAlign.center,
  overflow: TextOverflow.ellipsis,
  maxLines: 1,
);
```

---

