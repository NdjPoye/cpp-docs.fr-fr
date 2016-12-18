---
title: "Variable Argument Lists (...) (C++/CLI) | Microsoft Docs"
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
  - "variable argument lists"
  - "parameter arrays"
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Variable Argument Lists (...) (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment utiliser la syntaxe `...` dans Visual C\+\+ pour implémenter les fonctions qui ont un nombre variable d'arguments.  
  
> [!NOTE]
>  Cette rubrique concerne C\+\+\/CLI.  Pour plus d'informations sur l'utilisation de `...` en langage C\+\+ conforme à la norme ISO, consultez [Ellipses et modèles variadiques](../cpp/ellipses-and-variadic-templates.md) et [Ellipses et arguments par défaut](../misc/ellipses-and-default-arguments.md).  
  
 Le paramètre qui utilise `...` doit être le dernier paramètre dans la liste de paramètres.  
  
## Exemple  
  
### Code  
  
```  
// mcppv2_paramarray.cpp  
// compile with: /clr  
using namespace System;  
double average( ... array<Int32>^ arr ) {  
   int i = arr->GetLength(0);  
   double answer = 0.0;  
  
   for (int j = 0 ; j < i ; j++)  
      answer += arr[j];  
  
   return answer / i;  
}  
  
int main() {  
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));  
}  
```  
  
### Sortie  
  
```  
3  
```  
  
## Exemple de code  
 L'exemple suivant montre comment appeler de C\# une fonction Visual C\+\+ qui accepte un nombre variable d'arguments.  
  
```  
// mcppv2_paramarray2.cpp  
// compile with: /clr:safe /LD  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
```  
  
 La fonction `f` peut être appelée à partir de C\# ou de Visual Basic, par exemple, comme s'il s'agissait d'une fonction pouvant prendre un nombre variable d'arguments.  
  
 En C\#, un argument passé à un paramètre `ParamArray` peut être appelé par un nombre d'arguments variable.  L'exemple de code suivant est présenté en C\#.  
  
```  
// mcppv2_paramarray3.cs  
// compile with: /r:mcppv2_paramarray2.dll  
// a C# program  
  
public class X {  
   public static void Main() {  
      // Visual C# will generate a String array to match the   
      // ParamArray attribute  
      C myc = new C();  
      myc.f("hello", "there", "world");  
   }  
}  
```  
  
 Un appel à `f` dans Visual C\+\+ peut transmettre un tableau initialisé ou un tableau de longueur variable.  
  
```  
// mcpp_paramarray4.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
  
int main() {  
   C ^ myc = gcnew C();  
   myc->f("hello", "world", "!!!");  
}  
```  
  
## Voir aussi  
 [Arrays](../windows/arrays-cpp-component-extensions.md)