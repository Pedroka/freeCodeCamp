---
title: Error Handling
localeTitle: Обработка ошибок
---
## Обработка ошибок

Обработка ошибок и, в большей степени, обработка исключений - это функции / методы, написанные для возврата важной информации о манипуляции данными. Обработка ошибок часто используется вместе с обещаниями и обратными вызовами. Обработка ошибок - очень важная вещь, которую должен заботиться любой разработчик во время программирования. Здесь я объясню, как обрабатывать ошибки, возникающие во время выполнения, используя блоки try-catch с примером в программах на C #. Операторы try-catch доступны во всех основных языках программирования с похожим синтаксисом.

### Как работает блок try-catch.

Оператор try-catch состоит из блока **try** и **catch** и дополнительного блока **finally** . Код, который может генерировать исключение, должен быть помещен в блок try. Блок catch принимает исключение, которое может быть выбрано в качестве параметра, а затем обрабатывает это исключение внутри блока. Во время выполнения сначала выполняется код в блоке try. Если выбрано исключение, оно будет передано блоку catch, который будет обработан. Если нет блокировки catch, программа отобразит необработанную ошибку исключения и перестанет работать. Несколько блоков catch используются, если код в блоке try может вызывать более одного исключения. Существует также дополнительный блок **finally,** который будет выполнять код в нем независимо от того, выбрано ли исключение.

Ниже приведен пример программы, которая обрабатывает деление на нулевое исключение, используя предопределенный класс в библиотеке C #. Исключение является базовым классом для всех исключений.

`c# using System; namespace ErrorHandling { class DivideByZero { int result; DivideByZero() { result = 0; } public void division(int num1, int num2) { try { result = num1 / num2; } catch (DivideByZeroException e) { Console.WriteLine("Exception caught: {0}", e); } catch(Exception ex) { Console.WriteLine("Exception caught: {0}", ex); } finally { Console.WriteLine("Result: {0}", result); } } static void Main(string[] args) { DivideByZero d = new DivideByZero(); d.division(10, 0); Console.ReadKey(); } } }`

*   В вышеуказанной программе передача 0 в качестве второго параметра вызовет DivideByZeroExceptions.
    
*   Это исключение будет обрабатываться блоком catch, который имеет класс DivideByZeroException. Если происходят исключения, кроме DivideByZeroExceptions, они будут обрабатываться блоком catch Exception.
    
    Исключение - базовый класс для всех классов исключений, доступных в библиотеке C #. Даже если вы хотите написать свое собственное исключение, вы должны наследовать базовый класс Exception в свою программу.
    

#### Дополнительная информация:

https://quizlet.com/135129010/computer-science-error-handling-flash-cards/ https://en.wikipedia.org/wiki/Exception\_handling