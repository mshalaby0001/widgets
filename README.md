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

## Image Widget 

Here’s a summary of the [Flutter `Image` class documentation](https://api.flutter.dev/flutter/widgets/Image-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Image` Widget**
The `Image` widget is used to display images in a Flutter application. It supports various image sources, such as asset images, network images, and memory images.

---

### **1. Loading Images from Assets**
To display an image from your app's assets, use the `Image.asset` constructor.

#### Example:
```dart
Image.asset(
  'assets/images/flutter_logo.png',
  width: 100,
  height: 100,
);
```

---

### **2. Loading Images from the Network**
To display an image from a URL, use the `Image.network` constructor.

#### Example:
```dart
Image.network(
  'https://example.com/flutter_logo.png',
  width: 100,
  height: 100,
);
```

---

### **3. Loading Images from Memory**
To display an image from binary data in memory, use the `Image.memory` constructor.

#### Example:
```dart
Uint8List imageBytes = ...; // Binary image data
Image.memory(
  imageBytes,
  width: 100,
  height: 100,
);
```

---

### **4. Loading Images from Files**
To display an image from a file, use the `Image.file` constructor.

#### Example:
```dart
File imageFile = File('/path/to/image.png');
Image.file(
  imageFile,
  width: 100,
  height: 100,
);
```

---

### **5. Image Fit**
You can control how the image fits within its container using the `fit` property.

#### Example:
```dart
Image.asset(
  'assets/images/flutter_logo.png',
  width: 200,
  height: 200,
  fit: BoxFit.cover, // Covers the entire container
);
```

---

### **6. Image Alignment**
You can align the image within its container using the `alignment` property.

#### Example:
```dart
Image.asset(
  'assets/images/flutter_logo.png',
  width: 200,
  height: 200,
  alignment: Alignment.center, // Centers the image
);
```

---

### **7. Image Repeat**
You can repeat the image within its container using the `repeat` property.

#### Example:
```dart
Image.asset(
  'assets/images/flutter_logo.png',
  width: 200,
  height: 200,
  repeat: ImageRepeat.repeat, // Repeats the image
);
```

---

### **8. Image Color and Blend Mode**
You can apply a color filter to the image using the `color` and `colorBlendMode` properties.

#### Example:
```dart
Image.asset(
  'assets/images/flutter_logo.png',
  width: 100,
  height: 100,
  color: Colors.blue, // Applies a blue tint
  colorBlendMode: BlendMode.colorBurn, // Blends the color
);
```

---

### **9. Placeholder and Error Widgets**
You can provide placeholder and error widgets for network images using the `loadingBuilder` and `errorBuilder` properties.

#### Example:
```dart
Image.network(
  'https://example.com/flutter_logo.png',
  width: 100,
  height: 100,
  loadingBuilder: (context, child, loadingProgress) {
    if (loadingProgress == null) return child;
    return CircularProgressIndicator(); // Placeholder while loading
  },
  errorBuilder: (context, error, stackTrace) {
    return Text('Failed to load image'); // Error widget
  },
);
```

---

### **10. Image Frame Builder**
You can customize how the image is displayed as it loads using the `frameBuilder` property.

#### Example:
```dart
Image.network(
  'https://example.com/flutter_logo.png',
  width: 100,
  height: 100,
  frameBuilder: (context, child, frame, wasSynchronouslyLoaded) {
    if (wasSynchronouslyLoaded) return child;
    return AnimatedOpacity(
      child: child,
      opacity: frame == null ? 0 : 1,
      duration: Duration(seconds: 1),
      curve: Curves.easeOut,
    );
  },
);
```

---

### **11. Image Cache**
You can control how images are cached using the `cacheWidth`, `cacheHeight`, and `filterQuality` properties.

#### Example:
```dart
Image.network(
  'https://example.com/flutter_logo.png',
  width: 100,
  height: 100,
  cacheWidth: 100, // Caches the image at 100px width
  filterQuality: FilterQuality.high, // Improves image quality
);
```

---

### **Summary of `Image` Widget Properties**
| Property            | Description                              | Example                                   |
|---------------------|------------------------------------------|-------------------------------------------|
| `image`             | The image provider (e.g., `AssetImage`)  | `Image.asset('assets/image.png')`         |
| `width`             | Width of the image                       | `width: 100`                              |
| `height`            | Height of the image                      | `height: 100`                             |
| `fit`               | How the image fits the container         | `fit: BoxFit.cover`                       |
| `alignment`         | Alignment of the image                   | `alignment: Alignment.center`             |
| `repeat`            | How the image repeats                    | `repeat: ImageRepeat.repeat`              |
| `color`             | Color filter for the image               | `color: Colors.blue`                      |
| `colorBlendMode`    | Blend mode for the color filter          | `colorBlendMode: BlendMode.colorBurn`     |
| `loadingBuilder`    | Placeholder while loading                | `loadingBuilder: (context, child, ...)`   |
| `errorBuilder`      | Widget to display on error               | `errorBuilder: (context, error, ...)`     |
| `frameBuilder`      | Customizes image loading animation       | `frameBuilder: (context, child, ...)`     |
| `cacheWidth`        | Caches image at a specific width         | `cacheWidth: 100`                         |
| `filterQuality`     | Quality of the image rendering           | `filterQuality: FilterQuality.high`       |

---

### **Example: Full Usage**
Here’s an example combining multiple properties:
```dart
Image.network(
  'https://example.com/flutter_logo.png',
  width: 200,
  height: 200,
  fit: BoxFit.cover,
  alignment: Alignment.center,
  color: Colors.blue.withOpacity(0.5),
  colorBlendMode: BlendMode.colorBurn,
  loadingBuilder: (context, child, loadingProgress) {
    if (loadingProgress == null) return child;
    return CircularProgressIndicator();
  },
  errorBuilder: (context, error, stackTrace) {
    return Text('Failed to load image');
  },
);
```

---

## TextButton Widget 

Here’s a summary of the [Flutter `TextButton` class documentation](https://api.flutter.dev/flutter/material/TextButton-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `TextButton` Widget**
The `TextButton` widget is a Material Design button that displays text and responds to user interaction. It is typically used for less prominent actions in an app.

---

### **1. Basic Usage**
The simplest way to use a `TextButton` is to provide a `child` (usually a `Text` widget) and an `onPressed` callback.

#### Example:
```dart
TextButton(
  onPressed: () {
    print('Button pressed!');
  },
  child: Text('Click Me'),
);
```

---

### **2. Styling the Button**
You can customize the appearance of the button using the `style` parameter, which accepts a `ButtonStyle` object.

#### Example:
```dart
TextButton(
  onPressed: () {
    print('Button pressed!');
  },
  style: TextButton.styleFrom(
    primary: Colors.white, // Text color
    backgroundColor: Colors.blue, // Background color
    padding: EdgeInsets.all(16), // Padding
  ),
  child: Text('Click Me'),
);
```

---

### **3. Disabling the Button**
You can disable the button by setting `onPressed` to `null`.

#### Example:
```dart
TextButton(
  onPressed: null, // Disables the button
  child: Text('Disabled Button'),
);
```

---

### **4. Icon and Text**
You can include an icon alongside the text using the `Row` widget.

#### Example:
```dart
TextButton(
  onPressed: () {
    print('Button pressed!');
  },
  child: Row(
    mainAxisSize: MainAxisSize.min,
    children: [
      Icon(Icons.thumb_up),
      SizedBox(width: 8), // Spacing between icon and text
      Text('Like'),
    ],
  ),
);
```

---

### **5. Customizing Shape**
You can customize the shape of the button using the `shape` property in `ButtonStyle`.

#### Example:
```dart
TextButton(
  onPressed: () {
    print('Button pressed!');
  },
  style: TextButton.styleFrom(
    shape: RoundedRectangleBorder(
      borderRadius: BorderRadius.circular(20), // Rounded corners
    ),
  ),
  child: Text('Rounded Button'),
);
```

---

### **6. Adding a Border**
You can add a border to the button using the `side` property in `ButtonStyle`.

#### Example:
```dart
TextButton(
  onPressed: () {
    print('Button pressed!');
  },
  style: TextButton.styleFrom(
    side: BorderSide(color: Colors.blue, width: 2), // Border
  ),
  child: Text('Bordered Button'),
);
```

---

### **7. Elevation and Shadow**
You can add elevation and shadow to the button using the `elevation` property.

#### Example:
```dart
TextButton(
  onPressed: () {
    print('Button pressed!');
  },
  style: TextButton.styleFrom(
    elevation: 5, // Adds shadow
  ),
  child: Text('Elevated Button'),
);
```

---

### **8. Customizing Text Style**
You can customize the text style using the `textStyle` property in `ButtonStyle`.

#### Example:
```dart
TextButton(
  onPressed: () {
    print('Button pressed!');
  },
  style: TextButton.styleFrom(
    textStyle: TextStyle(
      fontSize: 18,
      fontWeight: FontWeight.bold,
    ),
  ),
  child: Text('Styled Text'),
);
```

---

### **9. Using `ButtonStyle` Theme**
You can define a global `ButtonStyle` for all `TextButton` widgets using the app's theme.

#### Example:
```dart
MaterialApp(
  theme: ThemeData(
    textButtonTheme: TextButtonThemeData(
      style: TextButton.styleFrom(
        primary: Colors.white,
        backgroundColor: Colors.blue,
      ),
    ),
  ),
  home: Scaffold(
    body: Center(
      child: TextButton(
        onPressed: () {
          print('Button pressed!');
        },
        child: Text('Themed Button'),
      ),
    ),
  ),
);
```

---

### **10. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
TextButton(
  onPressed: () {
    print('Button pressed!');
  },
  style: TextButton.styleFrom(
    primary: Colors.white,
    backgroundColor: Colors.blue,
    padding: EdgeInsets.all(16),
    shape: RoundedRectangleBorder(
      borderRadius: BorderRadius.circular(20),
    ),
    side: BorderSide(color: Colors.blue, width: 2),
    elevation: 5,
    textStyle: TextStyle(
      fontSize: 18,
      fontWeight: FontWeight.bold,
    ),
  ),
  child: Text('Custom Button'),
);
```

---

### **Summary of `TextButton` Properties**
| Property          | Description                              | Example                                   |
|-------------------|------------------------------------------|-------------------------------------------|
| `onPressed`       | Callback when the button is pressed      | `onPressed: () { print('Pressed'); }`    |
| `child`           | The widget inside the button             | `child: Text('Click Me')`                |
| `style`           | Customizes the button's appearance       | `style: TextButton.styleFrom(...)`        |
| `onLongPress`     | Callback for long press                  | `onLongPress: () { print('Long Press'); }`|
| `autofocus`       | Whether the button is focused initially  | `autofocus: true`                        |
| `clipBehavior`    | Clipping behavior                        | `clipBehavior: Clip.antiAlias`           |

---

### **Example: Full Usage**
Here’s a complete example of a `TextButton` with various customizations:
```dart
TextButton(
  onPressed: () {
    print('Button pressed!');
  },
  style: TextButton.styleFrom(
    primary: Colors.white,
    backgroundColor: Colors.blue,
    padding: EdgeInsets.all(16),
    shape: RoundedRectangleBorder(
      borderRadius: BorderRadius.circular(20),
    ),
    side: BorderSide(color: Colors.blue, width: 2),
    elevation: 5,
    textStyle: TextStyle(
      fontSize: 18,
      fontWeight: FontWeight.bold,
    ),
  ),
  child: Text('Custom Button'),
);
```

---

