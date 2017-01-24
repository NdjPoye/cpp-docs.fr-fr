---
title: "Cibles d’attribut (extensions du composant C++) | Microsoft Docs"
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
  - "attributs personnalisés, les cibles"
ms.assetid: b4e6e224-da77-4520-b6e6-b96846e0ebc1
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cibles d’attribut (extensions du composant C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécificateurs de l’utilisation d’attributs vous permettent de spécifier les cibles d’attribut.  Chaque attribut est défini pour l’appliquer à certains éléments de langage. Par exemple, un attribut peut être défini pour s’appliquent uniquement aux classes et structures.  La liste suivante présente les éléments syntaxiques possibles sur lequel un attribut personnalisé peut être utilisé. Combinaisons de ces valeurs (à l’aide de la logique ou) peut être utilisé.  
  
 Pour spécifier l’attribut cible, pour passer un ou plusieurs <xref:System.AttributeTargets> énumérateurs à <xref:System.AttributeUsageAttribute> lors de la définition de l’attribut.  
  
 Voici une liste des cibles d’attribut valide :  
  
-   `All` (s’applique à toutes les constructions)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::All)]  
    ref class Attr : public Attribute {};  
  
    [assembly:Attr];  
  
    ```  
  
-   `Assembly` (s’applique à un assembly dans son ensemble)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Assembly)]  
    ref class Attr : public Attribute {};  
  
    [assembly:Attr];  
  
    ```  
  
-   `Module` (s’applique à un module dans son ensemble)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Module)]  
    ref class Attr : public Attribute {};  
  
    [module:Attr];  
  
    ```  
  
-   `Class`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Class)]  
    ref class Attr : public System::Attribute {};  
  
    [Attr]   // same as [class:Attr]  
    ref class MyClass {};  
  
    ```  
  
-   `Struct`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Struct)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [struct:Attr]  
    value struct MyStruct{};  
  
    ```  
  
-   `enum`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Enum)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [enum:Attr]  
    enum struct MyEnum{e, d};  
  
    ```  
  
-   `Constructor`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Constructor)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] MyStruct(){}   // same as [constructor:Attr]  
    };  
  
    ```  
  
-   `Method`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Method)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] void Test(){}   // same as [method:Attr]  
    };  
  
    ```  
  
-   `Property`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Property)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] property int Test;   // same as [property:Attr]  
    };  
  
    ```  
  
-   `Field`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Field)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] int Test;   // same as [field:Attr]  
    };  
  
    ```  
  
-   `Event`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Event)]  
    ref class Attr : public Attribute {};  
  
    delegate void ClickEventHandler(int, double);  
  
    ref struct MyStruct{  
    [Attr] event ClickEventHandler^ OnClick;   // same as [event:Attr]  
    };  
  
    ```  
  
-   `Interface`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Interface)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [event:Attr]  
    interface struct MyStruct{};  
  
    ```  
  
-   `Parameter`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Parameter)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    void Test([Attr] int i);  
    void Test2([parameter:Attr] int i);  
    };  
  
    ```  
  
-   `Delegate`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Delegate)]  
    ref class Attr : public Attribute {};  
  
    [Attr] delegate void Test();  
    [delegate:Attr] delegate void Test2();  
  
    ```  
  
-   `ReturnValue`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::ReturnValue)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct {  
    // Note required specifier  
    [returnvalue:Attr] int Test() { return 0; }  
    };  
  
    ```  
  
 En règle générale, un attribut précède directement l’élément de langage auquel il s’applique. Toutefois, dans certains cas, la position d’un attribut n’est pas suffisante pour déterminer la cible de l’attribut. Considérez cet exemple :  
  
```  
[Attr] int MyFn(double x)...  
```  
  
 Point de vue syntaxique, il n’existe aucun moyen de déterminer si l’attribut est destiné à appliquer à la méthode ou à la valeur de retour (dans ce cas, les valeurs par défaut à la méthode). Dans ce cas, un spécificateur d’utilisation de l’attribut peut être utilisé. Par exemple, pour appliquer l’attribut à la valeur de retour, utilisez le `returnvalue` spécificateur, comme suit :  
  
```  
[returnvalue:Attr] int MyFn(double x)... // applies to return value  
```  
  
 Spécificateurs de l’utilisation d’attributs sont requis dans les situations suivantes :  
  
-   Pour spécifier un attribut de niveau assembly ou module.  
  
-   Pour spécifier qu’un attribut s’applique à la valeur de retour d’une méthode, pas la méthode :  
  
    ```  
    [method:Attr] int MyFn(double x)...     // Attr applies to method  
    [returnvalue:Attr] int MyFn(double x)...// Attr applies to return value  
    [Attr] int MyFn(double x)...            // default: method  
    ```  
  
-   Pour spécifier qu’un attribut s’applique à l’accesseur d’une propriété, pas la propriété :  
  
    ```  
    [method:MyAttr(123)] property int Property()    
    [property:MyAttr(123)] property int Property()  
    [MyAttr(123)] property int get_MyPropy() // default: property  
    ```  
  
-   Pour spécifier qu’un attribut s’applique à l’accesseur d’un événement, pas l’événement :  
  
    ```  
    delegate void MyDel();  
    ref struct X {  
       [field:MyAttr(123)] event MyDel* MyEvent;   //field  
       [event:MyAttr(123)] event MyDel* MyEvent;   //event  
       [MyAttr(123)] event MyDel* MyEvent;   // default: event  
    }  
    ```  
  
 Un spécificateur d’utilisation de l’attribut s’applique uniquement à l’attribut qui suit immédiatement. C'est  
  
```  
[returnvalue:Attr1, Attr2]  
```  
  
 est différent de  
  
```  
[returnvalue:Attr1, returnvalue:Attr2]  
```  
  
## <a name="example"></a>Exemple  
  
### <a name="description"></a>Description  
 Cet exemple montre comment spécifier plusieurs cibles.  
  
### <a name="code"></a>Code  
  
```  
  
using namespace System;  
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Struct, AllowMultiple = true )]  
ref struct Attr : public Attribute {  
   Attr(bool i){}  
   Attr(){}  
};  
  
[Attr]  
ref class MyClass {};  
  
[Attr]  
[Attr(true)]  
value struct MyStruct {};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Attributs définis par l’utilisateur](../windows/user-defined-attributes-cpp-component-extensions.md)