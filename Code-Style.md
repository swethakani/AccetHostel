# Code Style Guidelines for InstiGo-Android

Our code style guidelines is based on the [Square's Android Style Guide](https://github.com/square/java-code-styles/blob/master/configs/codestyles/SquareAndroid.xml).

Download the xml file and [import it](https://user-images.githubusercontent.com/1624385/37678878-9b61b562-2c7f-11e8-9733-d1d593f0aa67.png) in IntelliJ/Android Studio.

### For XML files

InstiGo follows `2 spaces` for the `Indent` and `4 spaces` for the `Continuous Indent` values. (Same as that in Square's Style Guide) You can update these values using following steps:

- Go to **Settings** -> **Editor** -> **Code Style** -> **XML**
- Update the respective values under the **Tabs and Indents** tab

After changing the values, one can simply select the files to indent, `Right click` -> `Reformat Code` -> Check `Rearrange entries` -> `OK`.

### Only a few extra rules

- Line length is 120 characters
- FIXME must not be committed in the repository use TODO instead. FIXME can be used in your own local repository only.

You can run a checkstyle with most rules via a gradle command:

```
$ ./gradlew checkstyle
```

It generates a HTML report in `build/reports/checkstyle/checkstyle.html`.

Try to remove as much warnings as possible, It's not completely possible to remove all the warnings, but over a period of time, we should try to make it as complete as possible.

### Some **DONT's**

- Don't use Hungarian Notation like `mContext` `mCount` etc
- Don't use underscores in variable names
- All constants should be CAPS. e.g `MINIMUM_TIMEOUT_ERROR_EXTERNAL`
- Always use `Locale.ENGLISH` when using `String.format()` unless the format itself is locale dependent e.g. `String query = String.format(Locale.ENGLISH,...`
- Never concat `null` with `""` (Empty String). It will become `"null"` e.g. `String.equals("" + null, "null") == TRUE`
