# LokaliseDemo

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.3.1.

### 1. add lokalize
  ```shell
  $ ng add @angular/localize --skip-confirmation
  ```

### 2. generate i18n xlf file
  2.1 mark text for translation
  ```shell
  src/app/app.component.html
  //
  <h1 i18n="main header|Friendly welcoming message">Hello world!</h1>
  ```
  2.2 generate i18n xlf file
  ```shell
  $ npm run i18n
  ```

### 3. create translation file for other language (ru)
  3.1 copy src/i18n/messages.xlf -> src/i18n/messages.ru.xlf  
  3.2 make changes
  ```shell
  $ sdiff.exe -w 212 src/i18n/messages.xlf src/i18n/messages.ru.xlf
  <?xml version="1.0" encoding="UTF-8" ?>                                                                 <?xml version="1.0" encoding="UTF-8" ?>
  <xliff version="1.2" xmlns="urn:oasis:names:tc:xliff:document:1.2">                                     <xliff version="1.2" xmlns="urn:oasis:names:tc:xliff:document:1.2">
    <file source-language="en-US" datatype="plaintext" original="ng2.template">                         |   <file source-language="en-US" datatype="plaintext" original="ng2.template" target-language="ru">
      <body>                                                                                                  <body>
        <trans-unit id="2241399650733502220" datatype="html">                                                   <trans-unit id="2241399650733502220" datatype="html">
          <source>Hello world!</source>                                                                           <source>Hello world!</source>
                                                                                                        >         <target>Всем привет!</target>
          <context-group purpose="location">                                                                      <context-group purpose="location">
            <context context-type="sourcefile">src/app/app.component.html</context>                                 <context context-type="sourcefile">src/app/app.component.html</context>
            <context context-type="linenumber">1</context>                                                          <context context-type="linenumber">1</context>
          </context-group>                                                                                        </context-group>
          <note priority="1" from="description">Friendly welcoming message</note>                                 <note priority="1" from="description">Friendly welcoming message</note>
          <note priority="1" from="meaning">main header</note>                                                    <note priority="1" from="meaning">main header</note>
        </trans-unit>                                                                                           </trans-unit>
      </body>                                                                                                 </body>
    </file>                                                                                                 </file>
  </xliff>                                                                                                </xliff>
  ```

### 4. run app - use other language localization (ru)
  ```shell
  npm run start:ru
  ```
