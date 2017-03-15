---
title: "attribute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.attribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__typeof keyword"
  - "custom attributes, creating"
  - "attribute attribute"
  - "attributes [C++], custom"
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# attribute
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous permet de créer un attribut personnalisé.  
  
## Syntaxe  
  
```  
  
      [ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### Paramètres  
 *AllowOn*  
 spécifie les éléments de langage auxquels l'attribut personnalisé peut être appliqué.  La valeur par défaut est **System::AttributeTargets::Tout** \(consultez [System : : AttributeTargets](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx)\).  
  
 `AllowMultiple`  
 spécifie si l'attribut personnalisé peut être appliqué à plusieurs reprises à un élément.  la valeur par défaut est **FALSE**.  
  
 `Inherited`  
 Indique si l'attribut doit être héritées par les sous\-classes.  Le compilateur ne fournit pas d'assistance spéciale de cette fonctionnalité ; il s'agit du travail des consommateurs d'attribut \(réflexion, par exemple\) pour respecter ces informations.  si `Inherited` est **TRUE**, l'attribut est hérité.  si `AllowMultiple` est **TRUE**, l'attribut s'accumulera sur le membre dérivé ; si `AllowMultiple` est **FALSE**, l'attribut remplace \(ou remplacer\) dans l'héritage.  Si `Inherited` est **FALSE**, l'attribut n'est pas héritée.  la valeur par défaut est **TRUE**.  
  
## Notes  
  
> [!NOTE]
>  L'attribut d' `attribute` est maintenant déconseillée.  Utilisez l'attribut System.Attribute du common langage runtime directement pour créer des attirbutes définis par l'utilisateur.  Pour plus d'informations, consultez [User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Vous définissez [attribut personnalisé](../windows/custom-attributes-cpp.md) en plaçant l'attribut d' `attribute` sur une définition de classe managée ou de struct.  le nom de la classe est l'attribut personnalisé.  Par exemple :  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 définit un attribut appelé MyAttr qui peut être appliqué aux paramètres de fonction.  la classe doit être publique si l'attribut va être utilisé dans d'autres assemblys.  
  
> [!NOTE]
>  Pour empêcher des collisions de l'espace de noms, tous les noms d'attributs se terminent implicitement par « attribute » ; dans cet exemple, le nom de l'attribut et la classe est réellement MyAttrAttribute, mais MyAttr et MyAttrAttribute peuvent être utilisés indifféremment.  
  
 Les constructeurs publics de la classe définissent des paramètres sans nom de l'attribut.  Les constructeurs surchargés autorisent plusieurs méthodes pour spécifier l'attribut, afin qu'un attribut personnalisé qui est défini de la façon suivante :  
  
```  
// cpp_attr_ref_attribute.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]   // apply attribute to classes  
public ref class MyAttr {  
public:  
   MyAttr() {}   // Constructor with no parameters  
   MyAttr(int arg1) {}   // Constructor with one parameter  
};  
  
[MyAttr]  
ref class ClassA {};   // Attribute with no parameters  
  
[MyAttr(123)]  
ref class ClassB {};   // Attribute with one parameter  
```  
  
 les données membres publiques et les propriétés de la classe sont les paramètres nommés facultatifs de l'attribut :  
  
```  
// cpp_attr_ref_attribute_2.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]  
ref class MyAttr {  
public:  
   // Property Priority becomes attribute's named parameter Priority  
    property int Priority {  
       void set(int value) {}  
       int get() { return 0;}  
   }  
   // Data member Version becomes attribute's named parameter Version  
   int Version;  
   MyAttr() {}   // constructor with no parameters  
   MyAttr(int arg1) {}   // constructor with one parameter  
};  
  
[MyAttr(123, Version=2)]   
ref class ClassC {};  
```  
  
 Pour obtenir la liste des types de paramètre d'attribut, consultez l' [attributs personnalisés](../windows/custom-attributes-cpp.md).  
  
 Consultez l' [User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md) pour une discussion sur les cibles d'attribut.  
  
 L'attribut d' `attribute` a un paramètre d' `AllowMultiple` qui spécifie si l'attribut personnalisé est seul service ou multiuse \(peut apparaître plusieurs fois sur la même entité\).  
  
```  
// cpp_attr_ref_attribute_3.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class, AllowMultiple = true) ]  
ref struct MyAttr {  
   MyAttr(){}  
};   // MyAttr is a multiuse attribute  
  
[MyAttr, MyAttr()]  
ref class ClassA {};  
```  
  
 Les classes d'attributs personnalisées sont dérivées directement ou indirectement d' <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>, qui fait identifier des définitions d'attribut dans les métadonnées rapide et facile.  l'attribut d' `attribute` implique l'héritage du système : : L'attribut, donc la dérivation explicite n'est pas nécessaire :  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 est équivalent à  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute` est un alias pour <xref:System.AttributeUsageAttribute?displayProperty=fullName> \(pas Attributattribute ; il s'agit d'une exception à l'attribut nommant la règle\).  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`ref` **classe**, **structure de référence**|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Exemple  
  
```  
// cpp_attr_ref_attribute_4.cpp  
// compile with: /c /clr  
using namespace System;  
[attribute(AttributeTargets::Class)]  
ref struct ABC {  
   ABC(Type ^) {}  
};  
  
[ABC(String::typeid)]   // typeid operator yields System::Type ^  
ref class MyClass {};  
```  
  
## Exemple  
 `Inherited` nommé argument spécifie si un attribut personnalisé appliqué sur une classe de base présenté à la réflexion d'une classe dérivée.  
  
```  
// cpp_attr_ref_attribute_5.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
[attribute( AttributeTargets::Method, Inherited=false )]  
ref class BaseOnlyAttribute { };  
  
[attribute( AttributeTargets::Method, Inherited=true )]  
ref class DerivedTooAttribute { };  
  
ref struct IBase {  
public:  
   [BaseOnly, DerivedToo]  
   virtual void meth() {}  
};  
  
// Reflection on Derived::meth will show DerivedTooAttribute   
// but not BaseOnlyAttribute.  
ref class Derived : public IBase {  
public:  
   virtual void meth() override {}  
};  
  
int main() {  
   IBase ^ pIB = gcnew Derived;  
  
   MemberInfo ^ pMI = pIB->GetType( )->GetMethod( "meth" );  
   array<Object ^> ^ pObjs = pMI->GetCustomAttributes( true );  
   Console::WriteLine( pObjs->Length ) ;  
}  
```  
  
  **2**   
## Voir aussi  
 [Attributes Alphabetical Reference](../windows/attributes-alphabetical-reference.md)   
 [Custom Attributes](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)