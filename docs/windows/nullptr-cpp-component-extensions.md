---
title: "nullptr  (C++ Component Extensions) | Microsoft Docs"
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
  - "__nullptr keyword (C++)"
  - "nullptr keyword [C++]"
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nullptr  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé `nullptr` représente une *valeur de pointeur null*.  Utilisez le mot clé pour indiquer qu'un handle d'objet, un pointeur intérieur ou un type pointeur natif ne pointe pas sur un objet.  
  
 Utilisez `nullptr` avec du code géré ou natif.  Le compilateur emet des instructions appropriés mais différentes pour les valeurs non managées et natives de pointeur null.  Pour plus d'informations sur l'utilisation de la version C\+\+ ISO de ce mot clé, consultez [nullptr](../cpp/nullptr.md).  
  
 Le mot clé `__nullptr` est spécifique à Microsoft et a la même signification que `nullptr`, mais il s'applique uniquement au code natif.  Si vous utilisez `nullptr` avec le code natif de C\/C\+\+ puis que vous le compilez avec l'option du compilateur [\/clr](../build/reference/clr-common-language-runtime-compilation.md), le compilateur ne peut pas déterminer si `nullptr` indique un caractère ou une valeur gérée de pointeur null.  Pour faire votre espace libre d'intention au compilateur, utilisez `nullptr` pour spécifier une valeur managée ou `__nullptr` pour spécifier une valeur native.  
  
 Le mot clé `nullptr` est équivalent a `Nothing` en Visual Basic et à `null` en C\#.  
  
## Utilisation  
 Le mot clé `nullptr` peut être utilisé partout où un handle, pointeur natif, l'argument de fonction peut être utilisée.  
  
 Le mot clé `nullptr` n'est pas un type et n'est pas prise en charge pour une utilisation avec :  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   `throw nullptr` \(bien que `throw (Object^)nullptr;` fonctionne\)  
  
 Le mot clé `nullptr` peut être utilisé dans l'initialisation des types pointeurs suivants :  
  
-   Pointeur natif  
  
-   Descripteur d'exécution windows  
  
-   Descripteur managé  
  
-   Pointeur interieur managé  
  
 Le mot clé `nullptr` peut être utilisé pour tester si une référence de curseur ou de descripteur est NULL avant que la référence soit utilisée.  
  
 Les appels de fonction parmi les languages qui utilisent des valeurs des pointeurs NULL pour la vérification des erreurs doivent être interprètes correctement.  
  
 Vous ne pouvez pas démarrer un descripteur à zéro ; seul `nullptr` peut être utilisé.  L'attribution de la constante 0 à un handle d'objet produit un `Int32` emboité une conversion à `Object^`.  
  
## Exemple  
 L'exemple de code suivant montre que le mot clé `nullptr` peut être utilisé à chaque fois qu'un handle, pointeur natif, ou argument de fonction peut être utilisé.  Puis l'exemple montre que le mot clé `nullptr` peut s'utiliser pour vérifier une référence avant d'être utilisé.  
  
```  
// mcpp_nullptr.cpp  
// compile with: /clr  
value class V {};  
ref class G {};  
void f(System::Object ^) {}  
  
int main() {  
// Native pointer.  
   int *pN = nullptr;  
// Managed handle.  
   G ^pG = nullptr;  
   V ^pV1 = nullptr;  
// Managed interior pointer.  
   interior_ptr<V> pV2 = nullptr;  
// Reference checking before using a pointer.  
   if (pN == nullptr) {}  
   if (pG == nullptr) {}  
   if (pV1 == nullptr) {}  
   if (pV2 == nullptr) {}  
// nullptr can be used as a function argument.  
   f(nullptr);   // calls f(System::Object ^)  
}  
```  
  
## Exemple  
 **Exemple**  
  
 L'exemple de code suivant montre que `nullptr` et zéro peuvent donc être utilisés l'un et l'autre sur des pointeurs natifs.  
  
```  
// mcpp_nullptr_1.cpp  
// compile with: /clr  
class MyClass {  
public:  
   int i;  
};  
  
int main() {  
   MyClass * pMyClass = nullptr;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
  
   pMyClass = 0;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
}  
```  
  
 **Sortie**  
  
  **pMyClass \=\= nullptr**  
 **pMyClass \=\= 0**  
 **pMyClass \=\= nullptr**  
 **pMyClass \=\= 0**   
## Exemple  
 **Exemple**  
  
 L'exemple de code suivant indique que `nullptr` est interprèté comme un handle à un type ou à un pointeur natif en un type de données.  En cas de surcharge de fonction avec les handles de types différents, une erreur d'ambiguïté est générée.  `nullptr` doit être explicitement converti en type.  
  
```  
// mcpp_nullptr_2.cpp  
// compile with: /clr /LD  
void f(int *){}  
void f(int ^){}  
  
void f_null() {  
   f(nullptr);   // C2668  
   // try one of the following lines instead  
   f((int *) nullptr);  
   f((int ^) nullptr);  
}  
```  
  
## Exemple  
 **Exemple**  
  
 L'exemple de code suivant indique qu'il permet la conversion de `nullptr` et renvoie un pointeur ou un descripteur du type de conversion qui contient la valeur `nullptr`.  
  
```  
// mcpp_nullptr_3.cpp  
// compile with: /clr /LD  
using namespace System;  
template <typename T>   
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type  
  
int main() {  
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)  
  
   // Delete the following line to resolve.  
   f(nullptr);  
  
   f(0);   // T = int, call f(int)  
}  
```  
  
## Exemple  
 **Exemple**  
  
 L'exemple de code suivant indique que `nullptr` peut être utilisé comme paramètre de fonction.  
  
```  
// mcpp_nullptr_4.cpp  
// compile with: /clr  
using namespace System;  
void f(Object ^ x) {  
   Console::WriteLine("test");  
}  
  
int main() {  
   f(nullptr);  
}  
```  
  
 **Sortie**  
  
  **tester**   
## Exemple  
 **Exemple**  
  
 L'exemple de code suivant montre que lorsque les descripteurs sont déclarés et pas explicitement initialisés, leur valeur par défaut est initialisée à `nullptr`.  
  
```  
// mcpp_nullptr_5.cpp  
// compile with: /clr  
using namespace System;  
ref class MyClass {  
public:  
   void Test() {  
      MyClass ^pMyClass;   // gc type  
      if (pMyClass == nullptr)  
         Console::WriteLine("NULL");  
   }  
};  
  
int main() {  
   MyClass ^ x = gcnew MyClass();  
   x -> Test();  
}  
```  
  
 **Sortie**  
  
  **NULL**   
## Exemple  
 **Exemple**  
  
 L'exemple de code suivant indique que `nullptr` peut être affecté à un pointeur natif lorsque vous compilez avec **\/clr**.  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## Conditions requises  
 Options du compilateur : \(Non obligatoires ; pris en charge par les options de génération de code, y compris **\/ZW** et **\/clr**\)  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../cpp/nullptr.md)