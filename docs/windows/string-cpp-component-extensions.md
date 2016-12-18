---
title: "String  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "string support with /clr"
  - "/clr compiler option [C++], string support"
ms.assetid: c695f965-9be0-4e20-9661-373bfee6557e
caps.latest.revision: 19
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# String  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur Visual C\+\+ prend en charge des *chaînes*, qui sont des objets qui représentent le texte comme une séquence de caractères.  Visual C\+\+ prend en charge les variables chaîne, dont la valeur est implicite, et les littéraux, dont la valeur est une chaîne entre guillemets explicite.  
  
## Tous les runtimes  
 Windows Runtime et Common Langage Runtime représentent les chaînes comme des objets dont la mémoire allouée est gérée automatiquement.  Autrement dit, vous n'êtes pas tenu d'ignorer explicitement la mémoire pour une chaîne lorsque la variable chaîne est hors de portée ou votre application se termine.  Pour indiquer que la durée de vie d'un objet chaîne doit être managée automatiquement, déclarez le type chaîne avec le modificateur [handle\-to\-object \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md).  
  
## Windows Runtime  
 L'architecture Windows Runtime nécessite Visual C\+\+ pour implémenter le type de données `String` dans l'espace de noms `Platform`.  Pour plus de facilité, Visual C\+\+ fournit également le type de données `string`, un synonyme de `Platform::String`, dans l'espace de noms `default`.  
  
### Syntaxe  
  
```cpp  
  
// compile with /ZW  
using namespace Platform;  
using namespace default;  
   Platform::String^ MyString1 = "The quick brown fox";  
   String^ MyString2 = "jumped over the lazy dog.";  
   String^ MyString3 = "Hello, world!";  
  
```  
  
### Remarques  
 Pour plus d'informations sur la mise en forme des chaînes, consultez [Platform::String, std::wstring, and Literals \(Platform\)](http://msdn.microsoft.com/fr-fr/ec92fbc6-edf3-4137-a85e-8e29bdb857a8).  
  
### Configuration requise  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
 Cette rubrique explique comment le compilateur Visual C\+\+ traite des littéraux de chaîne lorsque vous l'exécutez à l'aide de l'option **\/clr** du compilateur.  Pour utiliser **\/clr**, vous devez également utiliser le Common Langage Runtime \(CLR\), la syntaxe de C\+\+\/CLI et les objets managés.  Pour plus d'informations sur **\/clr**, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Lors de la compilation avec **\/clr**, le compilateur convertit des littéraux de chaîne en chaînes de type <xref:System.String>.  Pour conserver la rétro\-compatibilité avec le code existant il existe deux exceptions à ceci :  
  
-   Gestion des exceptions.  Lorsqu'un littéral de chaîne est renvoyé, le compilateur l'intercepte en tant que littéral de chaîne.  
  
-   Déduction de modèle.  Lorsqu'un littéral de chaîne est passé comme argument de modèle, le compilateur ne le convertit pas en <xref:System.String>.  Notez que les littéraux de chaîne passés comme argument générique seront promus en <xref:System.String>.  
  
 Le compilateur a également une prise en charge intégrée pour trois opérateurs, que l'on peut passer outre pour personnaliser leur comportement :  
  
-   System::String ^ operator \+\( System::String, System::String\);  
  
-   System::String ^ operator \+\( System::Object, System::String\);  
  
-   System::String ^ operator \+\( System::String, System::Object\);  
  
 Lorsque l'on passe un <xref:System.String>, le compilateur boxera, si nécessaire, puis concatènera l'objet et la chaîne \(avec ToString\).  
  
 Lors de la compilation avec **\/clr:oldSyntax**, des littéraux de chaîne ne seront pas convertis en <xref:System.String>.  
  
> [!NOTE]
>  Le symbole \(" ^ "\) indique que la variable déclarée est un handle vers un objet managé C\+\+\/CLI.  
  
 Pour plus d'informations, consultez [Littéraux de chaîne et de caractère](../cpp/string-and-character-literals-cpp.md).  
  
### Configuration requise  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple de code suivant illustre la concaténation et la comparaison des chaînes.  
  
```cpp  
// string_operators.cpp  
// compile with: /clr  
// In the following code, the caret ("^") indicates that the   
// declared variable is a handle to a C++/CLI managed object.  
using namespace System;  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   // variables of System::String returning a System::String  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   // accessing a character in the string  
   Console::WriteLine(a[2]);  
  
   // concatenation of three System::Strings  
   Console::WriteLine(a + b + c);  
  
   // concatenation of a System::String and string literal  
   Console::WriteLine(a + "zzz");  
  
   // you can append to a System::String ^  
   Console::WriteLine(a + 1);  
   Console::WriteLine(a + 'a');  
   Console::WriteLine(a + 3.1);  
  
   // test System::String ^ for equality  
   a += b;  
   Console::WriteLine(a);  
   a = b;  
   if (a == b)  
      Console::WriteLine("a and b are equal");  
  
   a = "abc";  
   if (a != b)  
      Console::WriteLine("a and b are not equal");  
  
   // System:String ^ and tracking reference  
   String^% rstr1 = a;  
   Console::WriteLine(rstr1);  
  
   // testing an empty System::String ^  
   String ^ n;  
   if (n == nullptr)  
      Console::WriteLine("n is empty");  
}  
```  
  
 **Sortie**  
  
  **12345 ABCDE**  
 **abcghi**  
 **ghiabc**  
 **c**  
 **abcdefghi**  
 **abczzz**  
 **abc1**  
 **abc97**  
 **abc3.1**  
 **12345 ABCDE**  
 **a et b sont égaux.**  
 **a et b ne sont pas égaux.**  
 **abc**  
 **n est vide.** **Exemple**  
  
 L'exemple suivant montre que l'on peut surcharger les opérateurs fournis par le compilateur, et que le compilateur trouvera une surcharge de fonction basée sur le type <xref:System.String>.  
  
```cpp  
// string_operators_2.cpp  
// compile with: /clr  
using namespace System;  
  
// a string^ overload will be favored when calling with a String  
void Test_Overload(const char * a) {   
   Console::WriteLine("const char * a");   
}  
void Test_Overload(String ^ a) {   
   Console::WriteLine("String ^ a");   
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, String ^ b) {  
   return ("overloaded +(String ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(Object ^ a, String ^ b) {  
   return ("overloaded +(Object ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, Object ^ b) {  
   return ("overloaded +(String ^ a, Object ^ b)");  
}  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   Test_Overload("hello");  
   Test_Overload(d);  
}  
```  
  
 **Sortie**  
  
  **overloaded \+\(String ^ a, String ^ b\)**   
 **overloaded \+\(String ^ a, Object ^ b\)**   
 **overloaded \+\(Object ^ a, String ^ b\)**   
 **String ^ a**  
 **const char \* a** **Exemple**  
  
 L'exemple suivant indique que le compilateur respecte la différence entre chaînes natives et chaînes <xref:System.String>.  
  
```cpp  
// string_operators_3.cpp  
// compile with: /clr  
using namespace System;  
int func() {  
   throw "simple string";   // const char *  
};  
  
int func2() {  
   throw "string" + "string";   // returns System::String  
};  
  
template<typename T>  
void func3(T t) {  
   Console::WriteLine(T::typeid);  
}  
  
int main() {  
   try {  
      func();  
   }  
   catch(char * e) {  
      Console::WriteLine("char *");  
   }  
  
   try {  
      func2();  
   }  
   catch(String^ str) {  
      Console::WriteLine("String^ str");  
   }  
  
   func3("string");   // const char *  
   func3("string" + "string");   // returns System::String  
}  
```  
  
 **Sortie**  
  
  **char\***  
 **String^ str**  
 **System.SByte\***  
 **System.String**   
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Littéraux de chaîne et de caractère](../cpp/string-and-character-literals-cpp.md)   
 [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md)