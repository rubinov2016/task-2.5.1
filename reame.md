## Краткое описание настройки JaCoCo
Для проверки 100%-го покрытия автотестов используется плагин JaCoCo.
Его настройка в файле pom.xml

1. Инициализация цели "check" на фазе "verify" 
```xml
    <id>jacoco-check</id>
    <phase>verify</phase>
    <goals>
        <goal>check</goal>
    </goals>
```
2. Настройка минимального процента покрытия автотестами, измеряемого к строках исходного кода
```xml
<rule>
   <element>PACKAGE</element>
   <limits>
      <limit>
         <counter>LINE</counter>
         <value>COVEREDRATIO</value>
         <minimum>1.00</minimum>
      </limit>
   </limits>
</rule>
```
При необходимости ключевое слово LINE может заменится на INSTRUCTION или BRANCH
```xml
<counter>LINE</counter>
<value>COVEREDRATIO</value>
```
Минимальный процент покрытия автотестами меняется здесь. Сейчас счетчик установлено на 100%:
```xml
<minimum>1.00</minimum>
```


