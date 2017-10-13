# AppBuilder Tutorial

## How to create preference files

### 1. In the main menu of UIWearProxy app, click "Select App" and turn on the button of the app that you want to create preference files for.

### 2. Click "Set Preference", then exit UIWearProxy app one time and open the corresponding app.

### 3. Swipe down for notification bar, click the notification from UIWearProxy with description of "Setting Preference".

### 4. Simply choose the elements needed, chosen elements should have red squares around them.

### 5. When finish choosing, double click back button to exit setting preference.

### 6. The preference file will automatically be saved under the file path:

```
/sdcard/UIWear/<app domain name>/Preferences/
```
the file name looks like:
```
YYYY-MM-DD-HH-MM-SS.xml
```
where all should be numbers.

## How to write mapping rule files

### 1. Open the preference file you generated, use the id name in every node appears like this:
```
<node>
    <id>some.node.name</id>
    ...
 </node>
```

### 2. For layout xml files for watch, you could use our templates or create your own.

### 3. Map the id in preference file and watch layout file one to one. Example:
```
<Title from="id from preference xml" to="id from watch layout xml">
        <text>default text</text>
</Title>
```

### Please see the example mapping files for Spotify for further more reference.

## How to create watch apk apps

**Make sure you have Android sdk and Java sdk installed to get this part work.

### 1. Copy the folder with app name including preference files in AppBuilder/src/main/resources.

### 2. In the app folder, Create three more folders: Configs, MappingRules, Resources.

### 3. In Configs, use the file name ic_launcher.png for your icon showing in watch launcher. Use file name app_name.txt to put your watch app name in it.

### 4. In MappingRules, put all the mapping xmls. 

### 5. In Resources, put all layout files and default pictures for initialization.

### 6. Be careful that the xml naming has restrictions: mapping rule xml, corresponding preference xml and layout xml need have similar name structures. 
* For example, with a preference xml named example_pref.xml, the mapping xml should be named as example_rule.xml and the layout xml should be example_layout.xml. 
* What's more, for each list view layout, there is only one preference file for both list and item. 
* Example for list naming: example_list_rule.xml and example_list_item.xml, example_list_pref.xml, example_list_layout.xml and example_list_layout.xml

### 7. In the main class AppBuilderMain.java (path: /AppBuilder/src/main/java/edu/stonybrook/cs/netsys/appbuilder), search for "appPkgNames.clear();", in the nextline, substitude the string part with your app folder name.

### 8. Use terminal tools to compile: cd to Appbuilder folder, and use the command below to compile.
```
./gradlew build
```

### 9. After compiling, cd to /AppBuilder/build/temp/<your app domain>/AppOutput, compile again to form the apk.
```
./gradlew aDebug
```

### 10. Tha apk generated should be under /AppBuilder/build/temp/<your app domain>/AppOutput/app/build/outputs/apk.




