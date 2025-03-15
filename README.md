# widgets

**Basic Widgets**
Container – A flexible box for layout, styling, and decoration.
Text – Displays text with styling options.
Image – Shows images from assets, network, or memory.
Icon – Displays material icons.
Scaffold – Provides a basic layout structure with an app bar, floating action button, etc.
**Layout Widgets**
Row – Arranges children horizontally.
Column – Arranges children vertically.
Stack – Overlaps widgets on top of each other.
Expanded – Forces a child to fill available space in a Row or Column.
Flexible – Similar to Expanded but with more control.
Padding – Adds space around a widget.
Align – Aligns a child within a parent.
SizedBox – Creates fixed-width or fixed-height space.
Wrap – Wraps children when they exceed available space.
**Input & Interaction Widgets**
ElevatedButton – A button with elevation.
TextButton – A button without elevation.
OutlinedButton – A button with an outlined border.
IconButton – A button with an icon.
GestureDetector – Detects touch gestures like taps, swipes, and drags.
InkWell – Provides ripple effects on tap.
TextField – Input field for text.
Checkbox – A tickable box.
Switch – A toggle switch.
Slider – A draggable value selector.
**Navigation & Structural Widgets**
AppBar – A material design app bar.
BottomNavigationBar – A bottom navigation menu.
Drawer – A slide-out navigation panel.
TabBar & TabBarView – Provides a tabbed interface.
Navigator – Manages screen transitions.
**List & Grid Widgets**
ListView – Displays a scrollable list of widgets.
GridView – Displays a scrollable grid of widgets.
ListTile – A single item in a list.
**Animation & Effect Widgets**
AnimatedContainer – Automatically animates changes in size, color, etc.
Hero – Enables shared element transitions.
Opacity – Controls widget transparency.
**Other Useful Widgets**
FutureBuilder – Handles asynchronous data loading.
StreamBuilder – Builds widgets based on a Stream.
ClipRRect – Clips a widget into a rounded rectangle.
RichText – Displays text with multiple styles.

[[# Text Widget]]


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

## Container Widget 

Here’s a summary of the [Flutter `Container` class documentation](https://api.flutter.dev/flutter/widgets/Container-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Container` Widget**
The `Container` widget is a versatile and commonly used widget in Flutter. It combines common painting, positioning, and sizing widgets into a single widget. It can be used to create boxes with background colors, borders, margins, padding, and more.

---

### **1. Basic Usage**
The simplest way to use a `Container` is to provide a `child` widget.

#### Example:
```dart
Container(
  child: Text('Hello, Flutter!'),
);
```

---

### **2. Adding Padding**
You can add padding around the child widget using the `padding` property.

#### Example:
```dart
Container(
  padding: EdgeInsets.all(16), // Padding on all sides
  child: Text('Hello, Flutter!'),
);
```

---

### **3. Adding Margins**
You can add margins around the container using the `margin` property.

#### Example:
```dart
Container(
  margin: EdgeInsets.all(16), // Margin on all sides
  child: Text('Hello, Flutter!'),
);
```

---

### **4. Setting Width and Height**
You can specify the width and height of the container using the `width` and `height` properties.

#### Example:
```dart
Container(
  width: 200,
  height: 100,
  child: Text('Hello, Flutter!'),
);
```

---

### **5. Adding a Background Color**
You can set a background color for the container using the `color` property.

#### Example:
```dart
Container(
  color: Colors.blue, // Background color
  child: Text('Hello, Flutter!'),
);
```

---

### **6. Adding a Border**
You can add a border to the container using the `decoration` property with a `BoxDecoration`.

#### Example:
```dart
Container(
  decoration: BoxDecoration(
    border: Border.all(
      color: Colors.black,
      width: 2,
    ),
  ),
  child: Text('Hello, Flutter!'),
);
```

---

### **7. Adding Rounded Corners**
You can add rounded corners to the container using the `borderRadius` property in `BoxDecoration`.

#### Example:
```dart
Container(
  decoration: BoxDecoration(
    borderRadius: BorderRadius.circular(10), // Rounded corners
    color: Colors.blue,
  ),
  child: Text('Hello, Flutter!'),
);
```

---

### **8. Adding a Gradient Background**
You can add a gradient background to the container using the `gradient` property in `BoxDecoration`.

#### Example:
```dart
Container(
  decoration: BoxDecoration(
    gradient: LinearGradient(
      colors: [Colors.blue, Colors.green],
      begin: Alignment.topLeft,
      end: Alignment.bottomRight,
    ),
  ),
  child: Text('Hello, Flutter!'),
);
```

---

### **9. Adding a Box Shadow**
You can add a shadow to the container using the `boxShadow` property in `BoxDecoration`.

#### Example:
```dart
Container(
  decoration: BoxDecoration(
    boxShadow: [
      BoxShadow(
        color: Colors.black.withOpacity(0.5),
        spreadRadius: 5,
        blurRadius: 7,
        offset: Offset(0, 3), // Shadow position
      ),
    ],
  ),
  child: Text('Hello, Flutter!'),
);
```

---

### **10. Aligning the Child**
You can align the child widget within the container using the `alignment` property.

#### Example:
```dart
Container(
  alignment: Alignment.center, // Centers the child
  child: Text('Hello, Flutter!'),
);
```

---

### **11. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Container(
  width: 200,
  height: 100,
  padding: EdgeInsets.all(16),
  margin: EdgeInsets.all(16),
  decoration: BoxDecoration(
    color: Colors.blue,
    borderRadius: BorderRadius.circular(10),
    border: Border.all(
      color: Colors.black,
      width: 2,
    ),
    boxShadow: [
      BoxShadow(
        color: Colors.black.withOpacity(0.5),
        spreadRadius: 5,
        blurRadius: 7,
        offset: Offset(0, 3),
      ),
    ],
  ),
  alignment: Alignment.center,
  child: Text('Hello, Flutter!'),
);
```

---

### **Summary of `Container` Properties**
| Property          | Description                              | Example                                   |
|-------------------|------------------------------------------|-------------------------------------------|
| `child`           | The widget inside the container          | `child: Text('Hello, Flutter!')`         |
| `padding`         | Padding around the child                 | `padding: EdgeInsets.all(16)`            |
| `margin`          | Margin around the container              | `margin: EdgeInsets.all(16)`             |
| `width`           | Width of the container                   | `width: 200`                             |
| `height`          | Height of the container                  | `height: 100`                            |
| `color`           | Background color                         | `color: Colors.blue`                     |
| `decoration`      | Customizes the container's appearance    | `decoration: BoxDecoration(...)`         |
| `alignment`       | Aligns the child within the container    | `alignment: Alignment.center`            |
| `constraints`     | Constraints on the container's size      | `constraints: BoxConstraints(...)`       |
| `transform`       | Transforms the container                 | `transform: Matrix4.rotationZ(0.1)`      |

---

### **Example: Full Usage**
Here’s a complete example of a `Container` with various customizations:
```dart
Container(
  width: 200,
  height: 100,
  padding: EdgeInsets.all(16),
  margin: EdgeInsets.all(16),
  decoration: BoxDecoration(
    color: Colors.blue,
    borderRadius: BorderRadius.circular(10),
    border: Border.all(
      color: Colors.black,
      width: 2,
    ),
    boxShadow: [
      BoxShadow(
        color: Colors.black.withOpacity(0.5),
        spreadRadius: 5,
        blurRadius: 7,
        offset: Offset(0, 3),
      ),
    ],
  ),
  alignment: Alignment.center,
  child: Text('Hello, Flutter!'),
);
```

---

## Card Widget 

Here’s a summary of the [Flutter `Card` class documentation](https://api.flutter.dev/flutter/material/Card-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Card` Widget**
The `Card` widget is a Material Design component used to display content in a rounded rectangle with a shadow. It is commonly used to group related information and provide a visual hierarchy.

---

### **1. Basic Usage**
The simplest way to use a `Card` is to provide a `child` widget.

#### Example:
```dart
Card(
  child: ListTile(
    leading: Icon(Icons.person),
    title: Text('John Doe'),
    subtitle: Text('Software Developer'),
  ),
);
```

---

### **2. Adding Padding**
You can add padding around the child widget using the `margin` and `padding` properties.

#### Example:
```dart
Card(
  margin: EdgeInsets.all(16), // Margin around the card
  child: Padding(
    padding: EdgeInsets.all(16), // Padding inside the card
    child: Text('Hello, Flutter!'),
  ),
);
```

---

### **3. Customizing Elevation**
You can customize the shadow of the card using the `elevation` property.

#### Example:
```dart
Card(
  elevation: 8, // Higher elevation for a larger shadow
  child: ListTile(
    leading: Icon(Icons.person),
    title: Text('John Doe'),
    subtitle: Text('Software Developer'),
  ),
);
```

---

### **4. Adding a Border**
You can add a border to the card using the `shape` property.

#### Example:
```dart
Card(
  shape: RoundedRectangleBorder(
    side: BorderSide(
      color: Colors.black,
      width: 2,
    ),
    borderRadius: BorderRadius.circular(10), // Rounded corners
  ),
  child: ListTile(
    leading: Icon(Icons.person),
    title: Text('John Doe'),
    subtitle: Text('Software Developer'),
  ),
);
```

---

### **5. Adding a Background Color**
You can set a background color for the card using the `color` property.

#### Example:
```dart
Card(
  color: Colors.blue, // Background color
  child: ListTile(
    leading: Icon(Icons.person),
    title: Text('John Doe'),
    subtitle: Text('Software Developer'),
  ),
);
```

---

### **6. Adding a Gradient Background**
You can add a gradient background to the card using the `decoration` property.

#### Example:
```dart
Card(
  decoration: BoxDecoration(
    gradient: LinearGradient(
      colors: [Colors.blue, Colors.green],
      begin: Alignment.topLeft,
      end: Alignment.bottomRight,
    ),
  ),
  child: ListTile(
    leading: Icon(Icons.person),
    title: Text('John Doe'),
    subtitle: Text('Software Developer'),
  ),
);
```

---

### **7. Adding a Clip Behavior**
You can control how the card's content is clipped using the `clipBehavior` property.

#### Example:
```dart
Card(
  clipBehavior: Clip.antiAlias, // Smooth edges
  child: ListTile(
    leading: Icon(Icons.person),
    title: Text('John Doe'),
    subtitle: Text('Software Developer'),
  ),
);
```

---

### **8. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Card(
  margin: EdgeInsets.all(16),
  elevation: 8,
  shape: RoundedRectangleBorder(
    side: BorderSide(
      color: Colors.black,
      width: 2,
    ),
    borderRadius: BorderRadius.circular(10),
  ),
  color: Colors.blue,
  child: Padding(
    padding: EdgeInsets.all(16),
    child: ListTile(
      leading: Icon(Icons.person),
      title: Text('John Doe'),
      subtitle: Text('Software Developer'),
    ),
  ),
);
```

---

### **Summary of `Card` Properties**
| Property          | Description                              | Example                                   |
|-------------------|------------------------------------------|-------------------------------------------|
| `child`           | The widget inside the card               | `child: ListTile(...)`                   |
| `margin`          | Margin around the card                   | `margin: EdgeInsets.all(16)`             |
| `elevation`       | Shadow depth                             | `elevation: 8`                           |
| `shape`           | Shape of the card                        | `shape: RoundedRectangleBorder(...)`     |
| `color`           | Background color                         | `color: Colors.blue`                     |
| `decoration`      | Customizes the card's appearance         | `decoration: BoxDecoration(...)`         |
| `clipBehavior`    | Clipping behavior                        | `clipBehavior: Clip.antiAlias`           |

---

### **Example: Full Usage**
Here’s a complete example of a `Card` with various customizations:
```dart
Card(
  margin: EdgeInsets.all(16),
  elevation: 8,
  shape: RoundedRectangleBorder(
    side: BorderSide(
      color: Colors.black,
      width: 2,
    ),
    borderRadius: BorderRadius.circular(10),
  ),
  color: Colors.blue,
  child: Padding(
    padding: EdgeInsets.all(16),
    child: ListTile(
      leading: Icon(Icons.person),
      title: Text('John Doe'),
      subtitle: Text('Software Developer'),
    ),
  ),
);
```

---

## Column Widget 

Here’s a summary of the [Flutter `Column` class documentation](https://api.flutter.dev/flutter/widgets/Column-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Column` Widget**
The `Column` widget is a layout widget that displays its children in a vertical array. It is commonly used to arrange widgets vertically on the screen.

---

### **1. Basic Usage**
The simplest way to use a `Column` is to provide a list of `children`.

#### Example:
```dart
Column(
  children: [
    Text('First Item'),
    Text('Second Item'),
    Text('Third Item'),
  ],
);
```

---

### **2. Main Axis Alignment**
You can align children along the main axis (vertical axis) using the `mainAxisAlignment` property.

#### Example:
```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center, // Centers children vertically
  children: [
    Text('First Item'),
    Text('Second Item'),
    Text('Third Item'),
  ],
);
```

---

### **3. Cross Axis Alignment**
You can align children along the cross axis (horizontal axis) using the `crossAxisAlignment` property.

#### Example:
```dart
Column(
  crossAxisAlignment: CrossAxisAlignment.start, // Aligns children to the start horizontally
  children: [
    Text('First Item'),
    Text('Second Item'),
    Text('Third Item'),
  ],
);
```

---

### **4. Main Axis Size**
You can control the size of the column along the main axis using the `mainAxisSize` property.

#### Example:
```dart
Column(
  mainAxisSize: MainAxisSize.min, // Column takes up minimum vertical space
  children: [
    Text('First Item'),
    Text('Second Item'),
    Text('Third Item'),
  ],
);
```

---

### **5. Adding Spacing**
You can add spacing between children using the `SizedBox` widget.

#### Example:
```dart
Column(
  children: [
    Text('First Item'),
    SizedBox(height: 10), // Adds 10 pixels of space
    Text('Second Item'),
    SizedBox(height: 10), // Adds 10 pixels of space
    Text('Third Item'),
  ],
);
```

---

### **6. Adding a Scrollable Column**
If the content of the column exceeds the available space, you can make it scrollable using the `SingleChildScrollView` widget.

#### Example:
```dart
SingleChildScrollView(
  child: Column(
    children: List.generate(20, (index) => Text('Item $index')),
  ),
);
```

---

### **7. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisSize: MainAxisSize.min,
  children: [
    Text('First Item'),
    SizedBox(height: 10),
    Text('Second Item'),
    SizedBox(height: 10),
    Text('Third Item'),
  ],
);
```

---

### **Summary of `Column` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `children`            | The widgets inside the column            | `children: [Text('Item 1'), Text('Item 2')]` |
| `mainAxisAlignment`   | Aligns children along the main axis      | `mainAxisAlignment: MainAxisAlignment.center` |
| `crossAxisAlignment`  | Aligns children along the cross axis     | `crossAxisAlignment: CrossAxisAlignment.start` |
| `mainAxisSize`        | Controls the size along the main axis    | `mainAxisSize: MainAxisSize.min`          |
| `textDirection`       | Text direction for children              | `textDirection: TextDirection.rtl`        |
| `verticalDirection`   | Vertical direction for children          | `verticalDirection: VerticalDirection.up` |

---

### **Example: Full Usage**
Here’s a complete example of a `Column` with various customizations:
```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisSize: MainAxisSize.min,
  children: [
    Text('First Item'),
    SizedBox(height: 10),
    Text('Second Item'),
    SizedBox(height: 10),
    Text('Third Item'),
  ],
);
```

---

## Row Widget 

Here’s a summary of the [Flutter `Row` class documentation](https://api.flutter.dev/flutter/widgets/Row-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Row` Widget**
The `Row` widget is a layout widget that displays its children in a horizontal array. It is commonly used to arrange widgets horizontally on the screen.

---

### **1. Basic Usage**
The simplest way to use a `Row` is to provide a list of `children`.

#### Example:
```dart
Row(
  children: [
    Text('First Item'),
    Text('Second Item'),
    Text('Third Item'),
  ],
);
```

---

### **2. Main Axis Alignment**
You can align children along the main axis (horizontal axis) using the `mainAxisAlignment` property.

#### Example:
```dart
Row(
  mainAxisAlignment: MainAxisAlignment.center, // Centers children horizontally
  children: [
    Text('First Item'),
    Text('Second Item'),
    Text('Third Item'),
  ],
);
```

---

### **3. Cross Axis Alignment**
You can align children along the cross axis (vertical axis) using the `crossAxisAlignment` property.

#### Example:
```dart
Row(
  crossAxisAlignment: CrossAxisAlignment.start, // Aligns children to the start vertically
  children: [
    Text('First Item'),
    Text('Second Item'),
    Text('Third Item'),
  ],
);
```

---

### **4. Main Axis Size**
You can control the size of the row along the main axis using the `mainAxisSize` property.

#### Example:
```dart
Row(
  mainAxisSize: MainAxisSize.min, // Row takes up minimum horizontal space
  children: [
    Text('First Item'),
    Text('Second Item'),
    Text('Third Item'),
  ],
);
```

---

### **5. Adding Spacing**
You can add spacing between children using the `SizedBox` widget.

#### Example:
```dart
Row(
  children: [
    Text('First Item'),
    SizedBox(width: 10), // Adds 10 pixels of space
    Text('Second Item'),
    SizedBox(width: 10), // Adds 10 pixels of space
    Text('Third Item'),
  ],
);
```

---

### **6. Adding a Scrollable Row**
If the content of the row exceeds the available space, you can make it scrollable using the `SingleChildScrollView` widget.

#### Example:
```dart
SingleChildScrollView(
  scrollDirection: Axis.horizontal,
  child: Row(
    children: List.generate(20, (index) => Text('Item $index ')),
  ),
);
```

---

### **7. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Row(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisSize: MainAxisSize.min,
  children: [
    Text('First Item'),
    SizedBox(width: 10),
    Text('Second Item'),
    SizedBox(width: 10),
    Text('Third Item'),
  ],
);
```

---

### **Summary of `Row` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `children`            | The widgets inside the row               | `children: [Text('Item 1'), Text('Item 2')]` |
| `mainAxisAlignment`   | Aligns children along the main axis      | `mainAxisAlignment: MainAxisAlignment.center` |
| `crossAxisAlignment`  | Aligns children along the cross axis     | `crossAxisAlignment: CrossAxisAlignment.start` |
| `mainAxisSize`        | Controls the size along the main axis    | `mainAxisSize: MainAxisSize.min`          |
| `textDirection`       | Text direction for children              | `textDirection: TextDirection.rtl`        |
| `verticalDirection`   | Vertical direction for children          | `verticalDirection: VerticalDirection.up` |

---

### **Example: Full Usage**
Here’s a complete example of a `Row` with various customizations:
```dart
Row(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.start,
  mainAxisSize: MainAxisSize.min,
  children: [
    Text('First Item'),
    SizedBox(width: 10),
    Text('Second Item'),
    SizedBox(width: 10),
    Text('Third Item'),
  ],
);
```

---

## List View Widget 

Here’s a summary of the [Flutter `ListView` class documentation](https://api.flutter.dev/flutter/widgets/ListView-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `ListView` Widget**
The `ListView` widget is a scrollable list of widgets arranged linearly. It is commonly used to display a list of items that can be scrolled vertically or horizontally.

---

### **1. Basic Usage**
The simplest way to use a `ListView` is to provide a list of `children`.

#### Example:
```dart
ListView(
  children: [
    ListTile(title: Text('Item 1')),
    ListTile(title: Text('Item 2')),
    ListTile(title: Text('Item 3')),
  ],
);
```

---

### **2. ListView.builder**
Use `ListView.builder` to create a list with a large or infinite number of items. It builds items on demand.

#### Example:
```dart
ListView.builder(
  itemCount: 100, // Number of items
  itemBuilder: (context, index) {
    return ListTile(title: Text('Item $index'));
  },
);
```

---

### **3. ListView.separated**
Use `ListView.separated` to create a list with separators between items.

#### Example:
```dart
ListView.separated(
  itemCount: 100, // Number of items
  separatorBuilder: (context, index) => Divider(), // Separator between items
  itemBuilder: (context, index) {
    return ListTile(title: Text('Item $index'));
  },
);
```

---

### **4. Scroll Direction**
You can change the scroll direction to horizontal using the `scrollDirection` property.

#### Example:
```dart
ListView(
  scrollDirection: Axis.horizontal, // Horizontal scrolling
  children: [
    Container(width: 100, color: Colors.red),
    Container(width: 100, color: Colors.green),
    Container(width: 100, color: Colors.blue),
  ],
);
```

---

### **5. Adding Padding**
You can add padding around the list using the `padding` property.

#### Example:
```dart
ListView(
  padding: EdgeInsets.all(16), // Padding around the list
  children: [
    ListTile(title: Text('Item 1')),
    ListTile(title: Text('Item 2')),
    ListTile(title: Text('Item 3')),
  ],
);
```

---

### **6. Adding a Header or Footer**
You can add a header or footer to the list using the `ListView`'s `children` property.

#### Example:
```dart
ListView(
  children: [
    Text('Header', style: TextStyle(fontSize: 24)),
    ListTile(title: Text('Item 1')),
    ListTile(title: Text('Item 2')),
    ListTile(title: Text('Item 3')),
    Text('Footer', style: TextStyle(fontSize: 24)),
  ],
);
```

---

### **7. Controlling Scroll Physics**
You can control the scroll behavior using the `physics` property.

#### Example:
```dart
ListView(
  physics: BouncingScrollPhysics(), // Bounce effect on iOS
  children: [
    ListTile(title: Text('Item 1')),
    ListTile(title: Text('Item 2')),
    ListTile(title: Text('Item 3')),
  ],
);
```

---

### **8. Infinite Scrolling**
You can implement infinite scrolling by dynamically adding items to the list.

#### Example:
```dart
class InfiniteListView extends StatefulWidget {
  @override
  _InfiniteListViewState createState() => _InfiniteListViewState();
}

class _InfiniteListViewState extends State<InfiniteListView> {
  List<int> items = List.generate(20, (index) => index);

  void _loadMore() {
    setState(() {
      items.addAll(List.generate(10, (index) => items.length + index));
    });
  }

  @override
  Widget build(BuildContext context) {
    return ListView.builder(
      itemCount: items.length + 1,
      itemBuilder: (context, index) {
        if (index == items.length) {
          _loadMore();
          return Center(child: CircularProgressIndicator());
        }
        return ListTile(title: Text('Item ${items[index]}'));
      },
    );
  }
}
```

---

### **9. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
ListView(
  padding: EdgeInsets.all(16),
  physics: BouncingScrollPhysics(),
  children: [
    Text('Header', style: TextStyle(fontSize: 24)),
    ListTile(title: Text('Item 1')),
    ListTile(title: Text('Item 2')),
    ListTile(title: Text('Item 3')),
    Text('Footer', style: TextStyle(fontSize: 24)),
  ],
);
```

---

### **Summary of `ListView` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `children`            | The widgets inside the list              | `children: [ListTile(...)]`              |
| `itemBuilder`         | Builds items on demand                   | `itemBuilder: (context, index) {...}`    |
| `itemCount`           | Number of items in the list              | `itemCount: 100`                         |
| `separatorBuilder`    | Builds separators between items          | `separatorBuilder: (context, index) {...}` |
| `scrollDirection`     | Scroll direction (vertical/horizontal)   | `scrollDirection: Axis.horizontal`       |
| `padding`             | Padding around the list                  | `padding: EdgeInsets.all(16)`            |
| `physics`             | Scroll behavior                          | `physics: BouncingScrollPhysics()`       |

---

### **Example: Full Usage**
Here’s a complete example of a `ListView` with various customizations:
```dart
ListView(
  padding: EdgeInsets.all(16),
  physics: BouncingScrollPhysics(),
  children: [
    Text('Header', style: TextStyle(fontSize: 24)),
    ListTile(title: Text('Item 1')),
    ListTile(title: Text('Item 2')),
    ListTile(title: Text('Item 3')),
    Text('Footer', style: TextStyle(fontSize: 24)),
  ],
);
```

---

## AppBar Widget 

Here’s a summary of the [Flutter `AppBar` class documentation](https://api.flutter.dev/flutter/material/AppBar-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `AppBar` Widget**
The `AppBar` widget is a Material Design app bar that typically appears at the top of the screen. It is commonly used to display the title, actions, and navigation controls.

---

### **1. Basic Usage**
The simplest way to use an `AppBar` is to provide a `title`.

#### Example:
```dart
AppBar(
  title: Text('My App'),
);
```

---

### **2. Adding Actions**
You can add action buttons to the app bar using the `actions` property.

#### Example:
```dart
AppBar(
  title: Text('My App'),
  actions: [
    IconButton(
      icon: Icon(Icons.search),
      onPressed: () {
        print('Search button pressed');
      },
    ),
    IconButton(
      icon: Icon(Icons.more_vert),
      onPressed: () {
        print('More button pressed');
      },
    ),
  ],
);
```

---

### **3. Adding a Leading Widget**
You can add a leading widget (e.g., a back button) using the `leading` property.

#### Example:
```dart
AppBar(
  title: Text('My App'),
  leading: IconButton(
    icon: Icon(Icons.menu),
    onPressed: () {
      print('Menu button pressed');
    },
  ),
);
```

---

### **4. Customizing the Title**
You can customize the title using the `title` property.

#### Example:
```dart
AppBar(
  title: Row(
    children: [
      Icon(Icons.home),
      SizedBox(width: 8),
      Text('My App'),
    ],
  ),
);
```

---

### **5. Adding a Flexible Space**
You can add a flexible space (e.g., a background image) using the `flexibleSpace` property.

#### Example:
```dart
AppBar(
  title: Text('My App'),
  flexibleSpace: Image.network(
    'https://example.com/background.jpg',
    fit: BoxFit.cover,
  ),
);
```

---

### **6. Adding a Bottom Widget**
You can add a bottom widget (e.g., a tab bar) using the `bottom` property.

#### Example:
```dart
AppBar(
  title: Text('My App'),
  bottom: TabBar(
    tabs: [
      Tab(icon: Icon(Icons.home),
      Tab(icon: Icon(Icons.settings)),
    ],
  ),
);
```

---

### **7. Customizing the App Bar Height**
You can customize the height of the app bar using the `toolbarHeight` property.

#### Example:
```dart
AppBar(
  title: Text('My App'),
  toolbarHeight: 100, // Sets the height of the app bar
);
```

---

### **8. Customizing the Background Color**
You can customize the background color of the app bar using the `backgroundColor` property.

#### Example:
```dart
AppBar(
  title: Text('My App'),
  backgroundColor: Colors.blue, // Sets the background color
);
```

---

### **9. Customizing the Elevation**
You can customize the elevation (shadow) of the app bar using the `elevation` property.

#### Example:
```dart
AppBar(
  title: Text('My App'),
  elevation: 10, // Sets the elevation
);
```

---

### **10. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
AppBar(
  title: Text('My App'),
  leading: IconButton(
    icon: Icon(Icons.menu),
    onPressed: () {
      print('Menu button pressed');
    },
  ),
  actions: [
    IconButton(
      icon: Icon(Icons.search),
      onPressed: () {
        print('Search button pressed');
      },
    ),
    IconButton(
      icon: Icon(Icons.more_vert),
      onPressed: () {
        print('More button pressed');
      },
    ),
  ],
  bottom: TabBar(
    tabs: [
      Tab(icon: Icon(Icons.home)),
      Tab(icon: Icon(Icons.settings)),
    ],
  ),
  backgroundColor: Colors.blue,
  elevation: 10,
  toolbarHeight: 100,
);
```

---

### **Summary of `AppBar` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `title`               | The title of the app bar                 | `title: Text('My App')`                  |
| `actions`             | Action buttons                           | `actions: [IconButton(...)]`             |
| `leading`             | Leading widget (e.g., back button)       | `leading: IconButton(...)`               |
| `flexibleSpace`       | Flexible space (e.g., background image)  | `flexibleSpace: Image.network(...)`      |
| `bottom`              | Bottom widget (e.g., tab bar)            | `bottom: TabBar(...)`                    |
| `toolbarHeight`       | Height of the app bar                    | `toolbarHeight: 100`                     |
| `backgroundColor`     | Background color                         | `backgroundColor: Colors.blue`           |
| `elevation`           | Elevation (shadow)                       | `elevation: 10`                          |

---

### **Example: Full Usage**
Here’s a complete example of an `AppBar` with various customizations:
```dart
AppBar(
  title: Text('My App'),
  leading: IconButton(
    icon: Icon(Icons.menu),
    onPressed: () {
      print('Menu button pressed');
    },
  ),
  actions: [
    IconButton(
      icon: Icon(Icons.search),
      onPressed: () {
        print('Search button pressed');
      },
    ),
    IconButton(
      icon: Icon(Icons.more_vert),
      onPressed: () {
        print('More button pressed');
      },
    ),
  ],
  bottom: TabBar(
    tabs: [
      Tab(icon: Icon(Icons.home)),
      Tab(icon: Icon(Icons.settings)),
    ],
  ),
  backgroundColor: Colors.blue,
  elevation: 10,
  toolbarHeight: 100,
);
```

---

## Scafold Widget 

Here’s a summary of the [Flutter `Scaffold` class documentation](https://api.flutter.dev/flutter/material/Scaffold-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Scaffold` Widget**
The `Scaffold` widget is a fundamental building block in Material Design apps. It provides a framework for implementing the basic Material Design layout structure, including app bars, drawers, floating action buttons, and more.

---

### **1. Basic Usage**
The simplest way to use a `Scaffold` is to provide a `body`.

#### Example:
```dart
Scaffold(
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
);
```

---

### **2. Adding an App Bar**
You can add an app bar using the `appBar` property.

#### Example:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('My App'),
  ),
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
);
```

---

### **3. Adding a Floating Action Button**
You can add a floating action button (FAB) using the `floatingActionButton` property.

#### Example:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('My App'),
  ),
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
  floatingActionButton: FloatingActionButton(
    onPressed: () {
      print('FAB pressed');
    },
    child: Icon(Icons.add),
  ),
);
```

---

### **4. Adding a Drawer**
You can add a drawer (side menu) using the `drawer` property.

#### Example:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('My App'),
  ),
  drawer: Drawer(
    child: ListView(
      children: [
        DrawerHeader(
          child: Text('Drawer Header'),
          decoration: BoxDecoration(
            color: Colors.blue,
          ),
        ),
        ListTile(
          title: Text('Item 1'),
          onTap: () {
            print('Item 1 pressed');
          },
        ),
        ListTile(
          title: Text('Item 2'),
          onTap: () {
            print('Item 2 pressed');
          },
        ),
      ],
    ),
  ),
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
);
```

---

### **5. Adding a Bottom Navigation Bar**
You can add a bottom navigation bar using the `bottomNavigationBar` property.

#### Example:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('My App'),
  ),
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
  bottomNavigationBar: BottomNavigationBar(
    items: [
      BottomNavigationBarItem(
        icon: Icon(Icons.home),
        label: 'Home',
      ),
      BottomNavigationBarItem(
        icon: Icon(Icons.settings),
        label: 'Settings',
      ),
    ],
  ),
);
```

---

### **6. Adding a SnackBar**
You can display a snack bar using the `ScaffoldMessenger`.

#### Example:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('My App'),
  ),
  body: Center(
    child: ElevatedButton(
      onPressed: () {
        ScaffoldMessenger.of(context).showSnackBar(
          SnackBar(content: Text('This is a SnackBar')),
        );
      },
      child: Text('Show SnackBar'),
    ),
  ),
);
```

---

### **7. Adding a Persistent Footer Button**
You can add a persistent footer button using the `persistentFooterButtons` property.

#### Example:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('My App'),
  ),
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
  persistentFooterButtons: [
    IconButton(
      icon: Icon(Icons.thumb_up),
      onPressed: () {
        print('Thumbs up pressed');
      },
    ),
    IconButton(
      icon: Icon(Icons.thumb_down),
      onPressed: () {
        print('Thumbs down pressed');
      },
    ),
  ],
);
```

---

### **8. Customizing the Background Color**
You can customize the background color of the scaffold using the `backgroundColor` property.

#### Example:
```dart
Scaffold(
  backgroundColor: Colors.blue, // Sets the background color
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
);
```

---

### **9. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('My App'),
  ),
  drawer: Drawer(
    child: ListView(
      children: [
        DrawerHeader(
          child: Text('Drawer Header'),
          decoration: BoxDecoration(
            color: Colors.blue,
          ),
        ),
        ListTile(
          title: Text('Item 1'),
          onTap: () {
            print('Item 1 pressed');
          },
        ),
        ListTile(
          title: Text('Item 2'),
          onTap: () {
            print('Item 2 pressed');
          },
        ),
      ],
    ),
  ),
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
  floatingActionButton: FloatingActionButton(
    onPressed: () {
      print('FAB pressed');
    },
    child: Icon(Icons.add),
  ),
  bottomNavigationBar: BottomNavigationBar(
    items: [
      BottomNavigationBarItem(
        icon: Icon(Icons.home),
        label: 'Home',
      ),
      BottomNavigationBarItem(
        icon: Icon(Icons.settings),
        label: 'Settings',
      ),
    ],
  ),
  persistentFooterButtons: [
    IconButton(
      icon: Icon(Icons.thumb_up),
      onPressed: () {
        print('Thumbs up pressed');
      },
    ),
    IconButton(
      icon: Icon(Icons.thumb_down),
      onPressed: () {
        print('Thumbs down pressed');
      },
    ),
  ],
  backgroundColor: Colors.blue,
);
```

---

### **Summary of `Scaffold` Properties**
| Property                  | Description                              | Example                                   |
|---------------------------|------------------------------------------|-------------------------------------------|
| `appBar`                  | App bar at the top                       | `appBar: AppBar(...)`                    |
| `body`                    | Main content of the scaffold             | `body: Center(...)`                      |
| `floatingActionButton`    | Floating action button                   | `floatingActionButton: FloatingActionButton(...)` |
| `drawer`                  | Side menu                                | `drawer: Drawer(...)`                    |
| `bottomNavigationBar`     | Bottom navigation bar                    | `bottomNavigationBar: BottomNavigationBar(...)` |
| `persistentFooterButtons` | Persistent footer buttons                | `persistentFooterButtons: [IconButton(...)]` |
| `backgroundColor`         | Background color                         | `backgroundColor: Colors.blue`           |

---

### **Example: Full Usage**
Here’s a complete example of a `Scaffold` with various customizations:
```dart
Scaffold(
  appBar: AppBar(
    title: Text('My App'),
  ),
  drawer: Drawer(
    child: ListView(
      children: [
        DrawerHeader(
          child: Text('Drawer Header'),
          decoration: BoxDecoration(
            color: Colors.blue,
          ),
        ),
        ListTile(
          title: Text('Item 1'),
          onTap: () {
            print('Item 1 pressed');
          },
        ),
        ListTile(
          title: Text('Item 2'),
          onTap: () {
            print('Item 2 pressed');
          },
        ),
      ],
    ),
  ),
  body: Center(
    child: Text('Hello, Flutter!'),
  ),
  floatingActionButton: FloatingActionButton(
    onPressed: () {
      print('FAB pressed');
    },
    child: Icon(Icons.add),
  ),
  bottomNavigationBar: BottomNavigationBar(
    items: [
      BottomNavigationBarItem(
        icon: Icon(Icons.home),
        label: 'Home',
      ),
      BottomNavigationBarItem(
        icon: Icon(Icons.settings),
        label: 'Settings',
      ),
    ],
  ),
  persistentFooterButtons: [
    IconButton(
      icon: Icon(Icons.thumb_up),
      onPressed: () {
        print('Thumbs up pressed');
      },
    ),
    IconButton(
      icon: Icon(Icons.thumb_down),
      onPressed: () {
        print('Thumbs down pressed');
      },
    ),
  ],
  backgroundColor: Colors.blue,
);
```

---

## Checkbox Widget 

Here’s a summary of the [Flutter `Checkbox` class documentation](https://api.flutter.dev/flutter/material/Checkbox-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Checkbox` Widget**
The `Checkbox` widget is a Material Design checkbox that allows users to select or deselect an option. It is commonly used in forms, settings, and other interactive UIs.

---

### **1. Basic Usage**
The simplest way to use a `Checkbox` is to provide a `value` and an `onChanged` callback.

#### Example:
```dart
bool isChecked = false;

Checkbox(
  value: isChecked,
  onChanged: (bool? value) {
    setState(() {
      isChecked = value ?? false;
    });
  },
);
```

---

### **2. Handling State**
The `Checkbox` requires state management to update its value. Typically, this is done using a `StatefulWidget`.

#### Example:
```dart
class CheckboxExample extends StatefulWidget {
  @override
  _CheckboxExampleState createState() => _CheckboxExampleState();
}

class _CheckboxExampleState extends State<CheckboxExample> {
  bool isChecked = false;

  @override
  Widget build(BuildContext context) {
    return Checkbox(
      value: isChecked,
      onChanged: (bool? value) {
        setState(() {
          isChecked = value ?? false;
        });
      },
    );
  }
}
```

---

### **3. Customizing the Checkbox**
You can customize the appearance of the checkbox using the `activeColor`, `checkColor`, and `fillColor` properties.

#### Example:
```dart
Checkbox(
  value: isChecked,
  onChanged: (bool? value) {
    setState(() {
      isChecked = value ?? false;
    });
  },
  activeColor: Colors.green, // Color when checked
  checkColor: Colors.white,  // Color of the checkmark
  fillColor: MaterialStateProperty.resolveWith<Color>((states) {
    if (states.contains(MaterialState.selected)) {
      return Colors.blue; // Color when checked
    }
    return Colors.grey; // Color when unchecked
  }),
);
```

---

### **4. Disabling the Checkbox**
You can disable the checkbox by setting `onChanged` to `null`.

#### Example:
```dart
Checkbox(
  value: isChecked,
  onChanged: null, // Disables the checkbox
);
```

---

### **5. Using with a ListTile**
You can combine a `Checkbox` with a `ListTile` to create a more interactive UI.

#### Example:
```dart
ListTile(
  title: Text('Enable Feature'),
  leading: Checkbox(
    value: isChecked,
    onChanged: (bool? value) {
      setState(() {
        isChecked = value ?? false;
      });
    },
  ),
);
```

---

### **6. Using with a Form**
You can use a `Checkbox` within a `Form` to manage its state along with other form fields.

#### Example:
```dart
class FormExample extends StatefulWidget {
  @override
  _FormExampleState createState() => _FormExampleState();
}

class _FormExampleState extends State<FormExample> {
  final _formKey = GlobalKey<FormState>();
  bool isChecked = false;

  @override
  Widget build(BuildContext context) {
    return Form(
      key: _formKey,
      child: Column(
        children: [
          CheckboxListTile(
            title: Text('Agree to Terms'),
            value: isChecked,
            onChanged: (bool? value) {
              setState(() {
                isChecked = value ?? false;
              });
            },
          ),
          ElevatedButton(
            onPressed: () {
              if (_formKey.currentState!.validate()) {
                print('Form submitted');
              }
            },
            child: Text('Submit'),
          ),
        ],
      ),
    );
  }
}
```

---

### **7. Using `CheckboxListTile`**
The `CheckboxListTile` widget combines a `Checkbox` with a `ListTile` for a more integrated look.

#### Example:
```dart
CheckboxListTile(
  title: Text('Enable Feature'),
  value: isChecked,
  onChanged: (bool? value) {
    setState(() {
      isChecked = value ?? false;
    });
  },
  secondary: Icon(Icons.settings), // Optional icon
);
```

---

### **8. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Checkbox(
  value: isChecked,
  onChanged: (bool? value) {
    setState(() {
      isChecked = value ?? false;
    });
  },
  activeColor: Colors.green,
  checkColor: Colors.white,
  fillColor: MaterialStateProperty.resolveWith<Color>((states) {
    if (states.contains(MaterialState.selected)) {
      return Colors.blue;
    }
    return Colors.grey;
  }),
);
```

---

### **Summary of `Checkbox` Properties**
| Property          | Description                              | Example                                   |
|-------------------|------------------------------------------|-------------------------------------------|
| `value`           | Whether the checkbox is checked          | `value: isChecked`                        |
| `onChanged`       | Callback when the checkbox is toggled    | `onChanged: (bool? value) {...}`          |
| `activeColor`     | Color when the checkbox is checked       | `activeColor: Colors.green`               |
| `checkColor`      | Color of the checkmark                   | `checkColor: Colors.white`                |
| `fillColor`       | Color of the checkbox fill               | `fillColor: MaterialStateProperty(...)`   |
| `tristate`        | Whether the checkbox can have a null value | `tristate: true`                        |

---

### **Example: Full Usage**
Here’s a complete example of a `Checkbox` with various customizations:
```dart
class CheckboxExample extends StatefulWidget {
  @override
  _CheckboxExampleState createState() => _CheckboxExampleState();
}

class _CheckboxExampleState extends State<CheckboxExample> {
  bool isChecked = false;

  @override
  Widget build(BuildContext context) {
    return Checkbox(
      value: isChecked,
      onChanged: (bool? value) {
        setState(() {
          isChecked = value ?? false;
        });
      },
      activeColor: Colors.green,
      checkColor: Colors.white,
      fillColor: MaterialStateProperty.resolveWith<Color>((states) {
        if (states.contains(MaterialState.selected)) {
          return Colors.blue;
        }
        return Colors.grey;
      }),
    );
  }
}
```

---

## Radio Widget 

Here’s a summary of the [Flutter `Radio` class documentation](https://api.flutter.dev/flutter/material/Radio-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Radio` Widget**
The `Radio` widget is a Material Design radio button that allows users to select one option from a set of mutually exclusive options. It is commonly used in forms, settings, and other interactive UIs.

---

### **1. Basic Usage**
The simplest way to use a `Radio` is to provide a `value`, `groupValue`, and an `onChanged` callback.

#### Example:
```dart
enum Options { option1, option2 }

Options selectedOption = Options.option1;

Radio<Options>(
  value: Options.option1,
  groupValue: selectedOption,
  onChanged: (Options? value) {
    setState(() {
      selectedOption = value ?? Options.option1;
    });
  },
);
```

---

### **2. Handling State**
The `Radio` requires state management to update its value. Typically, this is done using a `StatefulWidget`.

#### Example:
```dart
class RadioExample extends StatefulWidget {
  @override
  _RadioExampleState createState() => _RadioExampleState();
}

class _RadioExampleState extends State<RadioExample> {
  Options selectedOption = Options.option1;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Radio<Options>(
          value: Options.option1,
          groupValue: selectedOption,
          onChanged: (Options? value) {
            setState(() {
              selectedOption = value ?? Options.option1;
            });
          },
        ),
        Radio<Options>(
          value: Options.option2,
          groupValue: selectedOption,
          onChanged: (Options? value) {
            setState(() {
              selectedOption = value ?? Options.option2;
            });
          },
        ),
      ],
    );
  }
}
```

---

### **3. Customizing the Radio Button**
You can customize the appearance of the radio button using the `activeColor`, `fillColor`, and `toggleable` properties.

#### Example:
```dart
Radio<Options>(
  value: Options.option1,
  groupValue: selectedOption,
  onChanged: (Options? value) {
    setState(() {
      selectedOption = value ?? Options.option1;
    });
  },
  activeColor: Colors.green, // Color when selected
  fillColor: MaterialStateProperty.resolveWith<Color>((states) {
    if (states.contains(MaterialState.selected)) {
      return Colors.blue; // Color when selected
    }
    return Colors.grey; // Color when unselected
  }),
);
```

---

### **4. Disabling the Radio Button**
You can disable the radio button by setting `onChanged` to `null`.

#### Example:
```dart
Radio<Options>(
  value: Options.option1,
  groupValue: selectedOption,
  onChanged: null, // Disables the radio button
);
```

---

### **5. Using with a ListTile**
You can combine a `Radio` with a `ListTile` to create a more interactive UI.

#### Example:
```dart
ListTile(
  title: Text('Option 1'),
  leading: Radio<Options>(
    value: Options.option1,
    groupValue: selectedOption,
    onChanged: (Options? value) {
      setState(() {
        selectedOption = value ?? Options.option1;
      });
    },
  ),
);
```

---

### **6. Using with a Form**
You can use a `Radio` within a `Form` to manage its state along with other form fields.

#### Example:
```dart
class FormExample extends StatefulWidget {
  @override
  _FormExampleState createState() => _FormExampleState();
}

class _FormExampleState extends State<FormExample> {
  final _formKey = GlobalKey<FormState>();
  Options selectedOption = Options.option1;

  @override
  Widget build(BuildContext context) {
    return Form(
      key: _formKey,
      child: Column(
        children: [
          RadioListTile<Options>(
            title: Text('Option 1'),
            value: Options.option1,
            groupValue: selectedOption,
            onChanged: (Options? value) {
              setState(() {
                selectedOption = value ?? Options.option1;
              });
            },
          ),
          RadioListTile<Options>(
            title: Text('Option 2'),
            value: Options.option2,
            groupValue: selectedOption,
            onChanged: (Options? value) {
              setState(() {
                selectedOption = value ?? Options.option2;
              });
            },
          ),
          ElevatedButton(
            onPressed: () {
              if (_formKey.currentState!.validate()) {
                print('Form submitted');
              }
            },
            child: Text('Submit'),
          ),
        ],
      ),
    );
  }
}
```

---

### **7. Using `RadioListTile`**
The `RadioListTile` widget combines a `Radio` with a `ListTile` for a more integrated look.

#### Example:
```dart
RadioListTile<Options>(
  title: Text('Option 1'),
  value: Options.option1,
  groupValue: selectedOption,
  onChanged: (Options? value) {
    setState(() {
      selectedOption = value ?? Options.option1;
    });
  },
  secondary: Icon(Icons.settings), // Optional icon
);
```

---

### **8. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Radio<Options>(
  value: Options.option1,
  groupValue: selectedOption,
  onChanged: (Options? value) {
    setState(() {
      selectedOption = value ?? Options.option1;
    });
  },
  activeColor: Colors.green,
  fillColor: MaterialStateProperty.resolveWith<Color>((states) {
    if (states.contains(MaterialState.selected)) {
      return Colors.blue;
    }
    return Colors.grey;
  }),
);
```

---

### **Summary of `Radio` Properties**
| Property          | Description                              | Example                                   |
|-------------------|------------------------------------------|-------------------------------------------|
| `value`           | The value represented by this radio button | `value: Options.option1`                |
| `groupValue`      | The currently selected value             | `groupValue: selectedOption`             |
| `onChanged`       | Callback when the radio button is selected | `onChanged: (Options? value) {...}`     |
| `activeColor`     | Color when the radio button is selected  | `activeColor: Colors.green`              |
| `fillColor`       | Color of the radio button fill           | `fillColor: MaterialStateProperty(...)`  |
| `toggleable`      | Whether the radio button can be toggled  | `toggleable: true`                       |

---

### **Example: Full Usage**
Here’s a complete example of a `Radio` with various customizations:
```dart
class RadioExample extends StatefulWidget {
  @override
  _RadioExampleState createState() => _RadioExampleState();
}

class _RadioExampleState extends State<RadioExample> {
  Options selectedOption = Options.option1;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Radio<Options>(
          value: Options.option1,
          groupValue: selectedOption,
          onChanged: (Options? value) {
            setState(() {
              selectedOption = value ?? Options.option1;
            });
          },
          activeColor: Colors.green,
          fillColor: MaterialStateProperty.resolveWith<Color>((states) {
            if (states.contains(MaterialState.selected)) {
              return Colors.blue;
            }
            return Colors.grey;
          }),
        ),
        Radio<Options>(
          value: Options.option2,
          groupValue: selectedOption,
          onChanged: (Options? value) {
            setState(() {
              selectedOption = value ?? Options.option2;
            });
          },
        ),
      ],
    );
  }
}
```

---

## Slider Widget 

Here’s a summary of the [Flutter `Slider` class documentation](https://api.flutter.dev/flutter/material/Slider-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Slider` Widget**
The `Slider` widget is a Material Design slider that allows users to select a value from a range of values by dragging a thumb along a track. It is commonly used for settings like volume control, brightness adjustment, etc.

---

### **1. Basic Usage**
The simplest way to use a `Slider` is to provide a `value`, `min`, `max`, and an `onChanged` callback.

#### Example:
```dart
double sliderValue = 50;

Slider(
  value: sliderValue,
  min: 0,
  max: 100,
  onChanged: (double value) {
    setState(() {
      sliderValue = value;
    });
  },
);
```

---

### **2. Handling State**
The `Slider` requires state management to update its value. Typically, this is done using a `StatefulWidget`.

#### Example:
```dart
class SliderExample extends StatefulWidget {
  @override
  _SliderExampleState createState() => _SliderExampleState();
}

class _SliderExampleState extends State<SliderExample> {
  double sliderValue = 50;

  @override
  Widget build(BuildContext context) {
    return Slider(
      value: sliderValue,
      min: 0,
      max: 100,
      onChanged: (double value) {
        setState(() {
          sliderValue = value;
        });
      },
    );
  }
}
```

---

### **3. Customizing the Slider**
You can customize the appearance of the slider using the `activeColor`, `inactiveColor`, and `thumbColor` properties.

#### Example:
```dart
Slider(
  value: sliderValue,
  min: 0,
  max: 100,
  onChanged: (double value) {
    setState(() {
      sliderValue = value;
    });
  },
  activeColor: Colors.green, // Color of the active part of the track
  inactiveColor: Colors.grey, // Color of the inactive part of the track
  thumbColor: Colors.blue, // Color of the thumb
);
```

---

### **4. Adding Divisions**
You can add divisions to the slider using the `divisions` property.

#### Example:
```dart
Slider(
  value: sliderValue,
  min: 0,
  max: 100,
  divisions: 10, // Number of divisions
  label: sliderValue.round().toString(), // Label to display
  onChanged: (double value) {
    setState(() {
      sliderValue = value;
    });
  },
);
```

---

### **5. Adding a Label**
You can add a label to the slider using the `label` property.

#### Example:
```dart
Slider(
  value: sliderValue,
  min: 0,
  max: 100,
  divisions: 10,
  label: sliderValue.round().toString(), // Label to display
  onChanged: (double value) {
    setState(() {
      sliderValue = value;
    });
  },
);
```

---

### **6. Disabling the Slider**
You can disable the slider by setting `onChanged` to `null`.

#### Example:
```dart
Slider(
  value: sliderValue,
  min: 0,
  max: 100,
  onChanged: null, // Disables the slider
);
```

---

### **7. Using with a ListTile**
You can combine a `Slider` with a `ListTile` to create a more interactive UI.

#### Example:
```dart
ListTile(
  title: Text('Slider Value: ${sliderValue.round()}'),
  subtitle: Slider(
    value: sliderValue,
    min: 0,
    max: 100,
    onChanged: (double value) {
      setState(() {
        sliderValue = value;
      });
    },
  ),
);
```

---

### **8. Using with a Form**
You can use a `Slider` within a `Form` to manage its state along with other form fields.

#### Example:
```dart
class FormExample extends StatefulWidget {
  @override
  _FormExampleState createState() => _FormExampleState();
}

class _FormExampleState extends State<FormExample> {
  final _formKey = GlobalKey<FormState>();
  double sliderValue = 50;

  @override
  Widget build(BuildContext context) {
    return Form(
      key: _formKey,
      child: Column(
        children: [
          Slider(
            value: sliderValue,
            min: 0,
            max: 100,
            onChanged: (double value) {
              setState(() {
                sliderValue = value;
              });
            },
          ),
          ElevatedButton(
            onPressed: () {
              if (_formKey.currentState!.validate()) {
                print('Form submitted');
              }
            },
            child: Text('Submit'),
          ),
        ],
      ),
    );
  }
}
```

---

### **9. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Slider(
  value: sliderValue,
  min: 0,
  max: 100,
  divisions: 10,
  label: sliderValue.round().toString(),
  onChanged: (double value) {
    setState(() {
      sliderValue = value;
    });
  },
  activeColor: Colors.green,
  inactiveColor: Colors.grey,
  thumbColor: Colors.blue,
);
```

---

### **Summary of `Slider` Properties**
| Property          | Description                              | Example                                   |
|-------------------|------------------------------------------|-------------------------------------------|
| `value`           | The current value of the slider          | `value: sliderValue`                      |
| `min`             | The minimum value of the slider          | `min: 0`                                  |
| `max`             | The maximum value of the slider          | `max: 100`                                |
| `onChanged`       | Callback when the slider value changes   | `onChanged: (double value) {...}`         |
| `activeColor`     | Color of the active part of the track    | `activeColor: Colors.green`               |
| `inactiveColor`   | Color of the inactive part of the track  | `inactiveColor: Colors.grey`              |
| `thumbColor`      | Color of the thumb                       | `thumbColor: Colors.blue`                 |
| `divisions`       | Number of divisions                      | `divisions: 10`                           |
| `label`           | Label to display                         | `label: sliderValue.round().toString()`   |

---

### **Example: Full Usage**
Here’s a complete example of a `Slider` with various customizations:
```dart
class SliderExample extends StatefulWidget {
  @override
  _SliderExampleState createState() => _SliderExampleState();
}

class _SliderExampleState extends State<SliderExample> {
  double sliderValue = 50;

  @override
  Widget build(BuildContext context) {
    return Slider(
      value: sliderValue,
      min: 0,
      max: 100,
      divisions: 10,
      label: sliderValue.round().toString(),
      onChanged: (double value) {
        setState(() {
          sliderValue = value;
        });
      },
      activeColor: Colors.green,
      inactiveColor: Colors.grey,
      thumbColor: Colors.blue,
    );
  }
}
```

---

## Inkwell Widget 

Here’s a summary of the [Flutter `InkWell` class documentation](https://api.flutter.dev/flutter/material/InkWell-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `InkWell` Widget**
The `InkWell` widget is a Material Design ink splash effect that responds to touch events. It is commonly used to make any widget interactive by adding ripple effects when tapped.

---

### **1. Basic Usage**
The simplest way to use an `InkWell` is to wrap it around a child widget and provide an `onTap` callback.

#### Example:
```dart
InkWell(
  onTap: () {
    print('Tapped!');
  },
  child: Container(
    padding: EdgeInsets.all(20),
    child: Text('Tap Me'),
  ),
);
```

---

### **2. Handling Different Tap Events**
You can handle different tap events like `onDoubleTap`, `onLongPress`, and `onTapCancel`.

#### Example:
```dart
InkWell(
  onTap: () {
    print('Tapped!');
  },
  onDoubleTap: () {
    print('Double Tapped!');
  },
  onLongPress: () {
    print('Long Pressed!');
  },
  onTapCancel: () {
    print('Tap Cancelled!');
  },
  child: Container(
    padding: EdgeInsets.all(20),
    child: Text('Tap Me'),
  ),
);
```

---

### **3. Customizing the Splash Color**
You can customize the splash color using the `splashColor` and `highlightColor` properties.

#### Example:
```dart
InkWell(
  onTap: () {
    print('Tapped!');
  },
  splashColor: Colors.blue, // Splash color
  highlightColor: Colors.green, // Highlight color
  child: Container(
    padding: EdgeInsets.all(20),
    child: Text('Tap Me'),
  ),
);
```

---

### **4. Customizing the Border Radius**
You can customize the border radius of the ink splash using the `borderRadius` property.

#### Example:
```dart
InkWell(
  onTap: () {
    print('Tapped!');
  },
  borderRadius: BorderRadius.circular(10), // Rounded corners
  child: Container(
    padding: EdgeInsets.all(20),
    child: Text('Tap Me'),
  ),
);
```

---

### **5. Disabling the InkWell**
You can disable the `InkWell` by setting `onTap` to `null`.

#### Example:
```dart
InkWell(
  onTap: null, // Disables the InkWell
  child: Container(
    padding: EdgeInsets.all(20),
    child: Text('Disabled'),
  ),
);
```

---

### **6. Using with a ListTile**
You can combine an `InkWell` with a `ListTile` to create a more interactive UI.

#### Example:
```dart
ListTile(
  title: Text('Item 1'),
  onTap: () {
    print('Item 1 Tapped!');
  },
);
```

---

### **7. Using with a Card**
You can wrap a `Card` with an `InkWell` to make the entire card interactive.

#### Example:
```dart
InkWell(
  onTap: () {
    print('Card Tapped!');
  },
  child: Card(
    child: Container(
      padding: EdgeInsets.all(20),
      child: Text('Tap Me'),
    ),
  ),
);
```

---

### **8. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
InkWell(
  onTap: () {
    print('Tapped!');
  },
  onDoubleTap: () {
    print('Double Tapped!');
  },
  onLongPress: () {
    print('Long Pressed!');
  },
  splashColor: Colors.blue,
  highlightColor: Colors.green,
  borderRadius: BorderRadius.circular(10),
  child: Container(
    padding: EdgeInsets.all(20),
    child: Text('Tap Me'),
  ),
);
```

---

### **Summary of `InkWell` Properties**
| Property          | Description                              | Example                                   |
|-------------------|------------------------------------------|-------------------------------------------|
| `onTap`           | Callback when tapped                     | `onTap: () { print('Tapped!'); }`        |
| `onDoubleTap`     | Callback when double tapped              | `onDoubleTap: () { print('Double Tapped!'); }` |
| `onLongPress`     | Callback when long pressed               | `onLongPress: () { print('Long Pressed!'); }` |
| `onTapCancel`     | Callback when tap is cancelled           | `onTapCancel: () { print('Tap Cancelled!'); }` |
| `splashColor`     | Color of the splash effect               | `splashColor: Colors.blue`               |
| `highlightColor`  | Color of the highlight effect            | `highlightColor: Colors.green`           |
| `borderRadius`    | Border radius of the ink splash          | `borderRadius: BorderRadius.circular(10)`|
| `child`           | The widget inside the InkWell            | `child: Container(...)`                  |

---

### **Example: Full Usage**
Here’s a complete example of an `InkWell` with various customizations:
```dart
InkWell(
  onTap: () {
    print('Tapped!');
  },
  onDoubleTap: () {
    print('Double Tapped!');
  },
  onLongPress: () {
    print('Long Pressed!');
  },
  splashColor: Colors.blue,
  highlightColor: Colors.green,
  borderRadius: BorderRadius.circular(10),
  child: Container(
    padding: EdgeInsets.all(20),
    child: Text('Tap Me'),
  ),
);
```

---

## Form Widget 

Here’s a summary of the [Flutter `Form` class documentation](https://api.flutter.dev/flutter/widgets/Form-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Form` Widget**
The `Form` widget is a container for grouping and validating multiple form fields. It provides a way to manage the state of form fields, validate user input, and handle form submission.

---

### **1. Basic Usage**
The simplest way to use a `Form` is to wrap it around form fields like `TextFormField` and provide a `GlobalKey` to manage the form's state.

#### Example:
```dart
class MyForm extends StatefulWidget {
  @override
  _MyFormState createState() => _MyFormState();
}

class _MyFormState extends State<MyForm> {
  final _formKey = GlobalKey<FormState>();

  @override
  Widget build(BuildContext context) {
    return Form(
      key: _formKey,
      child: Column(
        children: [
          TextFormField(
            decoration: InputDecoration(labelText: 'Name'),
            validator: (value) {
              if (value == null || value.isEmpty) {
                return 'Please enter your name';
              }
              return null;
            },
          ),
          ElevatedButton(
            onPressed: () {
              if (_formKey.currentState!.validate()) {
                print('Form submitted');
              }
            },
            child: Text('Submit'),
          ),
        ],
      ),
    );
  }
}
```

---

### **2. Managing Form State**
The `Form` widget uses a `GlobalKey<FormState>` to manage the state of the form and validate the form fields.

#### Example:
```dart
final _formKey = GlobalKey<FormState>();

Form(
  key: _formKey,
  child: Column(
    children: [
      TextFormField(
        decoration: InputDecoration(labelText: 'Name'),
        validator: (value) {
          if (value == null || value.isEmpty) {
            return 'Please enter your name';
          }
          return null;
        },
      ),
      ElevatedButton(
        onPressed: () {
          if (_formKey.currentState!.validate()) {
            print('Form submitted');
          }
        },
        child: Text('Submit'),
      ),
    ],
  ),
);
```

---

### **3. Validating Form Fields**
You can validate form fields using the `validator` property of form field widgets like `TextFormField`.

#### Example:
```dart
TextFormField(
  decoration: InputDecoration(labelText: 'Email'),
  validator: (value) {
    if (value == null || value.isEmpty) {
      return 'Please enter your email';
    }
    if (!value.contains('@')) {
      return 'Please enter a valid email';
    }
    return null;
  },
);
```

---

### **4. Saving Form Data**
You can save form data using the `onSaved` property of form field widgets.

#### Example:
```dart
TextFormField(
  decoration: InputDecoration(labelText: 'Name'),
  onSaved: (value) {
    print('Name: $value');
  },
);
```

---

### **5. Resetting the Form**
You can reset the form using the `reset` method of the `FormState`.

#### Example:
```dart
ElevatedButton(
  onPressed: () {
    _formKey.currentState!.reset();
  },
  child: Text('Reset'),
);
```

---

### **6. Autovalidate Mode**
You can set the `autovalidateMode` property to automatically validate form fields as the user types.

#### Example:
```dart
Form(
  key: _formKey,
  autovalidateMode: AutovalidateMode.onUserInteraction,
  child: Column(
    children: [
      TextFormField(
        decoration: InputDecoration(labelText: 'Name'),
        validator: (value) {
          if (value == null || value.isEmpty) {
            return 'Please enter your name';
          }
          return null;
        },
      ),
      ElevatedButton(
        onPressed: () {
          if (_formKey.currentState!.validate()) {
            print('Form submitted');
          }
        },
        child: Text('Submit'),
      ),
    ],
  ),
);
```

---

### **7. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Form(
  key: _formKey,
  autovalidateMode: AutovalidateMode.onUserInteraction,
  child: Column(
    children: [
      TextFormField(
        decoration: InputDecoration(labelText: 'Name'),
        validator: (value) {
          if (value == null || value.isEmpty) {
            return 'Please enter your name';
          }
          return null;
        },
        onSaved: (value) {
          print('Name: $value');
        },
      ),
      TextFormField(
        decoration: InputDecoration(labelText: 'Email'),
        validator: (value) {
          if (value == null || value.isEmpty) {
            return 'Please enter your email';
          }
          if (!value.contains('@')) {
            return 'Please enter a valid email';
          }
          return null;
        },
        onSaved: (value) {
          print('Email: $value');
        },
      ),
      ElevatedButton(
        onPressed: () {
          if (_formKey.currentState!.validate()) {
            _formKey.currentState!.save();
            print('Form submitted');
          }
        },
        child: Text('Submit'),
      ),
      ElevatedButton(
        onPressed: () {
          _formKey.currentState!.reset();
        },
        child: Text('Reset'),
      ),
    ],
  ),
);
```

---

### **Summary of `Form` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `key`                 | GlobalKey to manage form state           | `key: _formKey`                           |
| `autovalidateMode`    | Automatically validate form fields       | `autovalidateMode: AutovalidateMode.onUserInteraction` |
| `child`               | The widget inside the form               | `child: Column(...)`                      |

---

### **Example: Full Usage**
Here’s a complete example of a `Form` with various customizations:
```dart
class MyForm extends StatefulWidget {
  @override
  _MyFormState createState() => _MyFormState();
}

class _MyFormState extends State<MyForm> {
  final _formKey = GlobalKey<FormState>();

  @override
  Widget build(BuildContext context) {
    return Form(
      key: _formKey,
      autovalidateMode: AutovalidateMode.onUserInteraction,
      child: Column(
        children: [
          TextFormField(
            decoration: InputDecoration(labelText: 'Name'),
            validator: (value) {
              if (value == null || value.isEmpty) {
                return 'Please enter your name';
              }
              return null;
            },
            onSaved: (value) {
              print('Name: $value');
            },
          ),
          TextFormField(
            decoration: InputDecoration(labelText: 'Email'),
            validator: (value) {
              if (value == null || value.isEmpty) {
                return 'Please enter your email';
              }
              if (!value.contains('@')) {
                return 'Please enter a valid email';
              }
              return null;
            },
            onSaved: (value) {
              print('Email: $value');
            },
          ),
          ElevatedButton(
            onPressed: () {
              if (_formKey.currentState!.validate()) {
                _formKey.currentState!.save();
                print('Form submitted');
              }
            },
            child: Text('Submit'),
          ),
          ElevatedButton(
            onPressed: () {
              _formKey.currentState!.reset();
            },
            child: Text('Reset'),
          ),
        ],
      ),
    );
  }
}
```

---

## Inherited Widget 

Here’s a summary of the [Flutter `InheritedWidget` class documentation](https://api.flutter.dev/flutter/widgets/InheritedWidget-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `InheritedWidget` Widget**
The `InheritedWidget` is a base class for widgets that efficiently propagate information down the widget tree. It allows descendant widgets to access data without requiring explicit passing of data through constructors.

---

### **1. Basic Usage**
To use `InheritedWidget`, you need to create a subclass that holds the data and provides a static method to access it.

#### Example:
```dart
class MyInheritedWidget extends InheritedWidget {
  final int data;

  MyInheritedWidget({
    required this.data,
    required Widget child,
  }) : super(child: child);

  @override
  bool updateShouldNotify(MyInheritedWidget oldWidget) {
    return oldWidget.data != data;
  }

  static MyInheritedWidget? of(BuildContext context) {
    return context.dependOnInheritedWidgetOfExactType<MyInheritedWidget>();
  }
}
```

---

### **2. Using the Inherited Widget**
You can use the `InheritedWidget` by wrapping it around the widget tree and accessing the data in descendant widgets.

#### Example:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MyInheritedWidget(
      data: 42,
      child: MaterialApp(
        home: Scaffold(
          appBar: AppBar(title: Text('InheritedWidget Example')),
          body: MyChildWidget(),
        ),
      ),
    );
  }
}

class MyChildWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final inheritedWidget = MyInheritedWidget.of(context);
    return Center(
      child: Text('Data: ${inheritedWidget?.data}'),
    );
  }
}
```

---

### **3. Updating the Inherited Widget**
When the data in the `InheritedWidget` changes, the `updateShouldNotify` method determines whether to rebuild the dependent widgets.

#### Example:
```dart
class MyInheritedWidget extends InheritedWidget {
  final int data;

  MyInheritedWidget({
    required this.data,
    required Widget child,
  }) : super(child: child);

  @override
  bool updateShouldNotify(MyInheritedWidget oldWidget) {
    return oldWidget.data != data;
  }

  static MyInheritedWidget? of(BuildContext context) {
    return context.dependOnInheritedWidgetOfExactType<MyInheritedWidget>();
  }
}
```

---

### **4. Accessing Data in Descendant Widgets**
You can access the data in descendant widgets using the static `of` method.

#### Example:
```dart
class MyChildWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final inheritedWidget = MyInheritedWidget.of(context);
    return Center(
      child: Text('Data: ${inheritedWidget?.data}'),
    );
  }
}
```

---

### **5. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
class MyInheritedWidget extends InheritedWidget {
  final int data;

  MyInheritedWidget({
    required this.data,
    required Widget child,
  }) : super(child: child);

  @override
  bool updateShouldNotify(MyInheritedWidget oldWidget) {
    return oldWidget.data != data;
  }

  static MyInheritedWidget? of(BuildContext context) {
    return context.dependOnInheritedWidgetOfExactType<MyInheritedWidget>();
  }
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MyInheritedWidget(
      data: 42,
      child: MaterialApp(
        home: Scaffold(
          appBar: AppBar(title: Text('InheritedWidget Example')),
          body: MyChildWidget(),
        ),
      ),
    );
  }
}

class MyChildWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final inheritedWidget = MyInheritedWidget.of(context);
    return Center(
      child: Text('Data: ${inheritedWidget?.data}'),
    );
  }
}
```

---

### **Summary of `InheritedWidget` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `child`               | The widget tree below the InheritedWidget | `child: MyChildWidget()`                 |
| `updateShouldNotify`  | Determines whether to rebuild dependent widgets | `updateShouldNotify: (oldWidget) {...}` |
| `of`                  | Static method to access the InheritedWidget | `MyInheritedWidget.of(context)`          |

---

### **Example: Full Usage**
Here’s a complete example of an `InheritedWidget` with various customizations:
```dart
class MyInheritedWidget extends InheritedWidget {
  final int data;

  MyInheritedWidget({
    required this.data,
    required Widget child,
  }) : super(child: child);

  @override
  bool updateShouldNotify(MyInheritedWidget oldWidget) {
    return oldWidget.data != data;
  }

  static MyInheritedWidget? of(BuildContext context) {
    return context.dependOnInheritedWidgetOfExactType<MyInheritedWidget>();
  }
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MyInheritedWidget(
      data: 42,
      child: MaterialApp(
        home: Scaffold(
          appBar: AppBar(title: Text('InheritedWidget Example')),
          body: MyChildWidget(),
        ),
      ),
    );
  }
}

class MyChildWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final inheritedWidget = MyInheritedWidget.of(context);
    return Center(
      child: Text('Data: ${inheritedWidget?.data}'),
    );
  }
}
```

---

## Stateless Widget 

Here’s a summary of the [Flutter `StatelessWidget` class documentation](https://api.flutter.dev/flutter/widgets/StatelessWidget-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `StatelessWidget` Widget**
The `StatelessWidget` is a base class for widgets that do not require mutable state. It is used to build UI components that depend only on their configuration (i.e., their constructor arguments) and do not change over time.

---

### **1. Basic Usage**
To create a `StatelessWidget`, you need to override the `build` method and return a widget tree.

#### Example:
```dart
class MyStatelessWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      color: Colors.blue,
      child: Center(
        child: Text('Hello, Flutter!'),
      ),
    );
  }
}
```

---

### **2. Using Constructor Parameters**
You can pass parameters to a `StatelessWidget` via its constructor to customize its behavior.

#### Example:
```dart
class GreetingWidget extends StatelessWidget {
  final String name;

  GreetingWidget({required this.name});

  @override
  Widget build(BuildContext context) {
    return Text('Hello, $name!');
  }
}

// Usage
GreetingWidget(name: 'Alice');
```

---

### **3. Building a UI**
The `build` method is where you define the UI for the widget. It must return a single widget, but that widget can contain a complex tree of other widgets.

#### Example:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('StatelessWidget Example')),
        body: Center(
          child: GreetingWidget(name: 'Alice'),
        ),
      ),
    );
  }
}
```

---

### **4. StatelessWidget Lifecycle**
Since `StatelessWidget` does not maintain state, it has a simple lifecycle:
1. **Creation**: The widget is created with its constructor.
2. **Build**: The `build` method is called to render the UI.
3. **Disposal**: The widget is removed from the tree and disposed of.

---

### **5. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
class MyStatelessWidget extends StatelessWidget {
  final String title;
  final String message;

  MyStatelessWidget({required this.title, required this.message});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(title),
      ),
      body: Center(
        child: Text(message),
      ),
    );
  }
}

// Usage
MyStatelessWidget(
  title: 'Welcome',
  message: 'Hello, Flutter!',
);
```

---

### **Summary of `StatelessWidget` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `build`               | Builds the UI for the widget             | `build: (context) { return ... }`         |
| Constructor Parameters | Pass data to the widget                 | `MyWidget({required this.data})`          |

---

### **Example: Full Usage**
Here’s a complete example of a `StatelessWidget` with various customizations:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('StatelessWidget Example')),
        body: Center(
          child: GreetingWidget(name: 'Alice'),
        ),
      ),
    );
  }
}

class GreetingWidget extends StatelessWidget {
  final String name;

  GreetingWidget({required this.name});

  @override
  Widget build(BuildContext context) {
    return Text('Hello, $name!');
  }
}
```

---

## Stateful widget 

Here’s a summary of the [Flutter `StatefulWidget` class documentation](https://api.flutter.dev/flutter/widgets/StatefulWidget-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `StatefulWidget` Widget**
The `StatefulWidget` is a base class for widgets that can change over time. It maintains mutable state, allowing the UI to update dynamically in response to user interactions, data changes, or other events.

---

### **1. Basic Usage**
To create a `StatefulWidget`, you need to:
1. Create a subclass of `StatefulWidget`.
2. Create a corresponding `State` subclass to manage the widget's state.

#### Example:
```dart
class MyStatefulWidget extends StatefulWidget {
  @override
  _MyStatefulWidgetState createState() => _MyStatefulWidgetState();
}

class _MyStatefulWidgetState extends State<MyStatefulWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('StatefulWidget Example')),
      body: Center(
        child: Text('Counter: $_counter'),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        child: Icon(Icons.add),
      ),
    );
  }
}
```

---

### **2. Managing State**
The `State` object is where you store mutable data and call `setState` to trigger UI updates.

#### Example:
```dart
class _MyStatefulWidgetState extends State<MyStatefulWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Text('Counter: $_counter'),
    );
  }
}
```

---

### **3. Using Constructor Parameters**
You can pass parameters to a `StatefulWidget` via its constructor, but the state is managed in the `State` object.

#### Example:
```dart
class CounterWidget extends StatefulWidget {
  final int initialValue;

  CounterWidget({required this.initialValue});

  @override
  _CounterWidgetState createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int _counter;

  _CounterWidgetState() : _counter = 0;

  @override
  void initState() {
    super.initState();
    _counter = widget.initialValue; // Access the widget's properties
  }

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Text('Counter: $_counter'),
    );
  }
}
```

---

### **4. Lifecycle Methods**
The `State` object has several lifecycle methods:
- `initState`: Called once when the state is created.
- `didUpdateWidget`: Called when the widget is rebuilt with new configuration.
- `dispose`: Called when the state is removed from the tree.

#### Example:
```dart
class _MyStatefulWidgetState extends State<MyStatefulWidget> {
  @override
  void initState() {
    super.initState();
    print('State initialized');
  }

  @override
  void didUpdateWidget(MyStatefulWidget oldWidget) {
    super.didUpdateWidget(oldWidget);
    print('Widget updated');
  }

  @override
  void dispose() {
    print('State disposed');
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Container();
  }
}
```

---

### **5. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
class CounterWidget extends StatefulWidget {
  final int initialValue;

  CounterWidget({required this.initialValue});

  @override
  _CounterWidgetState createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int _counter;

  _CounterWidgetState() : _counter = 0;

  @override
  void initState() {
    super.initState();
    _counter = widget.initialValue;
  }

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Counter')),
      body: Center(
        child: Text('Counter: $_counter'),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        child: Icon(Icons.add),
      ),
    );
  }
}
```

---

### **Summary of `StatefulWidget` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `createState`         | Creates the state object                 | `createState: () => _MyState()`           |
| `State`               | Manages mutable state                    | `class _MyState extends State<MyWidget>`  |
| `setState`            | Triggers UI updates                      | `setState(() { ... })`                    |
| `initState`           | Called once when state is created        | `initState: () { ... }`                   |
| `didUpdateWidget`     | Called when widget is updated            | `didUpdateWidget: (oldWidget) { ... }`    |
| `dispose`             | Called when state is disposed            | `dispose: () { ... }`                     |

---

### **Example: Full Usage**
Here’s a complete example of a `StatefulWidget` with various customizations:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: CounterWidget(initialValue: 0),
    );
  }
}

class CounterWidget extends StatefulWidget {
  final int initialValue;

  CounterWidget({required this.initialValue});

  @override
  _CounterWidgetState createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int _counter;

  _CounterWidgetState() : _counter = 0;

  @override
  void initState() {
    super.initState();
    _counter = widget.initialValue;
  }

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Counter')),
      body: Center(
        child: Text('Counter: $_counter'),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        child: Icon(Icons.add),
      ),
    );
  }
}
```

---

## Styling Widget using theme  

Here’s a summary of the [Flutter `Theme` class documentation](https://api.flutter.dev/flutter/material/Theme-class.html), using the same method with explanations and **code examples**:

---

### **Flutter `Theme` Widget**
The `Theme` widget is used to define the visual design of an app, such as colors, fonts, and shapes. It allows you to apply a consistent design across your app by providing a `ThemeData` object.

---

### **1. Basic Usage**
The simplest way to use a `Theme` is to wrap it around your app or a part of your app and provide a `ThemeData` object.

#### Example:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData(
        primarySwatch: Colors.blue,
        brightness: Brightness.light,
      ),
      home: MyHomePage(),
    );
  }
}
```

---

### **2. Customizing Theme Data**
You can customize the theme by providing a `ThemeData` object with properties like `primaryColor`, `accentColor`, `textTheme`, etc.

#### Example:
```dart
ThemeData(
  primaryColor: Colors.blue,
  accentColor: Colors.green,
  textTheme: TextTheme(
    headline1: TextStyle(fontSize: 32, fontWeight: FontWeight.bold),
    bodyText1: TextStyle(fontSize: 16, color: Colors.black),
  ),
);
```

---

### **3. Applying a Theme to a Subtree**
You can apply a theme to a specific part of your app by wrapping it with a `Theme` widget.

#### Example:
```dart
Theme(
  data: ThemeData(
    primaryColor: Colors.red,
    accentColor: Colors.orange,
  ),
  child: Container(
    color: Theme.of(context).primaryColor,
    child: Text('Hello, Flutter!', style: Theme.of(context).textTheme.headline1),
  ),
);
```

---

### **4. Inheriting the Theme**
You can access the current theme using `Theme.of(context)`.

#### Example:
```dart
Text(
  'Hello, Flutter!',
  style: Theme.of(context).textTheme.headline1,
);
```

---

### **5. Overriding the Theme**
You can override the theme for a specific part of your app by wrapping it with a `Theme` widget and setting the `data` property.

#### Example:
```dart
Theme(
  data: Theme.of(context).copyWith(
    primaryColor: Colors.purple,
  ),
  child: Container(
    color: Theme.of(context).primaryColor,
    child: Text('Hello, Flutter!'),
  ),
);
```

---

### **6. Using ThemeData**
The `ThemeData` class provides a wide range of properties to customize the theme.

#### Example:
```dart
ThemeData(
  primarySwatch: Colors.blue,
  brightness: Brightness.light,
  textTheme: TextTheme(
    headline1: TextStyle(fontSize: 32, fontWeight: FontWeight.bold),
    bodyText1: TextStyle(fontSize: 16, color: Colors.black),
  ),
  buttonTheme: ButtonThemeData(
    buttonColor: Colors.green,
    textTheme: ButtonTextTheme.primary,
  ),
);
```

---

### **7. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
Theme(
  data: ThemeData(
    primarySwatch: Colors.blue,
    brightness: Brightness.light,
    textTheme: TextTheme(
      headline1: TextStyle(fontSize: 32, fontWeight: FontWeight.bold),
      bodyText1: TextStyle(fontSize: 16, color: Colors.black),
    ),
    buttonTheme: ButtonThemeData(
      buttonColor: Colors.green,
      textTheme: ButtonTextTheme.primary,
    ),
  ),
  child: Container(
    color: Theme.of(context).primaryColor,
    child: Text('Hello, Flutter!', style: Theme.of(context).textTheme.headline1),
  ),
);
```

---

### **Summary of `Theme` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `data`                | The theme data to apply                  | `data: ThemeData(...)`                    |
| `child`               | The widget tree below the theme          | `child: Container(...)`                   |
| `Theme.of(context)`   | Accesses the current theme               | `Theme.of(context).primaryColor`          |
| `ThemeData`           | Customizes the theme                     | `ThemeData(primarySwatch: Colors.blue)`   |

---

### **Example: Full Usage**
Here’s a complete example of a `Theme` with various customizations:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      theme: ThemeData(
        primarySwatch: Colors.blue,
        brightness: Brightness.light,
        textTheme: TextTheme(
          headline1: TextStyle(fontSize: 32, fontWeight: FontWeight.bold),
          bodyText1: TextStyle(fontSize: 16, color: Colors.black),
        ),
        buttonTheme: ButtonThemeData(
          buttonColor: Colors.green,
          textTheme: ButtonTextTheme.primary,
        ),
      ),
      home: MyHomePage(),
    );
  }
}

class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Theme Example')),
      body: Center(
        child: Text('Hello, Flutter!', style: Theme.of(context).textTheme.headline1),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {},
        child: Icon(Icons.add),
      ),
    );
  }
}
```

---

## Responsive Widgets using `MediaQuery` and `SafeArea`

Here’s a summary of the [Flutter documentation on `SafeArea` and `MediaQuery`](https://docs.flutter.dev/ui/adaptive-responsive/safearea-mediaquery), using the same method with explanations and **code examples**:

---

### **Flutter `SafeArea` and `MediaQuery`**
These widgets are essential for creating adaptive and responsive UIs in Flutter. They help ensure that your app looks good on different devices and screen sizes.

---

### **1. `SafeArea` Widget**
The `SafeArea` widget ensures that its child is not obscured by system UI elements like notches, status bars, or navigation bars.

#### Example:
```dart
SafeArea(
  child: Container(
    color: Colors.blue,
    child: Text('This text is within the safe area.'),
  ),
);
```

---

### **2. `MediaQuery` Widget**
The `MediaQuery` widget provides information about the current device's screen size, orientation, and other display properties.

#### Example:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final mediaQuery = MediaQuery.of(context);
    final screenWidth = mediaQuery.size.width;
    final screenHeight = mediaQuery.size.height;

    return Scaffold(
      body: Center(
        child: Text('Screen Width: $screenWidth, Screen Height: $screenHeight'),
      ),
    );
  }
}
```

---

### **3. Combining `SafeArea` and `MediaQuery`**
You can combine `SafeArea` and `MediaQuery` to create responsive layouts that adapt to different screen sizes and avoid system UI elements.

#### Example:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final mediaQuery = MediaQuery.of(context);
    final screenWidth = mediaQuery.size.width;
    final screenHeight = mediaQuery.size.height;

    return SafeArea(
      child: Scaffold(
        body: Center(
          child: Container(
            width: screenWidth * 0.8,
            height: screenHeight * 0.5,
            color: Colors.blue,
            child: Center(
              child: Text('Responsive Container'),
            ),
          ),
        ),
      ),
    );
  }
}
```

---

### **4. Handling Orientation Changes**
You can use `MediaQuery` to detect the device's orientation and adjust the layout accordingly.

#### Example:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final mediaQuery = MediaQuery.of(context);
    final isPortrait = mediaQuery.orientation == Orientation.portrait;

    return Scaffold(
      body: Center(
        child: Text(isPortrait ? 'Portrait Mode' : 'Landscape Mode'),
      ),
    );
  }
}
```

---

### **5. Using `MediaQueryData`**
The `MediaQueryData` class provides detailed information about the device's display, such as padding, view insets, and text scaling.

#### Example:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final mediaQuery = MediaQuery.of(context);
    final padding = mediaQuery.padding;
    final viewInsets = mediaQuery.viewInsets;
    final textScaleFactor = mediaQuery.textScaleFactor;

    return Scaffold(
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text('Padding: $padding'),
            Text('View Insets: $viewInsets'),
            Text('Text Scale Factor: $textScaleFactor'),
          ],
        ),
      ),
    );
  }
}
```

---

### **6. Combining Properties**
Here’s an example combining multiple properties:

#### Example:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final mediaQuery = MediaQuery.of(context);
    final screenWidth = mediaQuery.size.width;
    final screenHeight = mediaQuery.size.height;
    final isPortrait = mediaQuery.orientation == Orientation.portrait;

    return SafeArea(
      child: Scaffold(
        body: Center(
          child: Container(
            width: isPortrait ? screenWidth * 0.8 : screenWidth * 0.5,
            height: isPortrait ? screenHeight * 0.5 : screenHeight * 0.8,
            color: Colors.blue,
            child: Center(
              child: Text('Responsive Container'),
            ),
          ),
        ),
      ),
    );
  }
}
```

---

### **Summary of `SafeArea` and `MediaQuery` Properties**
| Property              | Description                              | Example                                   |
|-----------------------|------------------------------------------|-------------------------------------------|
| `SafeArea`            | Ensures content is within safe areas     | `SafeArea(child: Container(...))`         |
| `MediaQuery`          | Provides screen information              | `MediaQuery.of(context).size.width`       |
| `MediaQueryData`      | Detailed display information             | `MediaQuery.of(context).padding`          |
| `Orientation`         | Detects device orientation               | `MediaQuery.of(context).orientation`      |

---

### **Example: Full Usage**
Here’s a complete example of using `SafeArea` and `MediaQuery` together:
```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final mediaQuery = MediaQuery.of(context);
    final screenWidth = mediaQuery.size.width;
    final screenHeight = mediaQuery.size.height;
    final isPortrait = mediaQuery.orientation == Orientation.portrait;

    return SafeArea(
      child: Scaffold(
        body: Center(
          child: Container(
            width: isPortrait ? screenWidth * 0.8 : screenWidth * 0.5,
            height: isPortrait ? screenHeight * 0.5 : screenHeight * 0.8,
            color: Colors.blue,
            child: Center(
              child: Text('Responsive Container'),
            ),
          ),
        ),
      ),
    );
  }
}
```

---

