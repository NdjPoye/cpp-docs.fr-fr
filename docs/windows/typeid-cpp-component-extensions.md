---
title: "typeid (Extensions de composant C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "typeid, mot clé [C++]"
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
caps.latest.revision: 35
caps.handback.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# typeid (Extensions de composant C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient une valeur indiquant le type d'un objet.  
  
> [!WARNING]
>  Cette rubrique fait référence à la version de composant d'extensions C\+\+ du typeid.  Pour obtenir la version ISO C\+\+ de ce mot clé, consultez [typeid, opérateur](../cpp/typeid-operator.md).  
  
## Tous les runtimes  
  
### Syntaxe  
  
```cpp  
  
T::typeid  
```  
  
### Paramètres  
 *T*  
 Nom de type.  
  
## Windows Runtime  
  
### Syntaxe  
  
```cpp  
Platform::Type^ type = T::typeid;  
```  
  
### Paramètres  
 `T`  
 Nom de type.  
  
### Remarques  
 Dans [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)], le typeid retourne un [Platform::Type](../Topic/Platform::Type%20Class.md) qui est construit à partir d'informations de type runtime.  
  
### Configuration requise  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Syntaxe**  
  
```  
  
type::typeid  
```  
  
 **Paramètres**  
  
 *type*  
 Le nom d'un type \(déclarateur abstrait\) pour lequel vous souhaitez l'objet System::Type.  
  
 **Remarques**  
  
 `typeid` est utilisé pour obtenir le <xref:System.Type> d'un type au moment de la compilation.  
  
 `typeid` est semblable à l'obtention du System::Type d'un type au moment de l'exécution à l'aide de <xref:System.Type.GetType%2A> ou de <xref:System.Object.GetType%2A>.  Toutefois, typeid accepte un seul nom de type en tant que paramètre.  Si vous voulez utiliser une instance de type pour obtenir son nom de System::Type, utilisez GetType.  
  
 `typeid` doit pouvoir évaluer un nom de type \(type\) au moment de la compilation, alors que GetType évalue le type à retourner au moment de l'exécution.  
  
 `typeid` peut prendre un nom de type natif ou un alias Common Language Runtime du nom de type natif ; consultez [Équivalents .NET Framework des types natifs C\+\+](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) pour plus d'informations.  
  
 `typeid` fonctionne également avec les types natifs, même s'il retournera toujours un System::Type.  Pour obtenir une structure type\_info, utilisez [typeid, opérateur](../cpp/typeid-operator.md).  
  
 `typeid` succède à [\_\_typeof](../misc/typeof.md) dans la syntaxe **\/clr** précédente.  
  
### Configuration requise  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple suivant compare le mot clé typeid au membre GetType\(\).  
  
```  
// keyword__typeid.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   Type ^ pType = pG->GetType();  
   Type ^ pType2 = G::typeid;  
  
   if (pType == pType2)  
      Console::WriteLine("typeid and GetType returned the same System::Type");  
   Console::WriteLine(G::typeid);  
  
   typedef float* FloatPtr;  
   Console::WriteLine(FloatPtr::typeid);  
}  
```  
  
 **Sortie**  
  
  **typeid et GetType ont retourné le même System::Type**  
**G**  
 **System.Single\*** **Exemple**  
  
 L'exemple suivant indique qu'une variable de type System::Type peut être utilisée pour obtenir les attributs d'un type.  Il montre également que, pour certains types, vous devez créer un typedef pour utiliser `typeid`.  
  
```  
// keyword__typeid_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Security;  
using namespace System::Security::Permissions;  
  
typedef int ^ handle_to_int;  
typedef int * pointer_to_int;  
  
public ref class MyClass {};  
  
class MyClass2 {};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass {  
public:  
   AtClass(Type ^) {  
      Console::WriteLine("in AtClass Type ^ constructor");  
   }  
};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass2 {  
public:  
   AtClass2() {  
      Console::WriteLine("in AtClass2 constructor");  
   }  
};  
  
// Apply the AtClass and AtClass2 attributes to class B  
[AtClass(MyClass::typeid), AtClass2]     
[AttributeUsage(AttributeTargets::All)]  
ref class B : Attribute {};  
  
int main() {  
   Type ^ MyType = B::typeid;  
  
   Console::WriteLine(MyType->IsClass);  
  
   array<Object^>^ MyArray = MyType -> GetCustomAttributes(true);  
   for (int i = 0 ; i < MyArray->Length ; i++ )  
      Console::WriteLine(MyArray[i]);  
  
   if (int::typeid != pointer_to_int::typeid)  
      Console::WriteLine("int::typeid != pointer_to_int::typeid, as expected");  
  
   if (int::typeid == handle_to_int::typeid)  
      Console::WriteLine("int::typeid == handle_to_int::typeid, as expected");  
}  
```  
  
 **Sortie**  
  
  **True**  
 **dans le constructeur AtClass2**  
 **dans le constructeur ^ de type AtClass**  
 **AtClass2**  
 **System.AttributeUsageAttribute**  
 **AtClass**  
 **int::typeid \!\= pointer\_to\_int::typeid, comme prévu**  
 **int::typeid \=\= handle\_to\_int::typeid, comme prévu**   
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)